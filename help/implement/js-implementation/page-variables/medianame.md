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


# mediaName

此变量指定视频或媒体项目的名称。

<!-- 

mediaName.xml

 -->

此变量只能通过[!UICONTROL 数据插入 API] 和[!UICONTROL 完全处理数据源]来使用。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 64KB | pev3 | 视频、下一视频流量、上一视频流量、查看的视频区段、视频查看时间 | 无 |

**语法和可能值** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**autoTrack 方法：**

如果使用 [!UICONTROL s.Media.autoTrack]，则不需要明确实施&#x200B;*`mediaName`*&#x200B;变量。它由 JavaScript AppMeasurement 代码自动确定。

**手动跟踪方法：**

语法：

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

可能值:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**示例** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**缺陷、问题和提示** {#section_941A445BB52E4063B0F6920E61BB90DE}

* 仅当使用 [!UICONTROL s.Media.autoTrack] = true 无法跟踪播放器时，才调用媒体跟踪方法。
* 与 VARCHAR(100) 相反，这个变量存储为 mySQL TEXT 变量。
