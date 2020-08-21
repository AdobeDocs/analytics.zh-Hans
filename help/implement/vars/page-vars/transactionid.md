---
title: transactionID
description: 使用此变量将在线和离线数据链接在一起。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---


# transactionID

`transactionID` 变量可唯一地标识交易，以便将点击绑定到通过数据源上传的数据。如果您希望使用其他渠道的数据并将其链接到通过 AppMeasurement 收集的数据，则此变量很有用。

>[!NOTE]
>
>在使用此变量之前，请确保在报表包中启用了[!UICONTROL 交易 ID 存储]。有关详细信息，请参阅管理员用户指南中的[一般帐户设置](/help/admin/admin/general-acct-settings-admin.md)。

当您在点击上设置 `transactionID` 时，Adobe 会及时拍摄在该时间点设置或持久保留的所有 Analytics 变量的快照。通过数据源上传且具有匹配交易 ID 的数据将会永久绑定到这些变量值。

默认情况下，Adobe 最多可在 90 天内记住所有交易 ID 值（已链接和未链接）。如果离线互动过程的时间超过 90 天，请联系客户关怀延长该期限。

## Adobe Experience Platform Launch 中的交易 ID

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置交易 ID。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 交易 ID] 部分。

您可以将交易 ID 设置为任何字符串值，包括数据元素。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.transactionID

`s.transactionID` 变量是一个包含交易的唯一标识符的字符串。有效值包括长度不超过 100 字节的字母数字字符。其默认值是空字符串。

```js
s.transactionID = "ABC123";
```

如果一次点击涉及多个交易 ID，则可以用逗号分隔每个交易 ID。多个交易 ID 仍受最大长度为 100 字节的限制。

```js
s.transactionID = "ABC123,XYZ456";
```

>[!NOTE]
>
>如果您使用此变量集成多个离线渠道，请确保各个渠道不会与交易 ID 重叠。例如，如果呼叫中心交易 ID 值为 `1234`，而潜在销售顾客交易 ID 值为 `1234`，则它们可能会发生冲突并导致意外结果。确保每个离线渠道的交易 ID 都包含唯一的格式，并在必要时加以区分。例如，在数据源和 AppMeasurement 中将呼叫中心交易 ID 设置为 `call_1234`，并将潜在销售顾客交易 ID 设置为 `lead_1234`。
