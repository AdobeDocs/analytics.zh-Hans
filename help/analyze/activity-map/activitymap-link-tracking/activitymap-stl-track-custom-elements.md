---
title: 将tl()方法与Activity Map结合使用
description: 您可以使用tl()方法跟踪自定义元素并配置动态内容的叠加图呈现。
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 43%

---

# 将`tl()`方法与Activity Map结合使用

您可以使用 `tl()` 方法来跟踪自定义元素并配置动态内容的叠加图呈现。

## 跟踪自定义元素

通过将 [`tl()` 方法](/help/implement/vars/functions/tl-method.md)用作 Activity Map AppMeasurement 模块的一部分，您可以跟踪任何经过单击的对象，甚至可以跟踪不属于锚标记或图像元素的对象。使用`tl()`，您可以跟踪任何不导致页面加载的自定义元素。

在 `tl()` 方法中，当前用于识别退出链接、自定义链接等内容的 `linkName` 参数。现在也可用来识别 Activity Map 变量的链接 ID。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

换言之，如果您使用`tl()`跟踪自定义元素，则链接ID是从作为`tl()`方法中第三个参数（链接名称）的值中提取的。 它并非是从 Activity Map 中用于进行[默认跟踪](activitymap-link-tracking-methodology.md)的标准链接跟踪算法中提取。

## 动态内容的叠加图呈现

如果从HTML元素的单击事件直接调用`tl()`方法，则在加载网页时，Activity Map可以显示该元素的叠加图。 示例：

```html
<a href="javascript:" onclick="s.tl(this,'o','Example custom link');">Example link text</a>
```

初始页面加载后，无论何时向该页面添加任何网页内容，都是间接调用 `tl()` 方法，因此我们无法显示新增内容的叠加图，除非明确地激活/单击页面。随后，会通过 Activity Map 触发新的链接收集进程。

如果不是从 HTML 元素的单击事件直接调用 `tl()` 方法，则只有当用户单击此元素后，Activity Map 才会显示叠加图。下面是间接调用 `tl()` 方法的示例：

```html
<a href="javascript:" onclick="someFn(event);">Example link text</a>
<script>function someFn (event)
{
  s.tl(event.srcElement,'o','Example custom link');
}
</script>
```

Activity Map叠加动态内容链接的最佳方式是设置一个自定义`ActivityMap.link`函数，以调用其返回值将传递到`tl()`的相同函数。 例如：

```js
var originalLinkFunction = s.ActivityMap.link;
s.ActivityMap.link = function(element,linkName)
{
    // if this is a s.tl call, just return string passed
    return linkName ||      
    // this is ActivityMap reporting time
    makeLinkName(element) ||
    // our custom function didn't return anything, so just return the default ActivityMap Link
    originalLinkFunction(element,linkName);
};
```

```html
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

在此，我们覆盖了`ActivityMap.link`函数，以便在调用时执行以下三种操作之一：

1. 如果传递了`linkName`，则此变量由`tl()`调用，因此只需返回作为`linkName`传递的`tl()`内容即可。
2. 当Activity Map在报告时调用时，永远不会传递`linkName`，因此使用链接元素调用`makeLinkName()`。 下面是关键步骤 — `makeLinkName(element)`调用应与`<button>`标记中`tl()`调用的第3个参数相同。 这意味着在调用`tl()`时，我们会跟踪由`makeLinkName()`返回的字符串。 当Activity Map报告页面上的链接时，它会使用相同的调用来创建链接。
3. 最终的解决方案是只返回默认 ActivityMap 链接函数的原始返回值。在默认情况下，将此引用保留为调用有助于您只需覆盖或编写`makeLinkName()`的自定义代码，而无需为页面上的所有链接提供链接返回值。
