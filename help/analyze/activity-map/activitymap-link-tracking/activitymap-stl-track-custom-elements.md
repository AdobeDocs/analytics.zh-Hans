---
title: 将tl()方法与Activity Map
description: 可以使用tl()方法跟踪自定义元素并为动态内容配置叠加渲染。
feature: Activity Map
role: 业务从业者，管理员
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 43%

---


# 将`tl()`方法与Activity Map

您可以使用 `tl()` 方法来跟踪自定义元素并配置动态内容的叠加图呈现。

## 跟踪自定义元素

通过将 [`tl()` 方法](/help/implement/vars/functions/tl-method.md)用作 Activity Map AppMeasurement 模块的一部分，您可以跟踪任何经过单击的对象，甚至可以跟踪不属于锚标记或图像元素的对象。使用`tl()`，可以跟踪不导致页面加载的任何自定义元素。

在 `tl()` 方法中，当前用于识别退出链接、自定义链接等内容的 `linkName` 参数。现在也可用来识别 Activity Map 变量的链接 ID。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

换句话说，如果使用`tl()`跟踪自定义元素，则将从作为`tl()`方法中的第三个参数(Link name)传递的值中提取链接ID。 它并非是从 Activity Map 中用于进行[默认跟踪](activitymap-link-tracking-methodology.md)的标准链接跟踪算法中提取。

## 动态内容的叠加图呈现

从HTML元素的单击事件直接调用`tl()`方法时，加载网页时，Activity Map可以显示该元素的叠加。 示例：

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

Activity Map叠加动态内容链接的最佳方法是设置自定义`ActivityMap.link`函数以调用返回值传递给`tl()`的相同函数。 例如：

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

在此，我们覆盖了`ActivityMap.link`函数，以在调用时执行以下三项操作之一：

1. 如果传递了`linkName`，则由`tl()`调用，因此只需返回作为`linkName`传递的`tl()`。
2. 当Activity Map在报告时调用`linkName`时，不会传递，因此使用链接元素调用`makeLinkName()`。 这是此处的关键步骤 — `makeLinkName(element)`调用应与`<button>`标记中`tl()`调用的第3个参数相同。 这意味着当调用`tl()`时，我们将跟踪由`makeLinkName()`返回的字符串。 当Activity Map报告页面上的链接时，它使用相同的调用来建立链接。
3. 最终的解决方案是只返回默认 ActivityMap 链接函数的原始返回值。在默认情况下，保持此引用可帮助您只需要覆盖或编写`makeLinkName()`的自定义代码，而不必为页面上的所有链接提供链接返回值。
