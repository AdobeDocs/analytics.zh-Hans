---
description: 您可以使用 s.tl() 函数来跟踪自定义元素并配置动态内容的叠加图呈现。
seo-description: 您可以使用 s.tl() 函数来跟踪自定义元素并配置动态内容的叠加图呈现。
seo-title: 使用 s.tl() 函数
solution: Analytics
title: 使用 s.tl() 函数
topic: Activity Map
uuid: 59e062af-6a1c-46ff-9c3b-6cf7a0453711
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 使用 s.tl() 函数

您可以使用 s.tl() 函数来跟踪自定义元素并配置动态内容的叠加图呈现。

## Tracking custom elements {#section_5D6688DFFFC241718249A9A0C632E465}

通过将 [s.tl() 函数](https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html)用作 AppMeasurement 模块的一部分，您可以跟踪任何经过单击的对象，甚至可以跟踪不属于锚标记或图像元素的对象。[!DNL Activity Map]通过使用 s.tl，您可以跟踪未导致页面加载的任何自定义元素。

在 s.tl 函数中，当前用于识别退出链接、自定义链接等内容的 linkName 参数is now also used to identify the Link ID for the [!DNL Activity Map] variable.

```
s.tl(this,linkType, 
<b>linkName</b>,variableOverrides,doneAction)
```

换句话说，如果您使用 s.tl 来跟踪您的自定义元素，那么链接 ID 是从作为 s.tl 函数中第三个参数 (linkName) 的值中提取的。It is not pulled from the standard link tracking algorithm that is used for [default tracking](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) in [!DNL Activity Map].

## Overlay rendering for dynamic content {#section_FD24B61A732149C7B58BA957DD84A5E7}

When the s.tl() function is called directly from the HTML element's on-click event, [!DNL Activity Map] can display an overlay for that element when the web page is loaded. 示例:

```
<div onclick="s.tl(this,'o','some link name')">Text to click on</a>
```

初始页面加载后，无论何时向该页面添加任何网页内容，都是间接调用 s.tl 函数，因此我们无法显示新增内容的叠加图，除非明确地激活/单击页面。Then a new link collection process is triggered from [!DNL Activity Map].

When the s.tl() function is not called directly from the HTML element's on-click event, [!DNL Activity Map] can only display overlay once that element has been clicked by the user. 下面是间接调用 s.tl() 函数的示例：

```
<div onclick="someFn(event)"></div> 
 <script>function someFn (event) 
 {    
 s.tl(event.srcElement,'o','some link name'); 
 } 
 </script>
```

The best way for [!DNL Activity Map] to overlay dynamic content links is to have a customized ActivityMap.link function set up to call the same function whose return value is passed to s.tl. 以下是一个示例：

```
var originalLinkFunction = s.ActivityMap.link; 
s.ActivityMap.link = function(element,linkName){ 
    return linkName ||      // if this is a s.tl call, just return string passed 
        makeLinkName(element) || // this is ActivityMap reporting time 
        originalLinkFunction(element,linkName); // our custom function didn't return anything, so just return the default ActivityMap Link 
};
```

```
<button type="button" onclick="s.tl(this,'o',makeLinkName(this)">Add To Cart</button>
```

这里，我们覆盖了 ActivityMap.link 函数，以便在调用时执行以下三个任务之一：

1. 如果传递 linkName，ActivityMap.link 将由 s.tl() 调用，这样只需返回 s.tl 作为 linkName 传入的内容。
1. This is called by [!DNL Activity Map] at reporting time, so a linkName is never passed, and so call makeLinkName() with the link element. This is the crucial step here - the "makeLinkName(element)" call should be the same at the s.tl call's 3rd argument in the `<button>` tag. 这意味着在调用 s.tl 时，我们会跟踪由 makeLinkName 返回的字符串。When [!DNL Activity Map] reports on the links on the page, is uses the same call to make a link.
1. 最终的解决方案是只返回默认 ActivityMap 链接函数的原始返回值。在默认情况下将此引用与调用保持联系，可使您只需覆盖或写入 makeLinkName 的自定义代码，而无需为页面上的所有链接创建链接返回值。
