---
description: 有关客户属性以及如何运行客户属性报表的 Analytics 常见问题解答。
solution: Experience Cloud,Analytics
title: 客户属性
uuid: 94721265-ba23-45d5-8807-76f81b0b8a30
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 客户属性

有关客户属性以及如何运行客户属性报表的 Analytics 常见问题解答。

**[!UICONTROL Reports]** **[!UICONTROL > Visitor Profile]** > **[!UICONTROL Customer Attributes]**

如果您在客户关系管理 (CRM) 数据库中捕获到企业客户数据，则可以将该数据上传到 Experience Cloud 中的客户属性数据源。上载数据之后，即可在 Reports &amp; Analytics 中运行“客户属性”报表。

* [Analytics 中的客户属性和报表量度](/help/components/c-variables/dimensionslist/reports-customer-attributes.md#section_EF343662146B460A882D3DF772ADD86D)
* [常见问题解答 - Analytics 中的客户属性](/help/components/c-variables/dimensionslist/reports-customer-attributes.md#section_E29641D1F3D649C1AC9EA5231921F038)

请参阅 Experience Cloud 帮助中的[客户属性](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/customer-attributes/attributes.html)，以了解有关上载客户属性数据的信息。

## Analytics 中的客户属性和报表量度 {#section_EF343662146B460A882D3DF772ADD86D}

在您上传客户属性并（在 Experience Cloud 中）验证架构后，系统会根据映射到属性字符串和整数的友好名称（例如 *`age`* 或 *`gender`*）创建量度。这些指标显示在 **[!UICONTROL Visitor Profile]** >报 **[!UICONTROL Customer Attributes]** 告中。

例如：

**[!UICONTROL Visitor Profile]** > **[!UICONTROL Customer Attributes]** > **[!UICONTROL Age]**

![](assets/report_age.png)

**示例 - 年龄量度**

如果将某个字符串指定为&#x200B;*`age`*，则系统会创建以下量度和维度：

* 年龄维度：允许您运行基于年龄属性的报表。
* 年龄量度：可添加到报表的量度，如独特访客报表。
* 年龄计数量度：可让您了解（例如）访客是否在表单中指定了 *`age`* 值。

由于量度是报表中的总和，您应当[创建一个计算量度](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/cm-overview.html)，用于表示平均年龄。此量度的公式为 `Age / Count of Age`。

## 常见问题解答 - Analytics 中的客户属性 {#section_E29641D1F3D649C1AC9EA5231921F038}

<table id="table_88631069013B408EBB0A810657662B36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>为什么说最好使用 Identity Service 来设置客户 ID，而不是在 prop 或 eVar 中填充客户 ID？ </p> </td> 
   <td colname="col2"> <p>使用 Identity Service 具有多项好处： </p> 
    <ul id="ul_5D3659604D43419F9CA5920B4F93728E"> 
     <li id="li_BA2EF0715C5A47EFAFA7191CFAD088A4">如果您未使用 Identity Service 设置客户 ID，则客户记录只可用于 Adobe Analytics。如果要使用客户记录进行实时定位，则必须使用 Identity Service。 </li> 
     <li id="li_228358684E474A298E39578D427BF932">使用 Identity Service 设置客户 ID，可减少将 ID 与 Experience Cloud 同步所花费的时间。如果在 prop 或 eVar 中放置客户 ID，则会通过批量进行的后端服务器同步将客户 ID 发送至 Experience Cloud。Identity Service 可立即将客户 ID 与 Experience Cloud 同步。 </li> 
     <li id="li_BCF28219E4014FCF9F747C3D8D270526"> 使用 Identity Service 而不是 prop 或 eVar，可腾出 prop 或 eVar 另作他用。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果我已在 prop 或 eVar 中存储了客户 ID，为什么要使用这一新功能，而不是通过 CRM 属性来分类我的 prop 或 eVar？ </p> </td> 
   <td colname="col2"> <p>prop 和 eVar 须遵循“超出的独特数”限制。使用此功能，您可以为无限数量的客户 ID 引入属性数据。另外，使用 prop/eVar 方法会限制向 Analytics 提供的 CRM 信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的 CRM 属性将如何在 Adobe Analytics 中显示？ </p> </td> 
   <td colname="col2"> <p>CRM 属性将在 Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis、报表 API 和 Report Builder 中出现。文本属性将显示为报表/维度。数值属性将同时显示为维度和量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM 数据会在 Data Warehouse 和数据馈送中提供吗？ </p> </td> 
   <td colname="col2"> <p>CRM 数据目前不会在 Data Warehouse 或 Analytics 数据馈送中提供。 </p> </td> 
  </tr> 
 </tbody> 
</table>

