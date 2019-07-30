---
description: 允许您使用受众库、Target和Audience Manager中的营销活动区段。
seo-description: 允许您使用受众库、Target和Audience Manager中的营销活动区段。
seo-title: 将区段发布到Experience Cloud
solution: Analytics
title: 将区段发布到Experience Cloud
topic: 区段
uuid: e5ce20c0-ce43-423b-a29 f-ba66 e9 e24 d27
translation-type: tm+mt
source-git-commit: 6298c00cf4c74a493b6ba6266763d693897d5299

---


# 将区段发布到Experience Cloud

>[!IMPORTANT]
>
>尚未向所有客户推出关于区段发布和此页面上描述的用户界面的滞后时间改进。The current production environment is described [here](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. 近期更新极大地优化了出版工作流程。以前，发布可用的区段大约需要48小时。

现在，处理最多可能需要小时，但根据其他流量和区段大小，处理可能会更快。(但是，当区段可用时，我们目前无法通知您，因此您必须手动检查。)我们还将可搜索区段的最大数量增加到75(从20)。您可以在“组件”&gt;“区段”中查看已发布的区段。


## 先决条件

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). 否则，您不能将其发布到Experience Cloud。
* Make sure you are working in a report suite that is [mapped to your Experience Cloud organization](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).
* Before you can publish segments, your Admin needs to assign the [!UICONTROL Segment Publishing] permission to a product profile in the [Admin Console](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html), and add you to the product profile.


## 注意事项

* **报告套件限制**：每个报告包最多可发布75个区段。此限制受实施。如果您已经发布了75个细分，则无法发布任何其他区段，直到您取消发布足够多的细分，从而达到75细分阈值。
* **会员资格限制**：与Analytics共享 [!DNL Experience Cloud] 的受众不能超过200万个唯一成员。
* **数据隐私**：不会根据访客的身份验证状态过滤受众。如果访客可在未验证或已验证的状态下浏览您的站点，则访客在处于未验证状态时执行的操作仍会导致访客被包含在受众中。Review [Adobe Experience Cloud privacy](https://www.adobe.com/privacy/experience-cloud.html) to understand the full privacy implications of audience sharing.
* For a discussion about the differences between segments in [!DNL Adobe Analytics] and [!DNL Audience Manager], go [here](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## 细分发布时间线

| 可用内容 | 当它可用时 | 在哪里可用 |
|---|---|---|
| 元数据数据(区段标题和定义) | 发布后立即 | [!DNL Audience Manager][!UICONTROL Experience Cloud受众库]、 [!DNL Target] |
| 具有会员资格的可使用细分 | 发布后的八小时 | Visitor Profile Viewer in [!DNL Audience Manager] |
| 特征和会员人数 | 24小时内 | [!DNL Audience Manager] |

## Publish segments in [!UICONTROL Segment Builder]

1. Navigate to [!UICONTROL Analytics &gt; Workspace &gt; Components &gt; Segments] &gt; +
1. Create a segment in the [!UICONTROL Segment Builder].
1. 为区段提供标题和描述-否则将无法保存。
1. Check [!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)].

![](assets/publish-ec.png)

| 元素 | 描述 |
|---|---|
| 已将此区段发布到 Experience Cloud（对于 `<report suite>`） | 启用此选项后，区段标题和定义(即，通常在广告平台中使用的Shell受众)会与Experience Cloud instantaneously共享，同时每个小时评估并共享区段成员资格。<br> 例如，当受众与中 [!DNL Target]的活动相关联时， [!DNL Analytics] 开始向符合Experience Cloud和 [!DNL Target] 受众资格的访客发送ID。At that point, the audience name and corresponding data begins displaying on the Experience Cloud Audiences page. </br> |
| 受众创建窗口 | 您选择的时间帧用于在滚动日历基础上创建受众。例如，“过去30天”(默认)包括符合受众资格的过去30天内的受众(不包括创建区段时的最初日期)。 |
| 在受众库中创建 | 您可以在Experience Cloud受众库中无延迟地创建和发布您创建和发布的区段。它们并不依赖于Analytics更新。这些区段不计入您的75个已发布区段的限制。 |
| x共75个已发布 | 显示已发布到Experience Cloud的区段数。单击链接可查看已发布区段及其关联的报表套件和所有者的列表。 |
| 保存 | 保存此区段。 |

## 取消发布或删除区段

要删除已发布到Experience Cloud的区段，必须先取消发布该区段。To unpublish a segment, just **unclick** the checkbox that you used to publish it.

>[!NOTE]
>
>You **cannot** unpublish a segment that is currently in use by any of the following Adobe solutions: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (for [!DNL Core Service] &amp; [!DNL Audience Manager] customers) and all other external partners (for [!DNL Audience Manager] customers). **您可以** 取消发布正在使用的区段 [!DNL Target]。

## View segment publishing status in the [!UICONTROL Segment Manager]

1. Navigate to [!UICONTROL Analytics &gt; Components &gt; Segments].
1. Notice the new [!UICONTROL Published] column. 是/否指区段是否已发布到Experience Cloud。

![](assets/publish-status.png)

## Retrieve the [!DNL Audience Manager] UUID

有种方法可捕获当前与浏览器关联的AAM UUID：

* Adobe Experience Cloud 调试器
* 浏览器中的本机开发人员工具(例如Chrome开发人员工具)

以下屏幕截图显示如何在浏览器中检索AAM UUID并将其用于Audience Manager访问者个人资料查看器，以验证特征和区段成员资格。

**方法1：使用Adobe Experience Cloud调试器**

1. Download and install [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) in the Chrome Web Store.
1. 加载页面时启动调试器。
1. Scroll to the Audience Manager section and find the AAM UUID set on the current browser page
(`50814298273775797762943354787774730612` in the example below)

![](assets/debugger.jpg)

**方法2：使用Chrome开发人员工具(或其他浏览器开发人员工具)**

1. 加载页面前启动Chrome开发人员工具
1. 加载页面并检查应用程序&gt; Cookies。The AAM UUID should be set in the 3rd-party
Demdex cookie ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) in the example below). The field demdex is the AAM UUID set
on the browser (`50814298273775797762943354787774730612` in the example below).

