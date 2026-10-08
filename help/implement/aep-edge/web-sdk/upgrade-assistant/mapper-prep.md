---
title: Web SDK升级助手中的映射器准备
description: 查看报表包中的Analytics变量，并选择要转入XDM映射的变量。
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
source-wordcount: '507'
ht-degree: 0%
---
# 映射器准备

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_mapperprep"
>title="映射器准备"
>abstract="查看Tags属性发送到每个报表包的Analytics变量。 您在此处选择的变量将结转到XDM映射。 使用选项卡检查最近数据，查找重复变量，并在报表包间比较设置。"

<!-- markdownlint-enable MD034 -->

升级助手会识别标记属性将数据发送到的报表包，然后将实施中的Analytics变量与每个报表包的配置和最近数据进行比较。 使用此步骤可决定哪些变量可结转到[XDM映射](xdm-mapping.md)。

升级助手使用您的报表包来了解您的实施设置了哪些变量以及这些变量的配置方式。 活动数据涵盖过去90天。

## 变量活动 {#variable-activity}

**[!UICONTROL 变量活动]**&#x200B;选项卡列出了在[变量分析](#variable-analysis)中选择映射的报表包的Analytics变量，并显示每个变量在过去90天内是否收集了数据。

您选择的变量将结转到XDM映射。 考虑清除不再收集数据或在Web SDK实施中不需要的变量。 最近没有活动的变量可能仍在使用中，例如，如果它是季节性变量或具有低流量，则在清除它之前请确认您不需要它。

对于您结转的每个列表变量和列表属性，输入分隔其值的分隔符。 升级助手无法从Adobe Analytics获取分隔符，并且您无法继续操作，除非每个分隔符都包含分隔符。

## 变量分析 {#variable-analysis}

如果tags属性将数据发送到多个报表包，请首先选择要映射的报表包。 **[!UICONTROL 变量分析]**&#x200B;选项卡随后会在映射变量之前标记可能需要决策的变量：

* 似乎收集了相同数据的变量。 确认它们捕获了相同的信息，然后决定是将其合并到单个变量中，还是将其分开。
* 最近未收集数据的变量。
* 值全部为“未指定”的变量。

## 比较报表包 {#compare}

如果标记属性将数据发送到多个报表包，则&#x200B;**[!UICONTROL 比较报表包]**&#x200B;选项卡最多可在其中三个报表包中比较每个变量的设置。 使用它查找在报表包之间配置不同的变量，然后再将它们映射到架构。

## 更新报表包数据 {#refresh}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_mapperprep_refresh"
>title="刷新报表包数据"
>abstract="再次检查链接到此标记属性的报表包，包括其变量设置和最近数据，然后重新运行变量分析。 如果升级助手尚未找到任何报表包，则会先在标记属性中查找它们。 您的选择和决策将被保留。"

<!-- markdownlint-enable MD034 -->

您可以更改升级助手在此步骤中分析的报表包。 如果在迁移过程中报表包配置发生更改，请选择&#x200B;**[!UICONTROL 刷新报表包数据]**&#x200B;以重新运行分析。 升级助手会保留您现有的选择和决策。

完成后，选择&#x200B;**[!UICONTROL 保存并继续]**&#x200B;以转到[XDM映射](xdm-mapping.md)。
