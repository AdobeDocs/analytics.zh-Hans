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


# pageType

 变量仅用于指定“页面未找到”404 错误页面。

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
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
   <td> 20 字节 </td> 
   <td> pageType </td> 
   <td> “路径”&gt;“页面”&gt;“页面 <p>未找到” </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. 完全按照以下所示在错误页面上设置 *`pageType`* 变量。

不要在 404 错误页面上使用页面名称变量。此&#x200B;*`pageType`*&#x200B;变量仅用于 404 错误页面。

大多数情况下，404 错误页面是一个硬编码的静态页面。在这种情况下，将 .JS 文件的引用设置为合适的全局或相对路径/目录非常重要。

**语法和可能值** {#section_C1C59968226446559B05F6EE7374D525}

*`pageType`* 唯一允许使用的值为“errorPage”，如下所示。

```js
s.pageType="errorPage"
```

**示例** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**配置设置** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

无

**缺陷、问题和提示** {#section_943681AB01FE47BEAC72E93CB60C53C8}

如果要捕获其他服务器端错误（如 500 错误），请使用 prop 捕获错误消息，并在 *`pageName`* 变量中放置“`500 Error: <URL>`”，其中 `<URL>` 是请求的 URL。按照这一操作过程，您可以使用[!UICONTROL 路径分析]报表查看是哪些路径导致用户产生 500 错误。prop 可解释哪个错误消息是由服务器发出的。

