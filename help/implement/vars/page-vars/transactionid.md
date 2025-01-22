---
title: transactionID
description: 使用此变量将在线和离线数据链接在一起。
feature: Variables
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
role: Admin, Developer
source-git-commit: e281d43204e1c5b10508661f04b880125fe8671c
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 89%

---

# transactionID

`transactionID` 变量可唯一地标识交易，以便将点击绑定到通过数据源上传的数据。如果您希望使用其他渠道的数据并将其链接到通过 AppMeasurement 收集的数据，则此变量很有用。

>[!NOTE]
>
>在使用此变量之前，请确保在报表包中启用了[!UICONTROL 交易 ID 存储]。有关详细信息，请参阅《管理员用户指南》中的[一般帐户设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)。

当您在点击上设置 `transactionID` 时，Adobe 会及时拍摄在该时间点设置或持久保留的所有 Analytics 变量的快照。通过数据源上传且具有匹配交易 ID 的数据将会永久绑定到这些变量值。

Adobe最多可在25个月内记住所有交易ID值（已链接和未链接）。

## 使用 Web SDK 的交易 ID

交易ID映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.commerce.order.payments[0].transactionID`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.transactionID`或`data.__adobe.analytics.xact`

## 使用 Adobe Analytics 扩展的交易 ID

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置交易 ID。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 交易 ID] 部分。

您可以将交易 ID 设置为任何字符串值，包括数据元素。

## AppMeasurement 和 Analytics 扩展自定义代码编辑器中的 s.transactionID

`s.transactionID` 变量是一个包含交易的唯一标识符的字符串。有效值包括长度不超过 100 字节的字母数字字符。其默认值是空字符串。

```js
s.transactionID = "ABC123";
```

如果一次点击涉及多个交易 ID，则可以用逗号分隔每个交易 ID。多个交易 ID 仍受最大长度为 100 字节的限制。

```js
s.transactionID = "ABC123,XYZ456";
```

>[!TIP]
>
>如果您使用此变量集成多个离线渠道，请确保各个渠道不会与交易 ID 重叠。例如，如果呼叫中心交易 ID 值为 `1234`，而潜在销售顾客交易 ID 值为 `1234`，则它们可能会发生冲突并导致意外结果。确保每个离线渠道的交易 ID 都包含唯一的格式，并在必要时加以区分。例如，在数据源和 AppMeasurement 中将呼叫中心交易 ID 设置为 `call_1234`，并将潜在销售顾客交易 ID 设置为 `lead_1234`。
