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

>[!IMPORTANT]用户和产品管理即将转移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html) 中。Adobe 会通知您何时迁移用户。在迁移完所有客户之后，将撤销 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员工具]** > **[!UICONTROL 用户管理]**&#x200B;中的帮助内容。

在粒度级别自定义用户访问权限，包括 eVar、流量报表、解决方案报表和路径报表。

**[!UICONTROL 用户管理]** > **[!UICONTROL 群组]** > **[!UICONTROL 报表访问]** > **[!UICONTROL 维度]** > **[!UICONTROL 自定义]**

>[!IMPORTANT] 某些维度当前不是许可维度。这些维度包括：移动书签长度；移动设备编号；移动 DRM；移动信息服务；移动 Java 虚拟机；移动邮件装饰；移动网络协议；移动操作系统；移动一键通。
>
>无论其他权限如何，这些维度可供所有用户使用。

此页面上的设置与“[!UICONTROL 定义用户群组]”页面上选择的报表包有关。

![](assets/permissions-dimensions.png)

了解以下有关权限所属维度类别的信息。

* eVar 1 至 250 是单独授权的。
* 所有流量报表都属于维度类别。
* 视频和移动设备报表属于维度类别，其他 Analytics 解决方案报表（Experience Manager、Advertising Cloud、Social 等）也属于维度类别。
* 如果用户拥有父维度的访问权限，则路径报表将可用。
* 自定义群组内的所有当前维度和量度均已自动迁移到新类别。如果现有的群组启用了量度，则默认情况下将为其提供所有新增的许可维度（eVar 和内容识别）和量度。
* 分类导入器（前身为 SAINT）权限：分类的访问权限取决于对此分类所依据的[变量](https://marketing.adobe.com/resources/help/zh_CN/reference/c_classifications.html)的访问权限。

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
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVar </a> </p> </td> 
   <td colname="col2"> <p>eVar 1 至 250 是单独授权的。eVar 是自定义转化变量，可用来对自定义报表中的转化成功量度进行分段。 </p> </td> 
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
   <td colname="col2"> <p> 与“列表属性”的功能类似，“列表变量”允许在同一图像请求中包含多个值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标准 </p> </td> 
   <td colname="col2"> <p>指 Analytics 中的标准（现成）维度。 </p> </td> 
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
