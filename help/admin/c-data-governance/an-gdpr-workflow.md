---
description: 'null'
seo-description: 'null'
seo-title: Adobe Analytics数据隐私工作流程
title: Adobe Analytics数据隐私工作流程
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 3276298eed17827c92162dd09856bed3f22de468

---


# Adobe Analytics数据隐私工作流程

欢迎使用Adobe Analytics和数据隐私准备！ 此工作流程概述了您需要采取哪些步骤来准备Adobe Analytics实施，以支持数据主体的数据隐私访问和删除权限。

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> 任务描述 </th> 
   <th colname="col3" class="entry"> 说明和更多信息的链接 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> 确保可能包含数据隐私相关数据的任何报表包均映射到您的Experience Cloud（或IMS）组织。 </p> <p>数据隐私请求是使用Experience cloud组织提交的，并将应用于该组织声明的所有报表包。 请求将不会应用于未映射到该组织的报表包，即使它们属于您的登录公司也是如此。 </p> </td> 
   <td colname="col3"> <p>请参阅<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">将报表包映射到组织</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/>设置您的数据保留策略。 </p> </td> 
   <td colname="col3"> <p>Adobe需要制定数据保留策略，才能为数据隐私数据访问／删除请求提供服务。 </p> <p>有关更多信息，请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Analytics 数据保留常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> 熟悉DULE/数据隐私标签、Adobe Analytics ID、命名空间和ID扩展。 </p> </td> 
   <td colname="col3"> <p> 请阅读本文档集中的以下主题： 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><!--<a href="/help/admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables</a>--> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">列表项 </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>--> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" />向报表包中的每个变量分配身份、敏感性和数据管理标签。 </p> <p>注意：请记住，每次创建新报表包后或在现有报表包中启用新变量时，都需要对标签设置进行审核。当启用新的解决方案集成时，您可能也需要审核标签设置，因为这些集成将出现要求设置标签的新变量。重新实施您的移动应用程序或网站时，可能会改变现有变量的使用方式，这或许也需要更新标签。 </p> </td> 
   <td colname="col3"> <p> 请按照 <!--<a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>-->. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> 连接到Adobe数据隐私API并提交访问和删除请求。 </p> </td> 
   <td colname="col3"> <p>As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Adobe Experience Cloud Data Privacy API</a>. </p> <p>You can submit any Analytics identifiers (as described in the section <!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>-->) in the requests along with their respective namespace IDs (data source IDs). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> 查看和管理报表包的数据隐私设置。 </p> </td> 
   <td colname="col3"> <p>请按照 <!--<a href="/help/admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>-->. </p> </td> 
  </tr> 
 </tbody> 
</table>

| 任务描述 | 说明和更多信息的链接 |
|--- |--- |
| **第1步**: 确保可能包含数据隐私相关数据的任何报表包均映射到您的Experience Cloud（或IMS）组织。  数据隐私请求是使用Experience cloud组织提交的，并将应用于该组织声明的所有报表包。 请求将不会应用于未映射到该组织的报表包，即使它们属于您的登录公司也是如此。 | Refer to [Map report suites to an organization.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **第2步**&#x200B;设置数据保留策略。 | Adobe需要制定数据保留策略，才能为数据隐私数据访问／删除请求提供服务。  For more information, see this [Analytics Data Retention FAQ.](/help/technotes/data-retention.md) |
| **第3步**: 熟悉DULE/数据隐私标签、Adobe Analytics ID、命名空间和ID扩展。 | 请阅读本文档集中的以下主题：<ul><li>[分析变量的数据隐私标签](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[标签设置最佳实践](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **第4步**:为报表包中的每个变量分配标识、敏感性和数据管理标签。  注意：请记住，每次创建新报表包后或在现有报表包中启用新变量时，都需要对标签设置进行审核。当启用新的解决方案集成时，您可能也需要审核标签设置，因为这些集成将出现要求设置标签的新变量。重新实施您的移动应用程序或网站时，可能会改变现有变量的使用方式，这或许也需要更新标签。 | 按照“标签报告包数 [据”中的说明操作。](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) |
| **第5步**: 连接到Adobe数据隐私API并提交访问和删除请求。 | As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API.](https://www.adobe.io/apis/experienceplatform/gdpr.html)您可以在请求中提交任何 Analytics 标识符（如[标签设置最佳实践](/help/admin/c-data-governance/gdpr-analytics-ids.md)一节中所述）及其各自的命名空间 ID（数据源 ID）。 |
| **第6步**:查看和管理报表包的数据隐私设置。 | 按照查看报 [告包的“数据管理设置”中的说明操作。](/help/admin/c-data-governance/gdpr-view-settings.md) |
