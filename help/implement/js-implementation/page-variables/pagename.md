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


# pageName

 变量包含网站中每个页面的名称。

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
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
   <td> pageName </td> 
   <td> <p>页面 </p> <p>路径 </p> </td> 
   <td> 页面 URL </td> 
  </tr> 
 </tbody> 
</table>

The *`pageName`*&#x200B;变量应使用企业用户可识别的值填充。在大多数情况下，*`pageName`* 值不是 URL 或文件路径。通用 *`pageName`* 值包括一些名称，如“主页”、“结帐”、“感谢购买”或“注册”。

请注意，页面名称和其他变量中不允许出现换行符、长划线或短划线，或任何 HTML 字符。有些浏览器可以传送换行符，而有些则不能，这会导致 Analytics 中的数据被分割到两个看起来相同的页面名称。在键入连字符时，许多文字处理器和电子邮件客户端会自动将其转换为长划线或短划线。由于长划线和短划线在 Analytics 变量中被视为非法字符（编码值高于 127 的 ASCII 字符），因此 Analytics 不会记录包含非法字符的页面名称，而改为显示 URL。

如果 *`pageName`* 留空，则会用 URL 来代表页面名称。将 *`pageName`* 留空常会导致一些问题，因为一个页面的 URL 有可能会变化，不总是相同，如 `www.mysite.com` 和 `mysite.com` 是不同的 URL，但却是同一个页面。

**语法和可能值** {#section_7A61EE70F1A84D26B414404998C84BA8}

*`pageName`* 变量应当包含一个有用的标识符，以供 Analytics 的企业用户使用。

```js
s.pageName="page_name"
```

*`pageName`* 除标准变量限制以外，无其它限制。

**示例** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**配置设置** {#section_58CBC68C805344A999EB47455FEBA8D5}

管理员可以使用[!UICONTROL 命名页面]工具在 Analytics 中更改显示的页面名称，这存在潜在的危险，可能会对报表造成负面影响。在使用命名页面工具之前，请联系 Adobe [!UICONTROL 客户关怀]部门。

**缺陷、问题和提示** {#section_BB41DC9682C34385B9CAA80D5257C113}

确保 *`pageName`* 不包含非法字符。
