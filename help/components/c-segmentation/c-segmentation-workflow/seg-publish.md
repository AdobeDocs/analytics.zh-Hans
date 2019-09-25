---
description: Lets you use the segment for marketing activity in the Audience Library, Target, and Audience Manager.
seo-description: Lets you use the segment for marketing activity in the Audience Library, Target, and Audience Manager.
seo-title: 将区段发布到 Experience Cloud
solution: Analytics
title: 将区段发布到 Experience Cloud
topic: 区段
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: bac0b1ae330753cfc537817e8da1ea70fbaaf0d5

---


# 将区段发布到 Experience Cloud

>[!IMPORTANT]
>
>尚未针对所有客户推出本页中介绍的有关细分发布和用户界面的延迟改进。 The current production environment is described [here](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Recent updates have significantly optimized the publishing workflow. 以前，发布可用区段大约需要48小时。

现在，处理最多可能需要8小时，但根据其他流量和区段大小，处理速度可能会更快。 （但是，我们目前无法通知您区段何时可用，因此您必须手动检查。）我们还将可发布区段的最大数量从20个增加到75个。 您可以在组件&gt;区段中查看已发布的区段。


## 先决条件

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). 否则，您无法将其发布到Experience Cloud。
* 确保您使用的报表包已映射 [到您的Experience cloud组织](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)。
* 确保您的组织正在使用Experience Cloud ID。
* 在您发布区段之前，您的管理员需要先在 [!UICONTROL Admin Console中将“区段发布][](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)”权限分配给产品配置，然后再将您添加到产品配置。


## 注意事项

* **报表包限制**:每个报表包最多可发布75个区段。 此限制是强制执行的。 如果已发布75个区段，则只有在取消发布足够的区段以低于75个区段阈值时，才能发布任何其他区段。
* **会员资格限制**:从Analytics共享给 [!DNL Experience Cloud] 的受众不能超过2000万个唯一成员。
* **数据隐私**:不会根据访客的身份验证状态过滤受众。 如果访客可在未验证或已验证的状态下浏览您的站点，则访客在处于未验证状态时执行的操作仍会导致访客被包含在受众中。查 [看Adobe Experience cloud隐私](https://www.adobe.com/privacy/experience-cloud.html) ，了解受众共享对隐私的全面影响。
* 有关中和中区 **段之间差异的[!DNL Adobe Analytics]讨[!DNL Audience Manager]**&#x200B;论，请 [访问](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)。

## 区段发布时间线

| 可用功能 | 当它可用时 | 可用位置 |
|---|---|---|
| 元数据（区段标题和定义） | 发布后立即 | [!DNL Audience Manager], [!UICONTROL Experience Cloud受众库], [!DNL Target] |
| 具有会员资格的可用细分 | 发布后8小时 | 中的访客资料查看器 [!DNL Audience Manager] |
| 特征和会员人数 | 24小时内 | [!DNL Audience Manager] |

## 在区段生成器中 [!UICONTROL 发布区段]

1. 导航到 **[!UICONTROL Analytics &gt; Workspace &gt;组件&gt;区段]&gt; +**
1. 在“区段生成器”中 [!UICONTROL 创建区段]。
1. 为区段提供标题和说明——否则您将无法保存它。
1. Check **[!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)]**.
1. Make sure you use "Visitors with Experience Cloud ID" when looking at segment previews in Analytics instead of the total “unique visitors” segment preview when comparing Adobe Analytics numbers to Audience Manager numbers.

![](assets/publish-ec.png)

| 元素 | 描述 |
|---|---|
| **[!UICONTROL 将此区段发布到Experience Cloud(*<report suite>*)]** | When this option is enabled, the segment title and definition (i.e. the shell audience as often used in ad platforms) are shared with the Experience Cloud instantaneously, while the segment membership is evaluated and shared every 4 hours. <br> 例如，当该受众与某个活动关 [!DNL Target]联时，开始为符合该Experience cloud资格的 [!DNL Analytics] 访客和受众发送ID [!DNL Target] 。 At that point, the audience name and corresponding data begins displaying on the Experience Cloud Audiences page. </br> |
| **[!UICONTROL 受众创建窗口]** | The time frame you select is used to create the audience on a rolling-calendar basis. For example, “Last 30 days” (default) includes visitors that have qualified for the audience over the last 30 days from today's date (NOT from the original date when the segment was created.) |
| **[!UICONTROL 在受众库中创建]** | The segments that you create and publish can be made available without latency in the Experience Cloud Audience Library. They are not dependent on Analytics updates. These segments do not count against your limit of 75 published segments. |
| **[!UICONTROL x of 75 Published]** | Shows the number of segments you have published to the Experience Cloud. 单击该链接可查看已发布区段及其关联的报表包和所有者的列表。 |
| **[!UICONTROL 保存]** | Saves this segment. |

