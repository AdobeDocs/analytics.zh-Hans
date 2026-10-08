---
title: Web SDK升级助手中的最终审阅
description: 审查并完成Web SDK迁移，然后将生成的标记库发布到生产环境。
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
source-wordcount: '469'
ht-degree: 0%
---
# 最终审阅

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_finalreview"
>title="最终审阅"
>abstract="选择要使用的Experience Platform沙盒，然后查看此迁移创建或更改的所有内容。 在完成迁移之前，不会发生任何更改。 完成后，升级助手会一次创建所有内容，将标记更改添加到新库中，并使此迁移成为只读迁移。 然后，您可以自行将该库发布到生产环境。"

<!-- markdownlint-enable MD034 -->

最终审查是迁移的最后一步。 它显示了迁移在Experience Platform和tags资产中创建或更改的所有内容。

## 查看迁移所创建的内容 {#review}

首先，选择迁移在其中创建其资源的Experience Platform沙盒。 只有在选择沙盒后才能完成迁移。

然后，升级助手会列出完成迁移创建或更改的所有内容：

* **[!UICONTROL XDM]**：一个以您的XDM映射及其所需的自定义字段组命名的新架构。 标准字段组已存在，因此架构按原样使用它们。 仅当您选择在[XDM映射](xdm-mapping.md#schema)中创建新架构时，才会显示此部分。
* **[!UICONTROL 数据集]**：两个数据集，一个用于开发，一个用于生产。 每个名称都以迁移命名，如`My migration - Development`。
* **[!UICONTROL 数据流]**：两个数据流（一个用于开发，一个用于生产）的命名方式与数据集相同。
* **[!UICONTROL Adobe标记]**：迁移后命名的新的库，如`Library - "My migration"`。 该库包含迁移更改的规则和数据元素，以及Web SDK操作所需的扩展配置。

## 完成迁移 {#finalize}

在完成迁移之前，升级助手不会更改标记属性或在Experience Platform中创建任何内容。

>[!IMPORTANT]
>
>完成迁移后，它将变为只读。 您仍然可以从&#x200B;**[!UICONTROL 迁移]**&#x200B;页面打开它以查看它创建的内容，但无法更改它或再次完成它。 由于新库仍在开发中，您可以在发布库之前，在标记UI中编辑或删除标记更改。

1. 选择&#x200B;**[!UICONTROL 创建项目]**。
1. 在&#x200B;**[!UICONTROL 验证这些推荐]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 继续]**。
1. 在&#x200B;**[!UICONTROL 完成此迁移？]** 对话框，选择&#x200B;**[!UICONTROL 完成]**。

升级助手会一次创建所有内容并显示进度。 它会将标记更改添加到新库，但不发布库。

## 发布更改 {#publish}

完成迁移后，在标记发布流中移动新库：

1. 在开发环境中构建并测试库，以确保Web SDK实施会发送您预期的数据。
1. 提交库以供审批，并在暂存环境中测试它。
1. 批准库并将其发布到生产环境。

请参阅标记用户指南中的[发布流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/publishing-flow)。
