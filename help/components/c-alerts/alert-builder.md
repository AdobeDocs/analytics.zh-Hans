---
description: 在 Analysis Workspace 中使用警报。
title: 警报生成器概述
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 966bd9a05e6c344a62ce3f0b12df8a99ff3d7ece
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 25%

---

# 创建警报 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="时间粒度"
>abstract="时间粒度是指检查警报的频率以及将包含的内容"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>将警报与异常检测（也称为&#x200B;_智能警报_）结合使用仅适用于具有Adobe Analytics Prime或Ultimate包的组织。

Adobe Analytics中的警报允许您根据更改的百分比或特定数据点接收通知。 根据您的Adobe Analytics包，您还可以使用要基于异常阈值触发的警报。 服务器调用使用情况警报是一种不同的警报，仅供Analytics管理员使用。 这些警报会通知您服务器调用消耗量和承诺数据中存在超额的风险或发生超额的情况。 有关详细信息，请参阅[服务器调用使用情况警报](/help/admin/admin/c-server-call-usage/scu-alerts.md)。

有关警报的更多详细概述信息，请参阅[警报概述](/help/components/c-alerts/intellligent-alerts.md)。

要创建警报，请执行以下操作：

1. 通过访问警报生成器开始创建警报。 您可以通过以下任意方式访问警报生成器：

   * 在Analysis Workspace中打开一个项目，然后选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 创建警报]**。
   * 在Analysis Workspace中打开一个项目，然后使用以下快捷方式： ***ctrl （或cmd） + shift + a***。
   * 在Analysis Workspace中打开一个项目，在自由格式表中选择一个或多个行项，然后右键单击并选择&#x200B;**[!UICONTROL 从选定范围中创建警报]**。 此操作会立即预填充警报生成器，以便使用正确的量度和过滤器创建警报。
   * 从警报管理器](/help/components/c-alerts/alert-manager.md#create-alerts)创建警报[。

   此时将显示警报生成器。 此界面与Analytics中构建区段或计算量度的界面相似：

   ![](assets/alert-builder.png)

1. 指定以下选项来配置警报：

   | 选项 | 描述 |
   |---------|----------|
   | [!UICONTROL **标题**] | 指定警报的名称。警报名称可能包含报表名称或指标阈值。 |
   | [!UICONTROL **描述（可选）**] | 指定警报的说明。 |
   | [!UICONTROL **时间粒度**] | 选择您希望检查指标的频率：每小时、每天、每周或每月。<p><b>注意：</b>对于具有自定义日历的报表包，不支持警报生成器中的每月粒度。<!--true?--></p> |
   | [!UICONTROL **收件人**] | 指定警报的发送地址。可以将警报发送给 Analytics 用户、Analytics 组、原始电子邮件地址或电话号码。<p><b>重要信息：</b>电话号码前面必须加上`+`和[国家/地区代码](https://countrycode.org/)。</p><p>一旦触发警报，用户将收到的电子邮件类似于：</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **过期日期**] | 设置希望警报到期的日期和时间。 |
   | [!UICONTROL **发送警报时间**] | [!UICONTROL **以下任何一个量度触发器**]：将量度（包括计算量度）拖放到此处以创建警报的触发器。<p>如果警报中并非所有量度、维度或区段都与当前所选的数据视图兼容，则会显示&#x200B;**“组件不兼容”**&#x200B;消息。</p><p>确定触发警报前指标必须超过的阈值。您可以将此值设置为一个阈值，然后设置为下列条件之一：</p><ul><li>异常已存在</li><li>异常高于预期</li><li>异常低于预期</li><li>大于或等于</li><li>小于或等于</li><li>更改百分比</li><li>您可以将阈值设置为 90%、95%、99%、99.75% 或 99.9%。</li></ul><p>[!UICONTROL **使用所有这些筛选器**]：拖放区段或维度以添加筛选器。 例如，添加“仅限移动设备”区段意味着规则仅针对移动设备触发。 您可以使用AND语句添加其他过滤器。 您可以通过单击齿轮图标添加 AND 或 OR 规则。</p><p>请参阅[警报 — 用例](/help/components/c-alerts/alerts-use-cases.md)。</p> |
   | [!UICONTROL **预览**] | 交互式警报预览可根据过去的经验显示警报大致的触发频率。<p>例如，如果将时间粒度设置为每天，则预览会显示某个指标在过去30或31天内触发了x次警报。 通过设置警报频率建立预览近似窗口。 对于每日警报频率，预览窗口大约为前30天。 对于每周警报频率，预览窗口大约为过去12周。 对于每月警报频率，预览窗口大约为前12个月。</p><p>如果您发现将触发的警报过多，则可以在[警报管理器](/help/components/c-alerts/alert-manager.md)中调整阈值。</p><p>![](assets/alert_preview.png)</p> |

1. 选择&#x200B;[!UICONTROL **保存**]。
