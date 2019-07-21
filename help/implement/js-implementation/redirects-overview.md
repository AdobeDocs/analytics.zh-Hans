---
description: 重定向无需用户交互即可将浏览器指向新的位置。重定向可以在 Web 浏览器（客户端重定向）或 Web 服务器（服务器端重定向）上执行。
keywords: Analytics 实施
seo-description: 重定向无需用户交互即可将浏览器指向新的位置。重定向可以在 Web 浏览器（客户端重定向）或 Web 服务器（服务器端重定向）上执行。
seo-title: 重定向和别名
solution: Analytics
subtopic: 重定向
title: 重定向和别名
topic: 开发人员和实施
uuid: 11f ad7a-5c45-410f-86dd-b7 d2 cec2 aae3
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 重定向和别名

重定向无需用户交互即可将浏览器指向新的位置。重定向可以在 Web 浏览器（客户端重定向）或 Web 服务器（服务器端重定向）上执行。

## Redirects and aliases {#concept_F4F1D53D473947FE8554897332545763}

重定向无需用户交互即可将浏览器指向新的位置。重定向可以在 Web 浏览器（客户端重定向）或 Web 服务器（服务器端重定向）上执行。

由于重定向不需要任何用户交互，因此用户通常不会注意到重定向的执行。只有浏览器的地址栏会表明发生了重定向。地址栏会显示与浏览器最初请求的链接不同的 URL。

虽然只有两种类型的重定向，但是可以通过多种方式实施。例如，由于用户将浏览器指向的网页包含能够将浏览器重定向到其他 URL 的脚本或特殊 HTML 代码，因此可能会发生客户端重定向。由于页面包含服务器端脚本或由于已经将 Web 服务器配置为将用户指向其他 URL，因此可能会发生服务器端重定向。

## Analytics and redirects {#concept_F9132879D0CB4AC1BE7AF45E388A47F7}

[!DNL Analytics] 会从浏览器收集一些数据，并且依赖于某些特定的浏览器属性。服务器端重定向可以更改其中两个属性：“反向链接 URL”（或“反向链接”）和“当前 URL”。由于浏览器知道请求了一个 URL，但是返回了其他 URL，因此它会清除反向链接 URL。结果，反向链接 URL 为空，[!DNL Analytics] 可能会报告页面不存在反向链接。

<!-- 

redirects_sc.xml

 -->

下列示例说明了不使用重定向和使用重定向会如何影响浏览：

