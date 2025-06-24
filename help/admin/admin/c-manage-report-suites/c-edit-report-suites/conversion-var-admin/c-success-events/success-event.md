---
description: 成功事件是可跟踪的操作。什么是成功事件完全由您来决定。例如，如果访客购买一件产品，该购买事件可被视为成功事件。
keywords: 事件
title: 成功事件概述
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 54%

---

# 成功事件

成功事件（也称为转化事件或自定义事件）是可以跟踪的操作。 什么是成功事件完全由您来决定。例如，如果访客购买一件产品，该购买事件可被视为成功事件。

有关成功事件的视频概述，请参阅Analytics教程指南中的[转化事件简介](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events)。

## 成功事件示例

成功事件的种类有多种，具体取决于网站类型。下面是一些示例：

* **零售**：产品查看、结账、购买
* **媒体**：订阅、竞赛注册、页面查看、视频查看
* **金融**：提交申请、登录、使用自助服务工具
* **旅行**：预订（购买）、内部促销活动（点进）、搜索（行程定价）
* **电信**：购买、商机、使用自助服务工具
* **高科技**：下载白皮书、RFP、填写表单、请求支持
* **汽车**：提交商机、申请报价、下载手册

成功事件是由 [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=zh-Hans) 变量来定义。

## 配置成功事件

您可以配置在网站上使用的事件变量。 您可以添加多达 1,000 个成功事件。仅当您使用H22代码或更高版本时，事件81-1,000才有效。

配置成功事件：

1. 在Adobe Analytics中，选择&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 选择要配置成功事件的报表包。
1. 选择&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 成功事件]**。

   ![步骤结果](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. 在&#x200B;[!UICONTROL **Event**]&#x200B;列中，标识要用作成功事件的事件名称。

1. 在&#x200B;**[!UICONTROL 名称]**&#x200B;列中，选中该项旁边的复选框以启用编辑，然后指定所需的名称。

   为您的网站上使用的成功事件取一个有意义的名称。例如，如果 event1 用于跟踪注册，则在此处更改名称，使 event1 在所有转化报告中都表示为“注册”量度。

1. 在&#x200B;**[!UICONTROL 类型]**&#x200B;列中，选中该项旁边的复选框以启用下拉列表，然后选择所需的类型。

   >[!IMPORTANT]
   >
   >更改事件类型时，请考虑以下事项：<ul><li>您可以在计数器和数值之间更改事件类型，而不会失去对之前捕获数据的访问权限。</li><li>将事件类型更改为货币事件，或将货币事件更改为其他事件类型时，将显示一则消息，声明历史数据在报表中不可用。 不同事件类型使用单独的数据表格，并且无法同时使用。如果用户还原事件类型，则可以恢复一些历史数据。但是，在初始更改后收集的任何数据均不可用。</li></ul>

   您选择的类型将决定事件是计数器（标准）、数值还是货币事件。 <p>计数器事件用于及时记录事件。</p><p>数值事件用于报告非货币数字，如订单中使用的优惠券数量。</p> <p>货币事件记录小数，如税或运。 传递给货币事件的值在收到后将从页面货币换算为报告包的基本货币。货币事件用于跟踪税款和运输费用。有关使用货币事件的详细信息，请与 Adobe 代表联系。<p>数值和货币事件允许您以大于 1 的增量增加量度。</p><p>在“标准”类型的“数据源”中使用的事件必须是数值事件或货币事件。</p>

1. 在&#x200B;**[!UICONTROL 极性]**&#x200B;列中，选中复选框，然后从下拉菜单中选择此量度的上升趋势是好还是坏。

   这允许您指示Adobe Analytics将给定的自定义事件（指标）上升的情况视为好还是坏。 它激活各种量度的方向指示器（箭头）以添加上下文（例如，逐周比较）。  示例：如果“提交的错误数”呈逐周上升趋势，Adobe Analytics 应将这种情况视为好还是坏？“电子邮件注册数”的上升可能是好的。但“表单提交错误数”的上升可能是坏的。在 Analysis Workspace 中，极性可应用于以下对象：自由格式表的条件格式、“概要变化”可视化图表，及地图可视化的“反差”颜色方案。

1. 在&#x200B;**[!UICONTROL 可见性]**&#x200B;列中，选中复选框，然后从下拉菜单中选择是否在菜单、量度选择器、计算量度生成器和区段生成器中隐藏标准（内置）量度、自定义事件和内置事件。

   这项设置不影响相关量度或事件的数据收集，而只会影响该量度或事件在用户界面中的可见性，如下所示：

   其中提供了以下设置：

   | 设置 | 可见位置 | 不可见位置 |
   |---------|----------|---------|
   | [!UICONTROL **随时随地可见**] | <ul><li>Analysis Workspace</li><li>区段生成器</li><li>计算指标生成器</li></ul> | 不适用 |
   | [!UICONTROL **生成器**] | <ul><li>区段生成器</li><li>计算指标生成器</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **随时随地隐藏**] | 不适用 | <ul><li>Analysis Workspace</li><li>区段生成器</li><li>计算指标生成器</li></ul> |

1. 在&#x200B;[!UICONTROL **Description**]&#x200B;列中，选中该复选框，然后提供说明。
1. 在&#x200B;[!UICONTROL **独特事件记录**]&#x200B;列中，选中复选框，然后从下拉菜单中选择是否始终记录该事件。

   可以使用以下选项：

   | 选项 | 功能 |
   |---------|----------|
   | [!UICONTROL **每次访问记录一次**] | 将给定事件绑定到访客的会话。 将忽略同一次访问中给定事件的后续计数。此类型的事件序列化不需要对实施进行任何更改。 |
   | [!UICONTROL **使用事件ID**] | 将给定事件绑定到自定义ID。 将忽略具有相同事件 ID 的给定事件的后续计数。此类型的事件序列化需要在点击中使用自定义 ID 来消除重复值。请参阅实施用户指南中的[事件 ID 序列化](/help/implement/vars/page-vars/events/event-serialization.md)。 |

1. 在&#x200B;[!UICONTROL **参与率**]&#x200B;列中，选中该复选框，然后选择是启用或禁用参与率。 启用后，它将为访问中的所有维度项目提供全部归因点数。

   >[!NOTE]
   >
   >您最多可以为 100 个自定义事件启用参与率。除此之外，您还可以在[计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md)生成器中创建参与率量度。

1. 选择&#x200B;**[!UICONTROL 保存]**。
