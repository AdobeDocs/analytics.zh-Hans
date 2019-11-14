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



# linkType

 变量是链接跟踪中使用的可选变量，可以确定要显示链接名称或 URL 的报表（自定义、下载或退出链接）。

<!-- 

linkType.xml

 -->

*`linkType`* 变量通常不是必需的变量，因为可用 *`tl()`* 函数的第二个参数替换它。

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
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
   <td> 一个字符 </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>文件下载 </p> <p>自定义链接 </p> <p>退出链接  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

自定义链接将数据发送给 Analytics。*`linkType`* 变量（或 *`tl()`* 函数中的第二个参数）用于识别将显示链接名称或 URL 的报表（[!UICONTROL 自定义]、[!UICONTROL 下载]或[!UICONTROL 退出链接]报表）。

对于退出和下载链接，将根据所点击的链接是退出链接还是下载链接，自动填充 *`linkType`* 变量。可以使用此变量或 *`tl()`* 函数中的第二个参数将自定义链接配置为将数据发送到三个报表中的任何一个。通过将 *`linkType`* 设置为“o”、“e”或“d”，可分别将 *`linkName`* 或链接 URL 发送到[!UICONTROL 自定义链接]、[!UICONTROL 退出链接]或[!UICONTROL 文件下载]报表。

**语法和可能值** {#section_18DB3A8083FB4F75B970055ED336DA4E}

*`linkType`* 变量语法取决于您使用的是 XML 还是查询字符串。

如果您使用的是 XML，则此变量只能包含单个字符，即“o”、“e”或“d”。

```js
s.tl(this,'o','Link Name');
```

如果您使用的是查询字符串 `pe`，则需要使用 `lnk_d`、`lnk_e` 或 `lnk_o`。

**示例** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**配置设置** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

无

**缺陷、问题和提示** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* 如果未指定 *`linkType`*，则使用自定义链接（“o”）。
