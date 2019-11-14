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



# linkName

该变量是用于[!UICONTROL 链接跟踪]的可选变量，可确定自定义链接、下载链接或退出链接的名称。

<!-- 

linkName.xml

 -->

*`linkName`* 变量通常不是必需的变量，因为可用 *`tl()`* 函数的第三个参数替换它。

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> 100 字节 </td> 
   <td> pev2 </td> 
   <td> <p>文件下载 </p> <p>自定义链接 </p> <p>退出链接  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL 自定义链接]是指发送跟踪数据的链接。此 *`linkName`* 变量（或 *`tl()`* 函数中的第三个参数）可用于确定显示在[!UICONTROL 自定义报表]、[!UICONTROL 下载报表]或[!UICONTROL 退出链接报表]中的值。如果 *`linkName`* 未被填充，则该链接的 URL 会在报表中显示。

**语法和可能值** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

*`linkName`* 变量除标准变量限制以外，无其它限制。

**示例** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**配置设置** {#section_F15FF429FC274F708D50DF79D4668EA3}

无

**缺陷、问题和提示** {#section_170A78452A7340B5B229713AC1FB71FA}

* *`linkName`* 变量可由 *`tl()`* 函数的第三个参数替换。

* 如果将 *`linkName`* 变量和 *`tl()`* 函数的第三个参数留为空白，则此链接的完整 URL（查询字符串除外）将在报表中显示（即使链接为相对链接）。
