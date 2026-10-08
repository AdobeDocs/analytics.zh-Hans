---
title: Web SDK升级助手中的审核结果
description: 在迁移到Web SDK之前，请查看并解决标记组件的可选清理建议。
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
source-wordcount: '336'
ht-degree: 2%
---
# 审计结果

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_auditfindings"
>title="审计结果"
>abstract="调查结果会指出迁移之前可能需要清理的规则和数据元素，例如没有任何内容引用的数据元素。 接受发现以将其建议的更改包含在迁移中，或拒绝它以保持组件的原样。 此步骤是可选的。"

<!-- markdownlint-enable MD034 -->

升级助手会检查您在[组件选择](component-selection.md)中选择的规则和数据元素，并标记迁移之前可能需要清理的规则和数据元素：

* 可以合并的重复规则或共享事件和条件的规则
* 可能影响数据准确性的规则操作序列
* 您可以合并的重复数据元素
* 可能未使用，但您可以禁用它的数据元素

此步骤是可选的。 您可以解决任意数量的调查结果，或直接继续[报告包验证](rs-verification.md)。

## 查看调查结果 {#review}

选择一个发现项目以查看其详细信息，包括：

* 结果的描述
* 组件的当前配置
* 在何处使用组件，在tags资产和Adobe Analytics中均使用

每个发现结果都包括一项推荐操作，具体取决于发现结果的类型。 例如，对于没有引用的数据元素，建议的操作是禁用它。

>[!IMPORTANT]
>
>标记为未使用的数据元素可能仍会动态引用，或从标记外部引用。 在接受发现结果之前，请检查其建议的更改、自定义代码、操作顺序和引用，以确认它们保留您预期的行为。

## 解决调查结果 {#resolve}

执行查找结果的建议操作时，将接受该查找结果。 升级助手将更改添加到迁移，并在您[完成迁移](final-review.md#finalize)时应用它。 如果您不想进行更改，请拒绝该发现。

如果您改变主意，可以重新打开已接受或已拒绝的发现。 要一次更新多个查找结果，请在列表中选择它们。
