---
title: transactionID
description: 使用此变量将联机和脱机数据链接在一起。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# transactionID

该变 `transactionID` 量可唯一标识事务，以便点击可以绑定到通过数据源上传的数据。 如果您希望使用来自其他渠道的数据并将其链接到通过AppMeasurement收集的数据，则此变量很有价值。

> [!NOTE] 在使用此变  量之前，请确保在报表包中启用了事务ID存储。 See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

在设置点 `transactionID` 击时，Adobe会对在该时间点设置或保留的所有Analytics变量进行“快照”。 通过数据源上传的具有匹配事务ID的数据将永久绑定到这些变量值。

默认情况下，Adobe会记住所有交易ID值（已链接和未链接），时间最长为90天。 如果您的线下互动过程超过90天，请联系客户关怀延长此限制。

## Adobe Experience Platform Launch中的事务ID

您可以在配置Analytics扩展（全局变量）时或根据规则设置事务ID。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“事 [!UICONTROL 务ID] ”部分。

您可以将事务ID设置为任何字符串值，包括数据元素。

## AppMeasurement中的s.transactionID和启动自定义代码编辑器

变 `s.transactionID` 量是包含事务的唯一标识符的字符串。 有效值包括长度不超过100字节的字母数字字符。 其默认值是空字符串。

```js
s.transactionID = "ABC123";
```

如果您有多个用于点击的事务ID，则可以用逗号分隔每个事务ID。 多个事务ID仍受100字节限制。

```js
s.transactionID = "ABC123,XYZ456";
```

> [!NOTE] 如果您使用此变量集成多个脱机渠道，请确保不同渠道不会与交易ID重叠。 例如，如果呼叫中心交易ID值为，而销售线索交易ID `1234` 值为，则它们可能会发生冲 `1234`突并导致意外结果。 确保每个脱机渠道的交易ID都包含唯一的格式，并在必要时加以区分。 例如，在数据源和AppMeasurement中将呼叫中 `call_1234` 心交易ID设置为，并将 `lead_1234` 销售线索交易ID设置为。
