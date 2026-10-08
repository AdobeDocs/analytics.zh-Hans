---
title: Web SDK升级助手
description: 规划并执行Adobe Analytics标记扩展到Adobe Experience Platform Web SDK的迁移。
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
source-git-commit: 212d38950264a33b925b7281c241992cadca2bfb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 3%
---
# Web SDK升级助手

Web SDK升级助手可帮助您规划并执行Adobe Analytics标记扩展到Adobe Experience Platform Web SDK的迁移。 它将迁移引入一个引导式工作区，以便您能够以结构化、可跟踪的方式从现有标记实施移至Web SDK。

## 升级助手的工作方式 {#how-it-works}

每个迁移都在一个标记属性中与Adobe Analytics实施配合使用。 升级助手会将Web SDK操作添加到现有规则中，而不会删除其Adobe Analytics操作，因此您的实施将继续与Web SDK一起将数据发送到Adobe Analytics。

升级助手仅转换Adobe Analytics组件。 您可以包含其他扩展（如Adobe Target、Adobe Audience Manager或第三方扩展）中的组件，但升级助手不会将它们转换为Web SDK。

升级助手将指导您完成以下步骤，每个步骤都基于您在上一步中所做的决策：

1. **[组件选择](component-selection.md)**：选择要包含在迁移中的规则、数据元素和扩展。
1. **[审核结果](audit-findings.md)**：查看所选组件的可选清理建议。
1. **[映射器准备](mapper-prep.md)**：查看报表包中的Analytics变量，并选择要结转的变量。
1. **[XDM映射](xdm-mapping.md)**：将Analytics变量映射到XDM架构中的字段。
1. **[Web SDK实施](web-sdk-implementation.md)**：查看升级助手添加到您规则的Web SDK操作。
1. **[最终审核](final-review.md)**：选择Experience Platform沙盒，审核迁移所创建的内容，然后完成迁移。

每个步骤都会配置迁移的一部分，您可以返回已完成的步骤，根据需要经常进行查看或更改。 在完成迁移之前，升级助手不会更改标记属性或在Experience Platform中创建任何内容。 完成后，升级助手会立即创建所有内容，并将标记更改添加到新库中。 然后，测试该库并使用标记发布流将其发布到生产环境。

>[!IMPORTANT]
>
>升级助手使用人工智能(AI)生成推荐，如XDM字段映射和Web SDK规则配置。 这些建议可能不准确或不完整。 在将更改发布到生产环境之前验证它们。

## 先决条件 {#prerequisites}

在创建迁移之前，请确保您具有：

* 升级助手所需的[权限](#permissions)。
* 使用Adobe Analytics扩展的tags属性。
* 该属性中的一个库，其中包含您要迁移的实施。 库可以处于任何状态，包括已发布。 请参阅标记用户指南中的[库](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/libraries)。

### 权限 {#permissions}

升级助手需要以下访问权限。 请与您组织的Experience Platform产品管理员合作，以获取您缺少的任何权限。

| 访问类型 | 必需 |
| --- | --- |
| [Experience Platform 权限](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home#permissions) | <ul><li>[!UICONTROL 查看架构]</li><li>[!UICONTROL 管理架构]</li><li>[!UICONTROL 查看数据集]</li><li>[!UICONTROL 管理数据集]</li><li>[!UICONTROL 查看身份标识命名空间]</li></ul> |
| 产品访问 | <ul><li>数据收集（标记）</li><li>Adobe Analytics</li></ul> |
| [标记权限](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/administration/user-permissions) | [!UICONTROL 管理属性] |

准备就绪后，[创建迁移](manager.md#create)。
