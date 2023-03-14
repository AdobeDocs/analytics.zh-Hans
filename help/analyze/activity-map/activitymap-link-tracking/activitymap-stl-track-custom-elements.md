---
title: 对Activity Map使用tl()方法
description: 您可以使用tl()方法跟踪自定义元素并配置动态内容的叠加图呈现。
feature: Activity Map
role: User, Admin
exl-id: e4e32de7-0e46-413a-abc9-9707e273903d
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 43%

---

# 使用 `tl()` 具有Activity Map的方法

您可以使用 `tl()` 方法来跟踪自定义元素并配置动态内容的叠加图呈现。

## 跟踪自定义元素

通过将 [`tl()` 方法](/help/implement/vars/functions/tl-method.md)用作 Activity Map AppMeasurement 模块的一部分，您可以跟踪任何经过单击的对象，甚至可以跟踪不属于锚标记或图像元素的对象。使用 `tl()`中，您可以跟踪任何不会导致页面加载的自定义元素。

在 `tl()` 方法中，当前用于识别退出链接、自定义链接等内容的 `linkName` 参数。现在也可用来识别 Activity Map 变量的链接 ID。

```js
s.tl([Link object],[Link type],[Link name],[Override variable]);
```

换句话说，如果您使用 `tl()` 为了跟踪您的自定义元素，将从作为第三个参数（链接名称）的值中提取链接ID， `tl()` 方法。 它并非是从 Activity Map 中用于进行[默认跟踪](activitymap-link-tracking-methodology.md)的标准链接跟踪算法中提取。

## 动态内容的叠加图呈现

当 `tl()` 方法直接从HTML元素的单击事件调用，Activity Map可以在加载网页时显示该元素的叠加图。 示例：

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

Activity Map叠加动态内容链接的最佳方式是自定义动态内容链接 `ActivityMap.link` 函数设置，以调用其返回值将传递到的相同函数 `tl()`. 例如：

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

在此，我们已覆盖 `ActivityMap.link` 函数在调用时执行以下三项操作之一：

1. 如果 `linkName` 通过，然后调用此函数 `tl()`，只需返回以下内容 `tl()` 传入身份 `linkName`.
2. 当Activity Map在报表时间调用时， `linkName` 从未传递，因此调用 `makeLinkName()` 链接元素。 这是关键的一步 —  `makeLinkName(element)` 调用应与 `tl()` 调用中的第3个参数 `<button>` 标记之前。 这意味着 `tl()` 名为，我们跟踪返回的字符串 `makeLinkName()`. 当Activity Map报告页面上的链接时，它会使用相同的调用来生成链接。
3. 最终的解决方案是只返回默认 ActivityMap 链接函数的原始返回值。在默认情况下将此引用保留为调用可帮助您只需覆盖或编写自定义代码 `makeLinkName()` 而且不必为页面上的所有链接提供链接返回值。
