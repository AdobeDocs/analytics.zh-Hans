---
description: 在粒度级别自定义用户访问权限，包括 eVar、流量报表、解决方案报表和路径报表。
keywords: groups;permissions
subtopic: Users and groups
title: 自定义维度权限
topic: Admin tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 自定义维度权限

>[!IMPORTANT]用户和产品管理即将转移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html) 中。Adobe 会通知您何时迁移用户。After all customers have migrated, help content for **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** will be retired.

在粒度级别自定义用户访问权限，包括 eVar、流量报表、解决方案报表和路径报表。

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Dimensions]** > **[!UICONTROL Customize]**

>[!IMPORTANT] 某些维度当前不是许可维度。这些维包括：移动书签长度；移动设备号；移动DRM;移动信息服务;移动Java虚拟机；移动邮件装饰；移动网络协议；移动操作系统；移动即说。
>
>这些维度适用于所有用户，而不管其他权限如何。

此页上的设置与页面上选定的报表包有关 [!UICONTROL Define User Groups] 。

![](assets/permissions-dimensions.png)

了解以下有关权限的维类别的信息。

* eVar 1-250是单独授权的。
* 所有流量报告都是维度。
* 视频和移动设备报表属于维度类别，其他 Analytics 解决方案报表（Experience Manager、Advertising Cloud、Social 等）也属于维度类别。
* 如果用户有权访问父维度，则路径报告可用。
* 自定义组中的所有当前维度和指标已自动迁移到新类别。 如果现有组启用了度量，默认情况下将为其提供所有新授权的维度（eVar和内容感知）和度量。
* 分类导入器（前身为 SAINT）权限：分类的访问权限取决于对此分类所依据的[变量](https://marketing.adobe.com/resources/help/zh_CN/reference/c_classifications.html)的访问权限。

有关详细信息，请参 [阅有关权限更改的常见问题解答](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html)。

**自定义维**

以下项目是您可以授予权限的维。

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVar </a> </p> </td> 
   <td colname="col2"> <p>eVar 1-250是单独授权的。 eVar是自定义转化变量，用于在自定义报告中细分转化成功量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_CN/sc/implement/props_eVars.html"> Prop </a> </p> </td> 
   <td colname="col2"> <p>Prop 是自定义流量变量。 </p> <p>请参阅 Analytics 实施中的<a href="https://marketing.adobe.com/resources/help/zh_CN/sc/implement/props_eVars.html">流量 prop 和转化 eVar</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_CN/sc/implement/hierN.html"> 层级 </a> </p> </td> 
   <td colname="col2"> <p> 层级 (hierN) 变量确定页面在网站层级或页面结构中的位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_CN/sc/implement/listN.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> 与列表Props的功能类似，列表变量允许同一图像请求中的多个值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标准 </p> </td> 
   <td colname="col2"> <p>指Analytics中的标准（现成）维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_CN/analytics/activitymap/"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Activity Map 报表维度：Activity Map 页面；Activity Map 链接；Activity Map 地区；按地区划分的 Activity Map 链接；Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_CN/mobile/"> 移动设备 </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>此合作伙伴集成已经失效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/zh_CN/sc/appmeasurement/hbvideo/nielsen-partnership.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>此合作伙伴集成已经失效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 社交 </p> </td> 
   <td colname="col2"> <p>未使用。 </p> </td> 
  </tr> 
 </tbody> 
</table>
