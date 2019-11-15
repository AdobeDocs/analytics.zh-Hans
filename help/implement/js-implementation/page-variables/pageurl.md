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


# pageUrl

 变量覆盖实际的页面 URL。

<!-- 

pageURL.xml

 -->

在少数情况下，页面的 URL 不是您想在 Analytics 中报告的 URL。

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
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
   <td> 无限制* </td> 
   <td> <p>G </p> </td> 
   <td> “流量”&gt;“分段”&gt;“最受欢迎页面路径” </td> 
   <td> 页面 URL </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE]尽管 Adobe 允许 *`pageURL`* 值为 64k，但一些浏览器对图像请求 URL 的大小存在限制。为了避免其他数据出现截断的情况，大于 255 字节的页面 URL 被拆分，前面的 255 个字节显示在 `g=` 参数中，剩下的字节稍后显示在 `-g=` 查询参数的查询字符串中。

**语法和可能值** {#section_22AF3BF7C2F743549967B0C760A095C0}

*`pageURL`* 变量必须为使用有效协议的有效 URL。域被填充到报表之前，将强制以小写字母形式显示域名，并有可能根据 Analytics 设置清空查询字符串。

```js
s.pageURL="proto://domain/path?query_string"
```

页面 URL 只能采用 URL 兼容的字符。

> [!NOTE]强烈建议您在将 *`pageURL`* 变量用于自定义目的之前，先联系 Adobe 顾问或 Adobe 客户关怀。

**示例** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**配置设置** {#section_A8F77DAD88164528ACC5C16C066B47DF}

无

