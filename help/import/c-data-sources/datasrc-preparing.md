---
description: 为使用数据源而采取的准备步骤。
subtopic: Data sources
title: 准备使用数据源
topic: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 准备使用数据源

为使用数据源而采取的准备步骤。

* [识别和命名指标](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [标识数据维度](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [促销活动跟踪代码](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [交易 ID](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [确定数据源数据的有效日期范围](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## 识别和命名指标 {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

了解数据源中包含的量度或度量很重要，例如 *`Off-line Sales Revenue by Product`*、*`Returns by Product`* 或 *`Ad Impressions by Campaign`*。这些是您可以与报表度量(事件、prop和eVar)关联的名称。

在为数据源数据确定适当的度量到事件映射后，使用与关联的数据源度量相应的描述性名称重命名事件。

请参 [阅管理工具帮助](https://marketing.adobe.com/resources/help/zh_CN/reference/success_event.html) 中的成功事件。

>[!NOTE] Adobe 强烈建议结合使用新的空事件与数据源数据，但在极少数情况下也可以使用预先存在的事件。

## 标识数据维度 {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

识别和收集要用于细分通过数据源导入的指标的数据（报告）。 此数据称为 *`data dimensions`*。

例如，如果数据源量度测量广告印象，则您的数据维度可能是活动跟踪代码。 如果您在评估离线销售，则可能希望使用产品代码（或SKU）作为数据维度。

您可以为一个量度定义多个数据维，但每个量度必须为每个关联的数据维提供相关值或值组合。 例如，如果您导入离线销售量度并将其与数据维关联 *`Product`* , *`Partner`* 则离线销售量度必须与产品和合作伙伴的每个组合相关（例如，总收入）。

>[!NOTE] 可能会导入无法按任何数据维度划分的总计量度。

在定义要与数据源一起使用的数据维后，通过将维数据映射到变量，将维数据集成到营销报告中。 使用标准报表（例如，产品、跟踪代码、搜索关键字）或转化流量变量(eVar)。

使用eVar时，您可以使用现有eVar或新eVar作为数据维度。 在选择eVar以从数据源接收数据维后，请确保对它们进行相应的命名。

请参 [阅Analytics帮助](https://marketing.adobe.com/resources/help/zh_CN/reference/success_event.html) 中的成功事件。

## 促销活动跟踪代码 {#section_468222796FF449ABAA90D88EB3264CB1}

除了导入成功事件外，您还可以选择导入关联的eVar值。 例如，如果您使用活动跟踪代码跟踪在线活动，并且脱机量度具有活动跟踪代码，则可以导入包含活动跟踪代码的量度。 此方法允许您在视图报告中活动线上和线下指标。

如果不导入具有关联eVar值的“数据源”量度，则无法视图按eVar划分的“数据源”量度。 相反，您只能看到“总量度”。

## 交易 ID {#section_D9513C1204B7496C9B738C5B12CCCFC7}

交易ID用于将联机事件连接到脱机事件。

## 确定数据源数据的有效日期范围 {#section_03AAB1291BDC4403BDC50905A78FDB71}

在定义数据源量度(自定义事件)和数据维度(eVar)后，查看要导入的数据源数据的日期范围。 不能导入超出现有报告数据范围的数据源。

例如，在实施在线数据跟踪之前，无法从导入数据源数据。 数据源数据应按天细分。
