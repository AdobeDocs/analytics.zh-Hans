---
description: 允许您将区段用于“受众库”、Target 和 Audience Manager 中的营销活动。
title: 将区段发布到Experience Cloud
feature: Segmentation
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '1363'
ht-degree: 58%

---

# 发布区段 {#publish-segments}

>[!CONTEXTUALHELP]
>id="components_segments_publishing"
>title="Experience Cloud 发布"
>abstract="您可以将从此区段派生的受众发布到受众库，从受众库就可以将此受众用于 Target 和其他 Experience Cloud 解决方案中的营销活动。"

>[!CONTEXTUALHELP]
>id="components_segments_audiencelibrary"
>title="受众库"
>abstract="在受众库中创建的区段立即可用，不受 Analytics 更新的影响。"


您可以将Adobe Analytics区段发布到Experience Cloud，以便可以将该区段用于[!DNL Audience Manager]和其他激活渠道中的营销活动，包括Adobe的[!DNL Advertising Cloud]、[!DNL Target]和[!DNL Campaign]。

您可以在8小时内将Analytics区段发布到Experience Cloud。 使用这些区段将 Audience Manager 中的受众激活到所有下游目标。


>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [发布区段](https://video.tv.adobe.com/v/36689?quality=12&learn=on&captions=chi_hans){target="_blank"}。

>[!ENDSHADEBOX]


>[!NOTE]
>
>Adobe Campaign（Classic 和 Standard）的行为方式不同，因为它在 8 小时延迟的基础之上会额外产生 24 小时的延迟。

## 先决条件

* 请确保要保存此区段的报表包已[启用Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-publish-audience-segment.html?lang=zh-Hans)。 否则，您无法将其发布到Experience Cloud。
* 确保您的组织使用的是 Experience Cloud ID。
* 在发布区段之前，您的管理员需要先在[管理控制台](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=zh-Hans)中向产品配置文件分配“[!UICONTROL 区段发布]”权限，并将您添加到产品配置文件中。

## 注意事项

* **报告包限制**：每个报告包最多可发布 75 个区段。此限制是强制实施的。如果已发布 75 个区段，则只有在取消发布足够数量的区段，使区段数量低于 75 个区段的阈值后，才能发布任何其他区段。
* **会员资格限制**：从 Adobe Analytics 共享到 [!DNL Experience Cloud] 的受众数量不能超过 2000 万个独特会员。
* **数据隐私**：受众并非基于访客的身份验证状态进行过滤。如果访客可在未验证或已验证的状态下浏览您的站点，则访客在处于未验证状态时执行的操作仍会导致访客被包含在受众中。请查看 [Adobe Experience Cloud 隐私](https://www.adobe.com/cn/privacy/experience-cloud.html)，了解受众共享对隐私的全面影响。
* 有关[!DNL Adobe Analytics]和&#x200B;[!DNL Audience Manager]&#x200B;**中区段之间的**&#x200B;差异的讨论，请参阅[了解Analytics和Audience Manager中的区段](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=zh-Hans)。

## 区段发布时间轴

| 可用内容 | 可用时间 | 可用位置 |
|---|---|---|
| 元数据（区段标题和定义） | 发布后立即 | [!DNL Audience Manager]、[!UICONTROL Experience Cloud 受众库]、[!DNL Target] |
| 具有会员资格的可用区段 | 发布后约 8 小时 | [!DNL Audience Manager] 中的访客轮廓查看器 |
| 特性和会员人群 | 24 - 48 小时内 | [!DNL Audience Manager] |

>[!NOTE]
>每周一次，所有数据都将完全同步，以考虑上周未捕获的任何增量或差异。

## 在[!UICONTROL 区段生成器]中发布区段

1. 在Adobe Analytics中，转到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 区段]**
1. 选择&#x200B;**[!UICONTROL 添加]**&#x200B;以创建新区段。
   ![发布 Experience Cloud](assets/publish-ec.png)
1. 提供区段的标题和描述。 在保存区段之前，需要填写这些字段。
1. 在&#x200B;**[!UICONTROL Experience Cloud发布]**&#x200B;部分中，选择选项&#x200B;**[!UICONTROL 将此区段发布到Experience Cloud（对于&#x200B;*报表包*）]**。

   >[!IMPORTANT]
   >
   >将Experience Cloud数字与Audience Manager数字进行比较时，请确保在&#x200B;**[!UICONTROL 数据预览]**&#x200B;中监视&#x200B;**[!UICONTROL 具有Adobe Analytics ID]**&#x200B;的访客，而不是&#x200B;**[!UICONTROL 独特访客]**。
   >

| 元素 | 描述 |
|---|---|
| **[!UICONTROL 将此区段发布到Experience Cloud（对于&#x200B;*报表包*）]** | 启用此选项后，区段标题和定义（即广告平台中经常使用的Shell受众）会立即与Experience Cloud共享，而区段会员资格则每4小时进行一次评估和共享。 <br>例如，当该受众与 [!DNL Target] 中的某个活动关联时，[!DNL Analytics] 将开始发送具有 Experience Cloud 和 [!DNL Target] 受众资格的访客的 ID。此时，受众名称和相应的数据开始显示在Experience Cloud的[!DNL Audience Library]页面中。</br> |
| **[!UICONTROL 受众创建窗口]** | 您选择用于在滚动日历基础上创建受众的时间范围。例如，**[!UICONTROL 最近30天]**（默认）包括从今天日期（不是创建区段的原始日期）起，最近30天中符合受众条件的访客。 |
| **[!UICONTROL 在受众库中创建]** | 您创建和发布的区段可在Experience Cloud的[!DNL Audience Library]页面上无延迟地提供。 它们不依赖于 Analytics 更新。这些区段不会计入 75 个已发布区段的限制。 |
| **[!UICONTROL 已发布 x 个（限制为 75 个）]** | 显示您已发布到Experience Cloud的区段数。 单击该链接可查看已发布的区段，及其关联的报告包和所有者的列表。 |
| **[!UICONTROL 保存]** | 保存此区段。 |

## 取消发布或删除区段

>[!CAUTION]
>
>要删除已发布到Experience Cloud的区段，必须先取消发布该区段。 要取消发布区段，只需取消选择&#x200B;**[!UICONTROL 将此区段发布到Experience Cloud（对于&#x200B;*报表包*）]**。


>[!NOTE]
>
>您&#x200B;**无法**&#x200B;取消发布以下任何一个 Adobe 解决方案当前正在使用的区段：[!DNL Analytics]（位于 [!DNL Audience Analytics] 中）、[!DNL Campaign]、[!DNL Advertising Cloud]（适用于 [!DNL Core Service] 和 [!DNL Audience Manager] 客户）和所有其他外部合作伙伴（适用于 [!DNL Audience Manager] 客户）。您&#x200B;**可以**&#x200B;取消发布 [!DNL Target] 正在使用的区段。

## 查看区段的发布状态

可发布的Adobe Analytics区段的最大数量为75个。

要查看已发布的区段，请执行以下操作：

1. 在Adobe Analytics中，转到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 区段]**。

1. 查看&#x200B;**[!UICONTROL 已发布]**&#x200B;列。 此列中的&#x200B;**[!UICONTROL 是]**&#x200B;表示该区段已发布到Experience Cloud。 **[!UICONTROL 否]**&#x200B;表示该区段未发布。

## 检索 [!DNL Audience Manager] UUID

有两种方法可捕获当前与浏览器关联的Adobe Audience Manager UUID：

* Adobe Experience Cloud 调试器
* 浏览器中的本机开发人员工具（例如，Chrome 开发人员工具）

以下屏幕截图显示了如何在浏览器中检索Adobe Audience Manager UUID，并在Audience Manager访客资料查看器中使用它来验证特征和区段成员资格。

### 方法 1：使用 Adobe Experience Cloud Debugger

1. 从 Chrome 网上应用店中，下载并安装 [Adobe Experience Cloud 调试器](/help/implement/validate/debugger.md)。
1. 加载页面时启动该调试器。
1. 滚动到Audience Manager部分，然后找到在当前浏览器页面上设置的Adobe Audience Manager UUID
（以下示例中的`35721780439475290181087231320657663953`）

   ![调试程序](assets/aepdebugger.png)

### 方法 2：使用 Chrome 开发人员工具（或其他浏览器开发人员工具）

1. 在加载页面之前启动 Chrome 开发人员工具
1. 加载页面，并选中“应用程序”>“Cookie”。Adobe Audience Manager UUID应在第三方中设置
Demdex Cookie （以下示例中为[adobe.demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=zh-Hans)）。 字段demdex是Adobe Audience Manager UUID集
在浏览器上（以下示例中为`35721780439475290181087231320657663953`）。

   ![Chrome 开发人员工具](assets/devtools.png)

## 使用 Audience Manager [!UICONTROL 访客轮廓查看器]

加载[!UICONTROL 访客资料查看器]时，默认情况下将使用浏览器上的Adobe Audience Manager UUID。 如果验证其他用户的特性实现，请在“UUID”字段中输入 UUID，然后单击“[!UICONTROL 刷新]”。请参阅[访客轮廓查看器](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/visitor-profile-viewer.html?lang=zh-Hans)，以了解详细信息。

## 在 [!DNL Audience Manager] 中查看区段特性

在Adobe Audience Manager中，当Analytics与Experience Cloud共享区段时，将以流式方式评估给定区段的具有ECID的访客列表。

1. 在[!DNL Audience Manager]中，转到&#x200B;**[!UICONTROL 受众数据]** > **[!UICONTROL 特征]** > **[!UICONTROL Analytics特征]**。 您将看到每个 Analytics 报告包对应的文件夹，这些报告包已映射到您的 Experience Cloud 组织。在启动或置备轮廓和受众/人员核心服务时，将创建这些文件夹（针对特性、区段和数据源）。
1. 选择报告包对应的文件夹，您之前在该报告包中创建了要与 [!DNL Audience Manager] 共享的区段。您将看到所创建的区段/受众。当您共享区段时，会在 [!DNL Audience Manager] 中发生以下两种情况：
   * 将创建一个特性，起初该特性中没有数据。在 [!DNL Analytics] 中发布该区段大约 8 小时后，会载入一个 ECID 列表，并将其与 [!DNL Audience Manager] 和其他 Experience Cloud 解决方案共享。

     ![Audience Manager 特征](assets/aam-traits.png)

   * 将创建一个区段，其中包含一个特性。该区段使用与您在其中发布该区段的报告包关联的数据源。
   * 特征有效期限现在设置为 16 天（以前为 2 天）。

## 在 [!DNL Adobe Target] 中查看区段

在 Adobe Analytics 中创建区段的过程中显示的“**[!UICONTROL 将此区段发布到 Experience Cloud]**”复选框，可使该区段在 Adobe Target 的自定义受众库中提供。在 Analytics 或 Audience Manager 中创建的区段可用于 Target 中的活动。例如，您可以根据 Analytics 转化量度和 Analytics 中创建的受众区段，来创建营销活动。

在Adobe Target中：

1. 选择&#x200B;**[!UICONTROL 受众]**。
1. 在“**[!UICONTROL 受众]**”页面上，找到来源于 [!DNL Experience Cloud] 的受众。这些受众可在 [!DNL Target] 活动中使用。

   ![定位受众](assets/target-audiences.png)
