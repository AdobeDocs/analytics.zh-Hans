---
title: s_objectID
description: 帮助 Activity Map 识别您网站上的唯一链接。
feature: Appmeasurement Implementation
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 80%

---

# s_objectID

`s_objectID` 变量为链接提供唯一标识符。此变量可使 [Activity Map](/help/analyze/activity-map/overview.md) 中的报表更准确。如果页面上的链接经常更改，则可以使用 `s_objectID` 变量告知 Activity Map 唯一链接位置，以便它可以根据需要正确地对数据进行分组。

如果Activity Map的准确性对贵组织至关重要，Adobe建议在网站链接的`s_objectID`事件中包含`onClick`变量。

## 使用Adobe Analytics扩展的对象ID

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s_objectID

`s_objectID` 变量是全局变量，这意味着它独立于 Analytics 跟踪对象运行（默认情况下为 `s`）。此变量的有效值可以是长度不超过 100 字节的任何字符串。如果未定义此变量，Activity Map会将链接文本用作链接的标识符。

此变量通常在 HTML 链接的 `onClick` 事件中设置。

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>将始终包含用于结束 JavaScript 语句的分号。Activity Map 需要分号才能正常工作。

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

即使链接指向同一URL，Activity Map也可以使用`s_objectID`变量在报表中正确区分它们。
