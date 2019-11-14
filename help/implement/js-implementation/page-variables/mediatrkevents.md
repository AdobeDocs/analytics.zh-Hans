---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# Media.trackEvents

 变量会确定点击媒体时应发送哪些事件。

<!-- 

media_trackEvents.xml

 -->

此变量仅适用于 JavaScript 和 [!UICONTROL ActionSource]。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | s.Media.trackEvents="None" |

**语法和可能值** {#section_66A978EF56914BEAAE73359A268A1B4A}

事件名称，如 event1 或 purchase。

**示例** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**缺陷、问题和提示** {#section_030B11C64EE84D46A85CA550DB732D28}

请确保只要填充了此变量就使用“events”填充 [!UICONTROL trackVars]。
