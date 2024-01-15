---
description: 描述如何配置成功事件的步骤。
title: 配置成功事件
feature: Event
role: Admin
exl-id: 0e9a6d8f-2ce7-4551-885d-bd77ff131da0
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 100%

---

# 配置成功事件

配置成功事件：

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报告包]**。
1. 选择报告包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 成功事件]**.

   ![步骤结果](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. 在&#x200B;**[!UICONTROL 名称]**&#x200B;列中，选中每个项目旁边的复选框以启用编辑，然后指定所需的名称。
1. 在&#x200B;**[!UICONTROL 类型]**&#x200B;列中，选中每个项目旁边的复选框以启用下拉列表，然后选择所需的类型。

   >[!NOTE]
   >
   >在更改事件类型之前，请参阅[更改事件类型](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)。

   有关这些元素的信息，请参阅[成功事件页面 - 描述](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)。

1. 在&#x200B;**[!UICONTROL 极性]**&#x200B;列中，指定此量度的上升趋势是好还是坏。
1. 在&#x200B;**[!UICONTROL 可见性]**&#x200B;列中，您可以隐藏“菜单”、“量度选择器”、“计算量度生成器”和“区段生成器”中的标准（内置）量度、自定义事件和内置事件。

   这项设置不影响相关量度或事件的数据收集，而只会影响该量度或事件在用户界面中的可见性，如下所示：


   | 设置 | 可见位置 | 不可见位置 |
   |---------|----------|---------|
   | [!UICONTROL **随时随地可见**] | <ul><li>Reports &amp; Analytics（菜单和指标选择器）</li><li>Analysis Workspace</li><li>区段生成器</li><li>计算指标生成器</li></ul> | 不适用 |
   | [!UICONTROL **生成器**] | <ul><li>区段生成器</li><li>计算指标生成器</li></ul> | <ul><li>Reports &amp; Analytics（菜单和指标选择器）</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **随时随地隐藏**] | 不适用 | <ul><li>Reports &amp; Analytics（菜单和指标选择器）</li><li>Analysis Workspace</li><li>区段生成器</li><li>计算指标生成器</li></ul> |

1. 提供描述。
1. 选择是否始终记录该事件。
1. 启用或禁用参与率量度。

   >[!NOTE]
   >
   >您最多可以为 100 个自定义事件启用参与率。除此之外，您还可以在[计算量度](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md)生成器中创建参与率量度。

1. 单击&#x200B;**[!UICONTROL 保存]**。
