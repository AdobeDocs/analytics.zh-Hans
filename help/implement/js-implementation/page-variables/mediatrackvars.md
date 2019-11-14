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


# Media.trackVars

 变量用来确认点击媒体时应发送哪些变量。

<!-- 

media_trackVars.xml

 -->

此变量仅适用于 JavaScript 和 [!UICONTROL ActionSource]。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | s.Media.trackVars="None" |

**语法和可能值** {#section_7374684A7EB34AE685E8C40A66CFD289}

变量名称，例如 [!UICONTROL propN]、*`eVarN`*、*`events`*、*`channel`* 等。

**示例** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**缺陷、问题和提示** {#section_615AE1B696124B00B78F651B03813EAB}

* 即使在 [!UICONTROL trackVars] 中指定了 eVar3，点击媒体时也会发送此变量。

## 移动设备 {#concept_0CEE045F57B444138C0EAA015FC7EA70}

 变量可控制使用 Cookie 和订阅者 ID 识别访客的顺序。

<!-- 

mobile.xml

 -->

请参阅[移动网络协议](/help/implement/js-implementation/c-additional-libraries/network-protocols.md)。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 图像 URL 路径中的 /5/ 或 /1/ | 不适用 | 无 |

**语法和可能值** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**缺陷、问题和提示** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

在 JavaScript Cookie 实施中使用 *`s.mobile`* 变量时，请使用跨访客标识来降低访客流量可能出现的峰值。
