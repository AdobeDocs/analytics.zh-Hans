---
description: 在粒度级别自定义用户访问权限，包括 eVar、流量报表、解决方案报表和路径报表。
keywords: 用户组；权限
seo-description: 在粒度级别自定义用户访问权限，包括 eVar、流量报表、解决方案报表和路径报表。
seo-title: 自定义维度权限
solution: Analytics
subtopic: 用户和用户组
title: 自定义维度权限
topic: 管理工具
uuid: aafa164ad-3863-4129-864e-39ec71c6a8eb
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# 自定义维度权限

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe 会通知您何时迁移用户。After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

在粒度级别自定义用户访问权限，包括 eVar、流量报表、解决方案报表和路径报表。

**[!UICONTROL “用户管理”]** &gt; **[!UICONTROL “组]** ”&gt; **[!UICONTROL “报告访问权限]** ”&gt; **[!UICONTROL “维度]** ”&gt; **[!UICONTROL “自定义”]**

>[!IMPORTANT]
>
>此时某些维度不可授予权限。这些维度包括：移动书签长度；移动设备编号；移动 DRM；移动信息服务；移动 Java 虚拟机；移动邮件装饰；移动网络协议；移动操作系统；移动一键通。
>
>无论其他权限如何，这些维度可供所有用户使用。

此页面上的设置与“[!UICONTROL 定义用户群组]”页面上选择的报表包有关。

![](assets/permissions-dimensions.png)

了解以下有关权限所属维度类别的信息。

* eVar 1 至 250 是单独授权的。
* 所有流量报表都属于维度类别。
* 视频和移动报告是维度以及其他Analytics解决方案报告(Experience Manager、Advertising Cloud、Social和on on.)
* 如果用户拥有父维度的访问权限，则路径报表将可用。
* 自定义群组内的所有当前维度和量度均已自动迁移到新类别。如果现有的群组启用了量度，则默认情况下将为其提供所有新增的许可维度（eVar 和内容识别）和量度。
* 分类导入器（前身为 SAINT）权限：分类的访问权限取决于对此分类所依据的[变量](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html)的访问权限。

有关详细信息，请参阅[关于权限更改的常见问题](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html)。

**自定义维度**

以下各项是您可以授予访问权限的维度。

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../admin/admin/conversion-var-admin/conversion-var-admin.md#concept_C02F7AA01DE242F1AA1A4E74022BE9DE" format="dita" scope="local"> eVar </a> </p> </td> 
   <td colname="col2"> <p>eVar 1 至 250 是单独授权的。eVar 是自定义转化变量，可用来对自定义报表中的转化成功量度进行分段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external"> Prop </a> </p> </td> 
   <td colname="col2"> <p>Prop 是自定义流量变量。 </p> <p>请参阅 Analytics 实施中的<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">流量 prop 和转化 eVar</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html" format="html" scope="external"> 层级 </a> </p> </td> 
   <td colname="col2"> <p> 层级 (hierN) 变量确定页面在网站层级或页面结构中的位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html" format="html" scope="external"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> 与“列表属性”的功能类似，“列表变量”允许在同一图像请求中包含多个值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标准 </p> </td> 
   <td colname="col2"> <p>指 Analytics 中的标准(现成) Analytics中的维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/" format="https" scope="external"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/" format="https" scope="external"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/" format="https" scope="external"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Activity Map 报表维度：Activity Map 页面；Activity Map 链接；Activity Map 地区；按地区划分的 Activity Map 链接；Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>此合作伙伴集成已经失效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html" format="html" scope="external"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>合作伙伴集成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 社交 </p> </td> 
   <td colname="col2"> <p>未使用。 </p> </td> 
  </tr> 
 </tbody> 
</table>