![Chrome 开发人员工具](assets/ggogle-uuid.png)

## Use Audience Manager [!UICONTROL Visitor Profile Viewer]

The AAM UUID on the browser will be used by default when [!UICONTROL Visitor Profile Viewer] is loaded. If verifying trait realizations for other users, input a UUID in the UUID field and click [!UICONTROL Refresh]. Refer to [Visitor Profile Viewer](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) for more information.

![](assets/aam-vpv.png)

## View the segment traits in [!DNL Audience Manager]

在AAM中，当Analytics与Experience Cloud共享区段时，将以流方式评估具有给定区段电子ID的访客列表。

1. In [!DNL Audience Manager], go to [!UICONTROL Audience Data &gt; Traits &gt; Analytics Traits]. 您将看到映射到Experience Cloud组织的每个Analytics报告套件的文件夹。这些文件夹(针对特征、区段和数据源)在配置文件和受众/人员核心服务被启动或配置时创建。
1. Select the folder for the report suite in which you previously created the segment you wanted to share with [!DNL Audience Manager]. 您将看到您创建的区段/受众。When you share a segment, 2 things happen in [!DNL Audience Manager]:
* 创建特征，在其中无数据。批准。8 hours after the segment gets published in [!DNL Analytics], the list of ECIDs gets onboarded and shared with [!DNL Audience Manager] and other Experience Cloud solutions.

![](assets/aam-traits.png)

* 创建一个特征区段。它使用与发布区段的报表包关联的数据源。

## View the segment in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. 在 Analytics 或 Audience Manager 中创建的区段可用于 Target 中的活动。例如，你可以根据 Analytics 转化量度和 Analytics 中创建的受众区段，来创建营销活动。], click [!UICONTROL Audiences].
1. On the [!UICONTROL Audiences] page, locate the audience sourced from the [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.
