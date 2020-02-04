---
title: s_objectID
description: 帮助活动图可识别您网站上的唯一链接。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# s_objectID

变量 `s_objectID` 为链接提供唯一标识符。 它用于使活动图中的报 [表更准确](/help/analyze/activity-map/activity-map.md) 。 如果页面上有经常更改的链接，则可以使用变量向Activity map告知唯一的链接位置，以便它能够根据需要正确分组数据。 `s_objectID`

如果Activity map的准确性对您的组织至关重要，则Adobe建议在您的 `s_objectID` 站点上出现 `onClick` 链接时包含该变量。 有关详 [细信息，请参阅“分析用户指南](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) ”中的Activity map链接跟踪用例。

## Adobe Experience Platform Launch中的对象ID

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和Launch自定义代码编辑器中的s_objectID

该 `s_objectID` 变量是全局变量，这意味着它独立于Analytics跟踪对象运行(默`s` 认情况下)。 此变量的有效值可以是长度不超过100字节的任何字符串。 如果未定义此变量，则Activity map将链接URL用作链接的标识符。

此变量通常在HTML链 `onClick` 接事件中设置。

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

> [!NOTE] 始终包含结束JavaScript语句的分号。 Activity map要运行，必须使用分号。

## 用例

只要您 `s_objectID` 希望Activity map报告中的准确性更高，该变量就很有价值。

### 从高度动态的内容聚合链接

某些站点具有高度动态的内容，例如新闻站点或具有频繁旋转项目的零售站点。 由于Activity map默认使用链接URL作为标识符，因此很难了解链接频繁更改的页面上点击量最大的区域。 如果您在这些链 `s_objectID` 接中使用，则Activity Map会了解哪些链接可以聚合，而不管它们指向的URL是什么。

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

无论链接指向何处或更改这些链接的频率如何，Activity map都会根据中的值聚合数据 `s_objectID`。

### 在页面上保持链接独立

某些站点具有指向不同位置的同一位置的链接。 例如，指向站点的页眉和页脚中主页的链接。 由于这些链接具有相同的URL，因此Activity map会聚合其数据。 您可以使用变量将它们分 `s_objectID` 开：

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

即使链接指向同一URL,Activity Map也可以使用变量在报 `s_objectID` 告中正确区分它们。
