---
title: 在Web SDK升级助手中管理迁移
description: 在Web SDK升级助手中创建、查看和打开迁移。
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
source-wordcount: '397'
ht-degree: 0%
---
# 管理迁移

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_migrations"
>title="迁移"
>abstract="每次迁移都会将一个tags属性中的Adobe Analytics实施升级到Web SDK。 打开迁移以从之前停止的位置继续，或选择“新建”以开始迁移。"

**[!UICONTROL 迁移]**&#x200B;页面是Web SDK升级助手的起点。 其中列出了您组织中的迁移，包括每个迁移的进度、状态以及创建者。 此页用于创建迁移或打开现有迁移。

## 创建迁移 {#create}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_newmigration"
>title="新迁移"
>abstract="选择要迁移的tags属性以及该属性中的库。 在创建迁移时，升级助手会拍摄库的快照。 迁移快照后对库所做的更改不包括在内。 在完成迁移之前，标记属性不会发生更改。"

<!-- markdownlint-enable MD034 -->

在创建迁移之前，请确保您满足[先决条件](overview.md#prerequisites)。

1. 在&#x200B;**[!UICONTROL 迁移]**&#x200B;页面上，选择&#x200B;**[!UICONTROL 新建]**。
1. 输入迁移的名称和（可选）说明。
1. 选择要迁移的标记属性。
1. 选择标记库。 在创建迁移时，升级助手会拍摄此库中现有实施的快照。 之后对库所做的更改将不会反映在迁移中。
1. 选择&#x200B;**[!UICONTROL 创建]**。

新迁移将显示在列表中。 将其打开以启动[组件选择](component-selection.md)。

## 打开迁移 {#open}

选择迁移的名称以将其打开。 迁移步骤将显示在左侧导航中。 您可以返回任何已完成的步骤，根据需要经常查看或更改这些步骤，但您尚未完成的步骤不可用。

升级助手会在您执行各个步骤时保存进度，以便您退出迁移并稍后返回。 在[完成迁移](final-review.md#finalize)之前，您配置的任何内容都不会生效。 完成迁移后，该迁移将变为只读。 您仍然可以打开它以查看它创建的内容，但无法更改它。

## 其他迁移操作 {#actions}

选择迁移的行以显示对其可用的操作：

* **[!UICONTROL 继续]**：打开迁移。
* **[!UICONTROL 重复的运行]**：创建迁移的副本。
* **[!UICONTROL 重命名]**：更改迁移的名称和描述。
* **[!UICONTROL 存档]**：将迁移的状态更改为&#x200B;**[!UICONTROL 已存档]**。
* **[!UICONTROL 删除迁移]**：永久删除迁移。 您无法撤消此操作。
