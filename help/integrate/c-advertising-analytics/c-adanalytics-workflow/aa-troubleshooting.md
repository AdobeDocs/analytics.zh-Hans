---
description: 排除和修复与 Advertising Analytics 相关的问题。
title: Advertising Analytics 疑难解答
feature: Advertising Analytics
exl-id: 29e39a15-504a-4155-8794-aceb47046a54
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 50%

---

# Advertising Analytics 疑难解答

* [我在“映射”部分中看不到我的报表包](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_9CAACDE6445C492DBAE542BA74DE6316)
* [我在对 Google AdWords 帐户进行身份验证时遇到错误...](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md#section_C99EA9A1946E4908B36778A331142B84)

## 我在“映射”部分中看不到我的报表包 {#section_9CAACDE6445C492DBAE542BA74DE6316}

您正在尝试 [设置新的Advertising帐户](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md) 并且您的报表包未在 **[!UICONTROL 已映射的报表包]** 下拉列表。 出现此问题的原因可能有两个：

<table id="table_271D7E817B4C44818717A47C3223E592"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 原因 </th> 
   <th colname="col2" class="entry"> 解决方案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1.报表包未映射到登录用户的Experience Cloud组织ID。 </p> </td> 
   <td colname="col2"> <p>联系客户关怀团队以将报表包映射到组织ID。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2.未为Advertising Analytics报表配置报表包。 </p> </td> 
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
