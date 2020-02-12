---
description: 可以使用s.tl()方法跟踪自定义元素并配置动态内容的叠加渲染。
title: 使用s.tl()方法
topic: Activity map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 290526ecc1b040f93d0734a5deaf2d79ab1bde10

---


# 使用方 `tl` 法

You can use the `tl` method to track custom elements and to configure overlay rendering for dynamic content.

## 跟踪自定义元素 {#section_5D6688DFFFC241718249A9A0C632E465}

Using the [`tl` method](/help/implement/vars/functions/tl-method.md) as part of the Activity Map AppMeasurement module lets you track any object that is clicked on, even objects that are not anchor tags or image elements. 通过使用 s.tl，您可以跟踪未导致页面加载的任何自定义元素。

In the `tl` method, the `linkName` parameter that is currently used to identify the exit links, custom links, etc. 现在也可用来识别 Activity Map 变量的链接 ID。

```js
s.tl(this,linkType,linkName,variableOverrides)
```

In other words, if you use `s.tl` to track your custom elements, the link ID is pulled from the value passed as the third parameter (linkName) in the `s.tl` method. 它并非是从 Activity Map 中用于进行[默认跟踪](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)的标准链接跟踪算法中提取。

## 动态内容的叠加图呈现 {#section_FD24B61A732149C7B58BA957DD84A5E7}

如果是从 HTML 元素的单击事件直接调用 s.tl() 函数，则在加载网页时，Activity Map 可以显示此元素的叠加图。示例：

```html
<div onclick="s.tl(this,'o','Example custom link')">Example link text</a>
```

Whenever any web page content is added to the page after the initial page load, the `tl` method is called indirectly and we cannot display overlays for that new content unless it is expressly activated/clicked. 随后，会通过 Activity Map 触发新的链接收集进程。

When the `tl` method is not called directly from the HTML element&#39;s on-click event, Activity Map can only display overlay once that element has been clicked by the user. Here is an example where the `tl` method is called indirectly:

```html
<div onclick="someFn(event)"></div>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

The best way for Activity Map to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to `s.tl`. 例如：

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName) {
    return linkName ||      // if this is a s.tl call, just return string passed
        makeLinkName(element) || // this is ActivityMap reporting time
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

这里，我们覆盖了 ActivityMap.link 函数，以便在调用时执行以下三个任务之一：

1. 如果传递 linkName，ActivityMap.link 将由 s.tl() 调用，这样只需返回 s.tl 作为 linkName 传入的内容。
2. 这将在报告时由 Activity Map 调用，因此绝不会传递 linkName，从而会调用具有链接元素的 makeLinkName()。下面是一个关键步骤 -“makeLinkName(element)”调用应当与 s.tl 调用在 `<button>` 标记中的第三个参数相同。这意味着在调用 s.tl 时，我们会跟踪由 makeLinkName 返回的字符串。Activity Map 在报告页面中的链接时，会使用相同的调用来创建链接。
3. 最终的解决方案是只返回默认 ActivityMap 链接函数的原始返回值。在默认情况下将此引用与调用保持联系，可使您只需覆盖或写入 makeLinkName 的自定义代码，而无需为页面上的所有链接创建链接返回值。
