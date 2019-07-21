---
description: 您可以使用 s.tl() 函数来跟踪自定义元素并配置动态内容的叠加图呈现。
seo-description: 您可以使用 s.tl() 函数来跟踪自定义元素并配置动态内容的叠加图呈现。
seo-title: 使用s. tl()函数
solution: Analytics
title: 使用s. tl()函数
topic: Activity Map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用s. tl()函数

您可以使用 s.tl() 函数来跟踪自定义元素并配置动态内容的叠加图呈现。

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

通过将 [s.tl() 函数](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html)用作 Activity Map AppMeasurement 模块的一部分，您可以跟踪任何经过单击的对象，甚至可以跟踪不属于锚标记或图像元素的对象。通过使用 s.tl，您可以跟踪未导致页面加载的任何自定义元素。

在 s.tl 函数中，当前用于识别退出链接、自定义链接等内容的 linkName 参数现在也可用来识别 Activity Map 变量的链接 ID。

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

换句话说，如果您使用 s.tl 来跟踪您的自定义元素，那么链接 ID 是从作为 s.tl 函数中第三个参数 (linkName) 的值中提取的。它并非是从 Activity Map 中用于进行[默认跟踪](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)的标准链接跟踪算法中提取。

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

如果是从 HTML 元素的单击事件直接调用 s.tl() 函数，则在加载 Web 页面时，Activity Map 可以显示此元素的叠加图。示例：

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

初始页面加载后，无论何时向该页面添加任何网页内容，都是间接调用 s.tl 函数，因此我们无法显示新增内容的叠加图，除非明确地激活/单击页面。随后，会通过 Activity Map 触发新的链接收集进程。

如果不是从 HTML 元素的单击事件直接调用 s.tl() 函数，那么只有当用户单击此元素后，Activity Map 才会显示叠加图。下面是间接调用 s.tl() 函数的示例：

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

Activity Map 叠加动态内容链接的最佳做法是设置一个自定义 ActivityMap.link 函数，以调用其返回值将传递到 s.tl 的相同函数。以下是一个示例：

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type=”button” onclick=”s.tl(this,’o’,makeLinkName(this)”>Add To Cart</button>
```

这里，我们覆盖了 ActivityMap.link 函数，以便在调用时执行以下三个任务之一：

1. 如果传递 linkName，ActivityMap.link 将由 s.tl() 调用，这样只需返回 s.tl 作为 linkName 传入的内容。
1. 这将在报告时由 Activity Map 调用，因此绝不会传递 linkName，从而会调用具有链接元素的 makeLinkName()。This is the crucial step here - the “makeLinkName(element)” call should be the same at the s.tl call’s 3rd argument in the `<button>` tag. 这意味着在调用 s.tl 时，我们会跟踪由 makeLinkName 返回的字符串。Activity Map 在报告页面中的链接时，会使用相同的调用来创建链接。
1. 最终的解决方案是只返回默认 ActivityMap 链接函数的原始返回值。在默认情况下将此引用与调用保持联系，可使您只需覆盖或写入 makeLinkName 的自定义代码，而无需为页面上的所有链接创建链接返回值。
