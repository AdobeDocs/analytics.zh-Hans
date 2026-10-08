---
title: Web SDK升级助手中的Web SDK实施
description: 查看升级助手添加到现有标记规则的Web SDK操作。
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
source-wordcount: '311'
ht-degree: 0%
---
# Web SDK实施

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_websdkimplementation"
>title="Web SDK实施"
>abstract="查看升级助手添加到规则中的Web SDK操作。 您的Adobe Analytics操作将保持不变。 选择一个组件，以并排比较其当前配置和Web SDK配置。 只有排队的组件会添加到迁移中。"

<!-- markdownlint-enable MD034 -->

升级助手使用您选择的组件和[XDM映射](xdm-mapping.md)，在每个Adobe Analytics操作之后直接将Web SDK操作添加到您的规则中。 Analytics操作保持不变，因此这些规则会将数据发送到Adobe Analytics和Web SDK。 大多数数据元素会沿用不变，而规则会继续按名称引用它们。

**[!UICONTROL Change type]**&#x200B;列显示完成迁移对每个组件的作用：

* **[!UICONTROL 已添加Web SDK操作]**：升级助手已将Web SDK操作添加到规则。
* **[!UICONTROL 无更改]**：组件未更改便继续运行。
* **[!UICONTROL 已阻止]**：组件需要您审核，升级助手才能向它添加Web SDK操作。 选择组件可查看导致其受阻的原因。

选择一个组件，以并排比较其当前配置与Web SDK配置。 如果您需要更多上下文，则升级助手将链接到标记UI中的组件。

排队的组件将添加到迁移中。 要将组件排入队列，请在列表中选择该组件，或在其详细信息中选择&#x200B;**[!UICONTROL 队列]**。 若要将其取出，请选择&#x200B;**[!UICONTROL 从队列]**&#x200B;中删除。 在您[完成迁移](final-review.md#finalize)之前，升级助手不会更改您的标记属性。

升级助手使用AI生成Web SDK操作，并且结果可能不准确或不完整。 生成操作不会验证它们在您的网站上的行为，因此在发布库之前测试它们。
