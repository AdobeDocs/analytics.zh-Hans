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


# mediaLength

 变量可指定正在播放的媒体的总长度。

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大大小 </th> 
   <th class="entry"> 调试程序参数 </th> 
   <th class="entry"> 填充报表 </th> 
   <th class="entry"> 默认值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 整个 pev3 请求无最大大小 - 大小受浏览器的 URL 长度限制。 </td> 
   <td> pev3 </td> 
   <td> 视频查看时间； <p>查看的视频区段 </p> </td> 
   <td> 无 </td> 
  </tr> 
 </tbody> 
</table>

**语法和可能值** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**autoTrack 方法：**

如果使用 [!UICONTROL s.Media.autoTrack]，则不需要明确实施 [!UICONTROL mediaLength] 变量。它由 JavaScript AppMeasurement 代码自动确定。

**手动跟踪方法：**

语法：

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能值:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**示例** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**缺陷、问题和提示** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* 只有在使用 [!UICONTROL s.Media.autoTrack] = true 无法跟踪播放器时，才需要调用媒体跟踪方法。
* 如果不是使用 [!UICONTROL autoTrack] 进行跟踪，请务必以秒为单位设置其长度。

