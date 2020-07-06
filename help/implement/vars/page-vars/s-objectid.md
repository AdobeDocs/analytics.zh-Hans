---
title: s_objectID
description: 帮助 Activity Map 识别您网站上的唯一链接。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 100%

---


# s_objectID

`s_objectID` 变量为链接提供唯一标识符。此变量可使 [Activity Map](/help/analyze/activity-map/activity-map.md) 中的报表更准确。如果页面上的链接经常更改，则可以使用 `s_objectID` 变量告知 Activity Map 唯一链接位置，以便它可以根据需要正确地对数据进行分组。

如果 Activity Map 的准确性对贵组织至关重要，Adobe 建议在网站的链接的 `onClick` 事件中包含 `s_objectID` 变量。有关更多信息，请参阅分析用户指南中的 ](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md)Activity Map 链接跟踪用例[。

## Adobe Experience Platform Launch 中的对象 ID

Launch 中没有可使用此变量的专用字段。按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s_objectID

`s_objectID` 变量是全局变量，这意味着它独立于 Analytics 跟踪对象运行（默认情况下为 `s`）。此变量的有效值可以是长度不超过 100 字节的任何字符串。如果未定义此变量，则 Activity Map 会将链接 URL 用作此链接的标识符。

此变量通常在 HTML 链接的 `onClick` 事件中设置。

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
> 将始终包含用于结束 JavaScript 语句的分号。Activity Map 需要分号才能正常工作。

## 用例

当您想提高 Activity Map 报表的准确性时，`s_objectID` 变量就很有作用。

### 从高动态内容中聚合链接

某些网站具有高动态内容，例如新闻网站或项目频繁轮换的零售网站。由于 Activity Map 默认使用链接 URL 作为标识符，因此很难了解链接频繁更改的页面上点击次数最多的区域。如果您在这些链接中使用 `s_objectID`，则 Activity Map 会了解哪些链接可以聚合，而不管它们指向哪些 URL。

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

无论链接指向何处或更改这些链接的频率如何，Activity Map 都会根据 `s_objectID` 中的值聚合数据。

### 在页面上保持链接分开

某些网站中不同位置具有指向同一位置的链接。例如，网站上页眉和页脚中指向主页的链接。由于这些链接具有相同的 URL，因此 Activity Map 会聚合其数据。您可以使用 `s_objectID` 变量将它们分开：

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

即使链接指向同一 URL，Activity Map 也可以使用 `s_objectID` 变量在报表中正确区分它们。