## Unpublish or delete segments

要删除已发布到 Experience Cloud 的区段，必须先取消发布该区段。要取消发布区段，只需&#x200B;**取消选中**&#x200B;用于发布该区段的复选框。

>[!NOTE]
>
>您&#x200B;**无法**&#x200B;取消发布以下任何一个 Adobe 解决方案当前正在使用的区段：[!DNL Analytics]（位于 [!DNL Audience Analytics] 中）、[!DNL Campaign]、[!DNL Advertising Cloud]（适用于 [!DNL Core Service] 和 [!DNL Audience Manager] 客户）和所有其他外部合作伙伴（适用于 [!DNL Audience Manager] 客户）。您&#x200B;**可以**&#x200B;取消发布 [!DNL Target] 正在使用的区段。

## View segment publishing status in the Segment Manager

1. Navigate to Analytics &gt; Components &gt; Segments.
1. Notice the new Published column. Yes/No refers to whether the segment has been published to the Experience Cloud or not.

![](assets/publish-status.png)

## 检索 [!DNL Audience Manager] UUID

有两种方法可捕获当前与浏览器关联的AAM UUID:

* Adobe Experience Cloud 调试器
* 浏览器中的本机开发人员工具（例如Chrome开发人员工具）

以下屏幕截图显示如何在浏览器上检索AAM UUID，并在Audience Manager访客资料查看器中使用它来验证特征和区段成员资格。

**方法1:使用Adobe Experience Cloud Debugger**

1. 在Chrome Web Store中下 [载和安装Adobe Experience Cloud](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) Debugger。
1. 在加载页面时启动调试器。
1. 滚动到Audience Manager部分，在当前浏览器页面（在以下示例中）上查找`50814298273775797762943354787774730612` AAM UUID集

![](assets/debugger.jpg)

**方法2:使用Chrome开发人员工具（或其他浏览器开发人员工具）**

1. 在加载页面之前启动Chrome开发人员工具
1. 加载页面并选中“应用程序”&gt;“Cookie”。 AAM UUID应在第三方Demdex cookie(以下示例中的[adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) )中设置。 字段demdex是浏览器中的AAM UUID选项(`50814298273775797762943354787774730612` 在以下示例中)。

![Chrome 开发人员工具](assets/ggogle-uuid.png)

## 使用Audience Manager访客 [!UICONTROL 资料查看器]

默认情况下，在加载访客配置文件查看器时，将使 [!UICONTROL 用浏览器上的AAM] UUID。 如果验证其他用户的特征实现，请在UUID字段中输入UUID，然后单击“刷 [!UICONTROL 新”]。 有关详细 [信息，请参阅访客资料查看器](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) 。

![](assets/aam-vpv.png)

## 查看 [!DNL Audience Manager]

在AAM中，当Analytics与Experience cloud共享区段时，将以流式方式评估特定区段的ECID访客列表。

1. 在中， [!DNL Audience Manager]转到“受 [!UICONTROL 众数据”&gt;“特征”&gt;“分析特征”]。 您将看到每个Analytics报表包的一个文件夹，该文件夹已映射到您的Experience cloud组织。 在启动或配置Profiles和Audiences/People核心服务时，将创建这些文件夹（针对特征、区段和数据源）。
1. 选择您之前在其中创建了要共享的区段的报表包的文件夹 [!DNL Audience Manager]。 您将看到您创建的区段／受众。 当您共享区段时，会发生以下两种情况 [!DNL Audience Manager]:
* A trait gets created, first with no data in it. 约 在区段发布8小时后，ECID [!DNL Analytics]列表即会载入并与其他Experience cloud解决方 [!DNL Audience Manager] 案共享。

![](assets/aam-traits.png)

* 创建单特征段。 它使用与您发布区段的报表包关联的数据源。

## View the segment in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. 在 Analytics 或 Audience Manager 中创建的区段可用于 Target 中的活动。例如，你可以根据 Analytics 转化量度和 Analytics 中创建的受众区段，来创建营销活动。], click Audiences.
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.

