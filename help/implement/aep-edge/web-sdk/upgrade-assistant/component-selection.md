---
title: Web SDK升级助手中的组件选择
description: 选择要包含在Web SDK迁移中的标记规则、数据元素和扩展。
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta 版
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%
---
# 组件选择

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection"
>title="组件选择"
>abstract="选择要包含在此迁移中的规则、数据元素和扩展。 默认情况下，将选择主动对Adobe Analytics实施做出贡献的组件。 之后的步骤仅适用于您在此处选择的组件。"

组件选择是迁移的第一步。 使用它从标记属性中选择要包含在迁移中的规则、数据元素和扩展。

升级助手将标记属性中的组件组织为&#x200B;**[!UICONTROL 规则]**、**[!UICONTROL 数据元素]**&#x200B;和&#x200B;**[!UICONTROL 扩展]**&#x200B;选项卡。 每个选项卡都根据升级助手在[创建迁移](manager.md#create)时拍摄的库快照，列出该类型的所有属性组件。 默认情况下，只会选择主动对Adobe Analytics实施做出贡献的组件。 可以选择或清除任何组件。

**[!UICONTROL Published]**&#x200B;列显示每个组件是否都是您选择的库的一部分。 不属于库的组件存在于标记属性中，但不存在于该库中。 要按此筛选列表，请使用&#x200B;**[!UICONTROL Source]**&#x200B;筛选器。

您可以包含与Adobe Analytics无关的组件，例如Adobe Target、Adobe Audience Manager或第三方扩展的组件，但升级助手不会将它们转换为Web SDK。

您选择的组件决定了后续步骤的适用情况。 例如，您可以包括任何内容都不引用的数据元素，以便[审核结果](audit-findings.md)可以标记它们以进行清理。

## 查看组件详细信息 {#details}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_tagsusage"
>title="标记使用"
>abstract="使用此组件的规则、数据元素和扩展。 扩展用法仅涵盖扩展配置设置。 规则内的用法显示在规则用法下。"

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_analyticsusage"
>title="Analytics使用情况"
>abstract="此组件分配给的Adobe Analytics变量，按变量类型分组。"

<!-- markdownlint-enable MD034 -->

选择组件的名称以打开一个面板，该面板显示其配置和使用位置：

* **[!UICONTROL 标记用法]**：使用该组件的规则、数据元素和扩展。 **[!UICONTROL 扩展用法]**&#x200B;仅涵盖扩展配置设置。 规则内的使用情况显示在&#x200B;**[!UICONTROL 规则使用情况]**&#x200B;下。
* **[!UICONTROL Analytics用法]**：组件所分配的Adobe Analytics变量，按变量类型分组。

要在标记UI中查看该组件，请在面板顶部选择其名称。

完成后，选择&#x200B;**[!UICONTROL 保存并继续]**&#x200B;以转到[审核发现](audit-findings.md)。