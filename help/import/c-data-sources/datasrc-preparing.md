---
description: 为使用数据源而采取的准备步骤。
seo-description: 为使用数据源而采取的准备步骤。
seo-title: 准备使用数据源
solution: Analytics
subtopic: 数据源
title: 准备使用数据源
topic: 开发人员和实施
uuid: 876ea069-574b-4e23-93b7-e3828 bfd90 f5
translation-type: tm+mt
source-git-commit: 887f48d2ea5f21b7db95a1a8f716f7da9cf43662

---


# 准备使用数据源

为使用数据源而采取的准备步骤。

* [量度的识别和命名](../../import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [标识数据维度](../../import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [促销活动跟踪代码](../../import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [交易 ID](../../import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [识别数据源数据的有效日期范围](../../import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## 量度的识别和命名 {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

It is important to understand the metrics or measurements that are contained in your data sources, such as *`Off-line Sales Revenue by Product`*, *`Returns by Product`*, or *`Ad Impressions by Campaign`*. 这些名称可以与报表量度（事件、prop 和 eVar）关联。

在确定数据源数据的相应量度到事件映射之后，请使用关联数据源量度所适用的描述性名称重命名事件。

请参阅管理工具帮助中的[成功事件](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=success_event)。

>[!NOTE]
>
>Adobe强烈建议在数据源数据中使用新的空事件，但在少数情况下，使用预先存在的事件可能是合理的。

## 标识数据维度 {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

标识和收集要用来对通过数据源导入的量度进行划分的数据（报表）。该数据称为 *`data dimensions`*。

例如，如果数据源量度测量广告显示次数，则您的数据维度可能是促销活动跟踪代码。如果测量离线销售，建议您使用产品代码（或 SKU）作为数据维度。

您可以定义多个数据维度对应一个量度，但是每个量度必须为每个关联的数据维度提供一个相关的值，或多个值的组合。例如，如果您导入离线销售量度并将其与&#x200B;*`Product`**`Partner`* 数据维度，离线销售计量必须与产品和合作伙伴的每个组合相关(例如总收入)。

>[!NOTE]
>
>可以导入不能按任何数据维度划分的总量度。

在您定义要与数据源一起使用的数据维度之后，请通过将维度数据映射到变量，将其集成到市场营销报表中。可使用标准报表（例如，产品、跟踪代码、搜索关键词）或转化流量变量 (eVar)。

在使用 eVar 时，您可以将现有 eVar 或新 eVar 用作数据维度。在选择了用于从数据源接收数据维度的 eVar 之后，请确保将其正确命名。

请参阅 Analytics 帮助中的[成功事件](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=success_event)。

## 促销活动跟踪代码 {#section_468222796FF449ABAA90D88EB3264CB1}

除了导入成功事件之外，您还可以选择性地导入关联的 eVar 值。例如，如果跟踪具有促销活动跟踪代码的在线活动，并且离线量度也有促销活动跟踪代码，则可以导入具有促销活动跟踪代码的量度。此方法允许您同时查看促销活动报表中的在线和离线量度。

如果您不导入具有关联 eVar 值的数据源量度，则您便无法查看按 eVar 划分的数据源量度。您而是只能查看总计量度。

## 交易 ID {#section_D9513C1204B7496C9B738C5B12CCCFC7}

交易 ID 用于将在线事件连接到离线事件。

## 识别数据源数据的有效日期范围 {#section_03AAB1291BDC4403BDC50905A78FDB71}

在定义数据源量度（自定义事件）和数据维度 (eVar) 之后，即可查看需要导入的数据源数据的日期范围。您无法导入现有报表数据范围以外的数据源。

例如，您无法在实施在线数据跟踪之前导入数据源数据。数据源数据应当按日划分。
