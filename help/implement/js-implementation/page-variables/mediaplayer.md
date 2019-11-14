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


# mediaPlayer

此变量指定用于播放视频或媒体项目的播放器。

<!-- 

mediaPlayer.xml

 -->

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | pev3 | 视频播放器 | 无 |

**语法和可能值** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**autoTrack 方法：**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**手动跟踪方法：**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能值:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**示例** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**缺陷、问题和提示** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

仅当使用 s.Media.autoTrack = true 无法跟踪播放器时，才调用媒体跟踪方法。

