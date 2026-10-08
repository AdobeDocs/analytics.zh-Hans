---
title: Web SDK升级助手中的XDM映射
description: 在Web SDK迁移过程中，将Adobe Analytics变量映射到XDM架构中的字段。
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
source-wordcount: '419'
ht-degree: 3%
---
# XDM映射

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping"
>title="XDM映射"
>abstract="将您选择的Analytics变量映射到XDM架构中的字段。 升级助手可以使用人工智能建议的映射创建新架构，也可以将变量映射到已拥有的架构。 在继续操作之前，请查看所有映射。"

<!-- markdownlint-enable MD034 -->

Web SDK使用[体验数据模型(XDM)](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home)字段发送数据，因此您从[报表包验证](rs-verification.md)结转的每个Analytics变量都需要XDM架构中的匹配字段。 在此步骤中，您可以选择架构并将变量映射到其字段。

## 选择架构 {#schema}

您可以通过以下两种方式之一构建映射：

* **创建新架构**：升级助手会分析您的Analytics变量并为每个变量建议一个XDM字段，然后根据这些建议生成架构以供您查看。
* **使用现有架构**：选择Experience Platform中已存在的架构，然后自行将每个变量映射到字段。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping_fieldgroups"
>title="字段组首选项"
>abstract="选择升级助手在构建架构时支持的字段组类型。 标准字段组由Adobe定义。 自定义字段组由您的组织定义。"

<!-- markdownlint-enable MD034 -->

创建新方案时，您还可以选择升级助手是支持标准字段组还是自定义字段组。 标准字段组由Adobe定义，而自定义字段组由您的组织定义。 请参阅XDM文档中的[字段组](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#field-group)。

## 查看映射 {#review}

映射将列出每个Analytics变量及其映射到的XDM字段，并预览其旁边的完整架构。 选择架构的一部分以筛选列表，找到映射到此列表的变量。 您可以同时调整单个映射和架构本身。

升级助手使用AI来建议映射，并且结果可能不准确或不完整。 在继续操作之前，请查看每个映射。 在您[完成迁移](final-review.md#finalize)之前，升级助手不会在Experience Platform中创建架构。

完成后，选择&#x200B;**[!UICONTROL 保存并继续]**&#x200B;以保存您的映射并转到[Web SDK实施](web-sdk-implementation.md)。 要在保存映射后对其进行更改，请选择&#x200B;**[!UICONTROL 编辑]**，进行更改，然后选择&#x200B;**[!UICONTROL 保存并再次继续]**。 完成迁移时，不会包含未以这种方式保存的更改。