* [示例：不使用重定向浏览](../../implement/js-implementation/redirects-overview.md#section_5C835A4D665A4625A23333C2C21F152D)
* [示例：使用重定向浏览](../../implement/js-implementation/redirects-overview.md#section_921DDD32932847848C4A901ACEF06248)

## 示例：不使用重定向浏览 {#section_5C835A4D665A4625A23333C2C21F152D}

考虑下列假设的情景，其中用户不会遇到重定向：

1. 用户将其浏览器指向 `www.google.com`**，然后在搜索字段输入“discount airline tickets”并单击[!UICONTROL 搜索]按钮。**
1. 浏览器显示搜索结果，其中包括到您网站的链接 [!DNL https://www.flywithus.com/]。After displaying the search results, the browser's address bar displays the search terms that the user entered in the search field ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`). 请注意，搜索词包括在 `https://www.google.com/search?` ? 后面的 URL 查询字符串参数中。
1. 用户可单击到您的假设网站的链接[!DNL https://www.flywithus.com/] 。When the user clicks this link and lands on the [!DNL flywithus.com] website, [!DNL Analytics] uses JavaScript to collect the referring URL ( `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`) as well as the current URL ( `https://www.flywithus.com/`).
1. [!DNL Analytics] 在各种报告中报告在各种报告中收集的信息，例如 [!UICONTROL “引用域名]”、 [!UICONTROL “搜索引擎”]和 [!DNL Search Keywords]“搜索引擎”。

## 示例：使用重定向浏览 {#section_921DDD32932847848C4A901ACEF06248}

重定向可能会导致浏览器清除真正的反向链接 URL。请考虑下列情景︰

1. User points his or her browser to `https://www.google.com`, and types, *discount airline tickets* into the search field, and then clicks the **[!UICONTROL Search]** button.
1. The browser window's address bar displays the search terms that the user typed into the search field `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets`. 请注意，搜索词包括在 `https://www.google.com/search?` ? 后面的 URL 查询字符串参数中。浏览器还会显示包含搜索结果的页面，其中包括到您的一个域名的链接：[!DNL https://www.flytohawaiiforfree.com/]。此&#x200B;*虚构的*&#x200B;域已配置为将用户重定向到`https://www.flywithus.com/` 。
1. The user clicks on the link `https://www.flytohawaiiforfree.com/` and is redirected by the server to your main site, `https://www.flywithus.com`. 在发生重定向后，由于浏览器清除了反向链接 URL，因此对 [!DNL Analytics] 数据收集极其重要的数据将丢失。所以，在 [!DNL Analytics] 报表中使用的原始搜索信息（例如[!UICONTROL 反向链接域名]、[!UICONTROL 搜索引擎]、[!UICONTROL 搜索关键词]）将丢失。

[实施重定向](../../implement/js-implementation/redirects-overview.md#concept_5EC2EE9677A44CC5B90A38ECF28152E7)讨论了如何利用 [!DNL Analytics] 变量捕获重定向中丢失的数据。该部分特别讨论了如何修复上述“discount airline tickets”情况。

## Implement redirects {#concept_5EC2EE9677A44CC5B90A38ECF28152E7}

若要通过重定向捕获 [!DNL Analytics][!DNL AppMeasurement] 数据，需要对创建重定向和 JavaScript 文件的代码做出四个较小的修改。

<!-- 

redirects_implement.xml

 -->

Completing the following steps will retain the information that the original referrer (for example, `https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets` in the scenario above) passes to your site:

## Configure referrer override JavaScript code {#section_87BB1D47D9C345C18339078824645CC4}

<!-- 

redirects_js_override.xml

 -->

The code snippet below shows two JavaScript variables, *`s_referrer`* and *`s_pageURL`*. 此代码位于重定向的最终登陆页面上。

```js
<script language="JavaScript" src="//INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="" 
s.pageURL=""
```

>[!IMPORTANT]
>
>Set *`s.referrer`* only once on the page. 如果在跟踪的每个跟踪调用或每个链接单击中设置一次以上，则会导致重复计算反向链接或相关维度，例如搜索引擎和关键词。

## 使用 getQueryParam 重定向 {#section_EE924E399F7A431C8FC8E8A2BEF84DEC}

虽然 [!UICONTROL getQueryParam] 能够简便地用查询字符串值填充 [!DNL Analytics] 变量，但是必须结合临时变量来实施，以便在查询字符串为空时不会覆盖合法的反向链接。使用 [!UICONTROL getQueryParam] 时，最好的方法就是像下面的伪代码一样，与 [!UICONTROL getValue] 插件结合。

```js
// AppMeasurement 1.x 
var tempVar=s.Util.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

```js
// H Code 
var tempVar=s.getQueryParam('origref') 
if(tempVar) 
  s.referrer=tempVar;
```

## Modify the redirect mechanism {#section_2FF9921E8FCA4440B6FF90F15386E548}

<!-- 

redirects_modify_mechanism.xml

 -->

由于浏览器会剥离反向链接 URL，因此您必须配置处理重定向的机制（例如 Web 服务器、服务器端代码和客户端代码）以便传递原始反向链接信息。如果您还希望记录别名链接 URL，也必须将该信息传递到最终登陆页面。请使用&#x200B;*`s_pageURL`* 变量覆盖当前 URL。

由于存在多种实施重定向的方式，因此您应该咨询网络运营团队或在线广告合作伙伴来确定在您的网站上执行重定向的具体机制。

## Capture the original referrer {#section_7F1A77F447CF485385B456A64B174050}

<!-- 

redirects_referrer.xml

 -->

[!DNL Analytics] 通常会从浏览器的 [!UICONTROL document.referrer] 属性获得反向链接 URL，并从 [!UICONTROL document.location] 属性获得当前 URL。By passing values to the *`referrer`* and *`pageURL`* variables, you can override the default processing. 通过将值传递给 referrer 变量，告诉 [!DNL Analytics] 忽略 [!UICONTROL document.referrer] 属性中的反向链接信息，并使用您定义的替代值。

因此，登陆页面的最终版本需要包含下列代码以更正在“discount airline tickets”方案中介绍的问题。

```js
<script language="JavaScript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"></script> 
<script language="JavaScript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.campaign="" 
s.referrer="https://www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets" 
// Setting the s.pageURL variable is optional. 
s.pageURL="https://www.flytohawaiiforfree.com"
```

## Verify the referrer with the Adobe Debugger {#section_B3E85941982E4E1698B271375AD669B9}

<!-- 

redirects_verify_referrer.xml

 -->

Run a test to verify that the referrer, originating URL ( *`s_server`*) and campaign variables are being captured.

These variables will be represented as the following parameters in the [Experience Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/experience-cloud-debugger/).

<table id="table_5F3B987D4D514CA283F7B9F52EBC2301"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> <b>URL 或查询字符串值</b> </th> 
   <th class="entry"> <b>DigitalPulse Debugger 中所示的值</b> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>原始反向链接 </p> </td> 
   <td> <p> <span class="filepath"> Searchl%3den%26iTTF826q%3折扣%2Bairline%2Bhor%2Bhor </span> </p> </td> 
   <td> <p> <span class="filepath"> r= Socies-8&amp; q=折扣+航空公司+机票 </span> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>页面 URL </p> </td> 
   <td> <p> <span class="filepath"> https://www.flytohawaiiforfree.com </span> </p> </td> 
   <td> <p> <span class="filepath"> g=https://www.flytohawaiiforfree.com </span> </p> <p>This value will appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>最终登陆页面 URL </p> </td> 
   <td> <p> <span class="filepath"> https://www.flywithus.com </span> </p> </td> 
   <td> <p>This value will NOT appear in the DigitalPulse Debugger if the <span class="varname"> pageURL </span> variable is used. </p> </td> 
  </tr> 
 </tbody> 
</table>

调试器显示的文本应该与以下示例对应：

```
Image 
 
https://flywithuscom.112.2o7.net/b/ss/flywithuscom/1/JS-1.4/s61944015791667?[AQB] 
ndh=1 
t=4/8/2014 13:34:28 4 360 
pageName=Welcome to FlyWithUs.com 
r=https://ref=www.google.com/search?hl=en&ie=UTF-8&q=discount+airline+tickets 
cc=USD 
g=https://www.flytohawaiiforfree.com 
s=1280x1024 
c=32 
j=1.3 
v=Y 
k=Y 
bw=1029 
bh=716 
ct=lan 
hp=N 
[AQE]
```

After verifying that the Adobe [!UICONTROL Debugger] displays these variables, it is always helpful to confirm that the search terms and the original referring domain (prior to the redirect) are registering traffic in reports.
