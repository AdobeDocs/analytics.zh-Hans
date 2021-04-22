---
description: 排除和修复与 Advertising Analytics 相关的问题。
title: Advertising Analytics 疑难解答
uuid: d0abe7cc-ed13-4d3d-87a6-f0d649c7ad2d
exl-id: 29e39a15-504a-4155-8794-aceb47046a54
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '178'
ht-degree: 100%

---

# Advertising Analytics 疑难解答

* [我在“映射”部分中看不到我的报表包](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_9CAACDE6445C492DBAE542BA74DE6316)
* [我在对 Google AdWords 帐户进行身份验证时遇到错误...](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_C99EA9A1946E4908B36778A331142B84)

## 我在“映射”部分中没有看到我的报表包 {#section_9CAACDE6445C492DBAE542BA74DE6316}

您正在尝试[设置一个新的广告帐户](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)，并且在&#x200B;**[!UICONTROL 选择报表包]**&#x200B;下拉列表中列出的报表包中，没有看到您的报表包。出现此问题的原因可能有两个：

<table id="table_271D7E817B4C44818717A47C3223E592"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 原因 </th> 
   <th colname="col2" class="entry"> 解决方案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1. 未将报表包映射到登录用户的 Experience Cloud 组织 ID。 </p> </td> 
   <td colname="col2"> <p>有关说明，请参阅<a href="https://docs.adobe.com/content/help/zh-Hans/core-services/interface/about-core-services/report-suite-mapping.html"  >将报表包映射到组织</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2. 报表包没有配置为可以使用 Advertising Analytics 报告功能。 </p> </td> 
   <td colname="col2"> <p>有关说明，请参阅<a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  >配置报表包</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 我在对 Google AdWords 帐户进行身份验证时遇到错误 {#section_C99EA9A1946E4908B36778A331142B84}

<table id="table_F1C1192BF40C43CE8600B1BB417A7269"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 原因 </th> 
   <th colname="col2" class="entry"> 解决方案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>使用电子邮件帐户对 Google AdWords 进行身份验证时，如果该电子邮件帐户还关联到 AdWords Manager 帐户，则身份验证无法奏效。 </p> </td> 
   <td colname="col2"> <p>请使用另一个关联到该相同 AdWords 帐户的电子邮件进行身份验证。 </p> </td> 
  </tr> 
 </tbody> 
</table>
