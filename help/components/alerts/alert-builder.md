---
description: 了解如何在 Analysis Workspace 中创建警报。
title: 创建警报
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '1028'
ht-degree: 87%

---

# 创建警报 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="时间粒度"
>abstract="时间粒度是指系统检查警报的频率。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>只有拥有 Adobe Analytics Prime 或 Ultimate 包的组织才能使用带有异常检测的警报（也称为&#x200B;_智能警报_）。

Adobe Analytics 中的警报允许您根据变化的百分比或特定数据点收到通知。根据您的 Adobe Analytics 包，您还可以使用基于异常阈值触发的警报。服务器调用使用情况警报是另一种警报，仅供 Analytics 管理员使用。这些警报会通知您服务器调用使用情况和使用承诺数据存在超额的风险或发生次数。有关详细信息，请参阅 [服务器调用使用情况警报](/help/admin/tools/server-call-usage/scu-alerts.md)。

有关警报的更多详细信息，请参阅[警报概述](alerts-overview.md)。

要创建警报：

1. 您可以通过以下任意方式创建警报：

   * 在 Analysis Workspace 中打开一个项目，然后选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 创建警报]**。
   * 在 Analysis Workspace 中打开一个项目，然后使用以下快捷键：***cmd + shift + a*** (macOS) 或 ***ctrl + shift + a*** (Windows)。
   * 在 Analysis Workspace 中打开一个项目，在自由格式表中选择一个或多个行项目，然后右键单击并选择&#x200B;**[!UICONTROL 从选定范围中创建警报]**。这项操作会立即预填充[警报构建器](alert-builder.md)，以便使用正确的量度和过滤器创建警报。
   * [从警报管理器](/help/components/alerts/alert-manager.md#create-alerts)创建警报。

   警报构建器会显示出来。此界面与 Analytics 中生成区段或计算量度的界面很相似。



## 警报构建器

警报构建器界面与您在 Customer Journey Analytics 中创建区段或计算量度所使用的界面类似：

![警报构建器界面](assets/alert-builder.png)

在警报构建器中为警报指定以下详细信息：

| 元素 | 描述 |
|---------|----------|
| **[!UICONTROL 标题]** | 指定警报的名称。 警报名称可能包含报告名称或量度阈值。 |
| **[!UICONTROL 描述（可选）]** | 指定警报的描述。 |
| **[!UICONTROL 时间粒度]** | 选择检查量度的频率：每天、每周或每月。<p> |
| **[!UICONTROL 收件人]** | 指定警报的发送地址。警报可以发送给Analytics用户、Analytics群组、原始电子邮件地址或电话号码。<p><b>重要</b>：电话号码前必须加上 `+` 和[国家/地区代码](https://countrycode.org/)。</p><p>用户收到的电子邮件示例：</p><p>![警报电子邮件](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 过期日期]** | 设置警报过期的日期和时间。 |
| **[!UICONTROL 延迟]** | 数据完成并可在 Customer Journey Analytics 中报告所需的时间因组织而异，通常在数据事件时间后的 3 至 9 小时之间。为了确保警报准确无误，给定事件范围的事件数据必须是完整的，这意味着 Adobe 不会再接收指定事件范围的任何事件数据。<p>为了解决摄取时间的延迟，警报发送前的默认延迟时间为 9 小时。</p><p>您可以将默认延迟时间从 9 小时调整为 0 至 24 小时之间的任意值。但是，将延迟时间减少到 9 小时以下可能意味着您报告的数据不完整，从而会导致警报信息不准确。</p><p>减少延迟时间时请考虑以下事项：</p><ul><li>**了解数据可用性与数据完整性之间的区别**：所有批量数据需在 3 至 9 小时后才会被摄取至 Experience Platform 数据集。为了确保警报的准确性，数据摄取必须完整，且数据集中所有批量数据都可用。</li><li>**确定数据需要多长时间才能完成并在数据集中可用**：数据摄取时间因组织而异。确保您为警报传递选择的延迟时间与批量数据在 Platform 数据集中可用所需的时间相同或更短<!--add link? -->。</li><p>**提示：**&#x200B;了解所有批量数据完成并纳入 Platform 数据集所需时间的最准确方法是咨询组织中的数据工程师。</p><p>或者，您也可以大致了解您所在组织的批量数据在 Experience Platform 数据集中变得可用所需的时间。在 Analysis Workspace 中创建如下自由格式表格：</p><ol><li>在 Analysis Workspace 中的自由格式表中，添加一个&#x200B;[!UICONTROL **事件**]&#x200B;量度和一个&#x200B;[!UICONTROL **天**]&#x200B;维度。</li><li>使用&#x200B;[!UICONTROL **小时**]&#x200B;维度来分解&#x200B;[!UICONTROL **天**]&#x200B;维度。<p>无数据的小时将显示为 0。</p></li></ol><li>**考虑计算中的错误**：如果您缩短默认延迟时间，请将延迟时间配置为至少比您的组织完成数据摄取所需的时间长一个小时。例如，如果数据摄取完成之前有 3 小时的延迟，那么您应该将延迟时间设置为 4 小时。</li> |
| **[!UICONTROL 发送警报时间]** | [!UICONTROL **以下任何一个量度触发器**]： <ol><li>拖放指标（包括计算指标）以创建警报的触发器。<p>如果警报中有量度、维度或区段与当前选中的报表包不兼容，则会显示&#x200B;*不兼容的组件*&#x200B;消息。</p><p>确定在设置警报之前，量度必须超过或使用的值（对于异常）的阈值（对于上、下、等于或百分比变化）。</li><li>选择下列条件之一：<ul><li>异常存在</li><li>异常超出预期</li><li>异常低于预期值</li><li>高于或等于</li><li>低于或等于</li><li>更改者</li></ul></li><li>选择阈值或输入值。</li></ol>[!UICONTROL **使用所有这些过滤器**]：通过拖放区段或维度来为警报添加过滤器。例如，添加&#x200B;*仅限移动设备*&#x200B;区段表示仅针对移动设备触发规则。您可以使用 AND 语句添加其他过滤器。您可以通过单击齿轮图标添加 AND 或 OR 规则。</p><p>有关示例用例，请参阅[警报 - 用例](alerts-use-cases.md)。</p> |
| **[!UICONTROL 预览]** | 交互式警报预览可根据过去的经验显示警报大致的触发频率。<p>例如，如果将时间粒度设置为每天，则预览会显示某个量度在过去 30 或 31 天中触发了 x 次警报。</p><p>如果您发现触发警报的次数过多，则可以在[管理警报](alert-manager.md)中调整阈值。</p><p>![](assets/alert-preview.png){width="50%"}</p> |
