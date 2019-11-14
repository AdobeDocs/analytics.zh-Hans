---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# transactionID

[!UICONTROL 集成数据源使用交易 ID 将离线数据绑定至在线交易（如在线生成的商机或购买）。]

<!-- 

transactionID.xml

 -->

每个发送到 Adobe 的唯一 *`transactionID`* 均会被记录，以备该交易离线信息的[!UICONTROL 数据源]上载。请参阅[数据源](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | xact | 不适用 | "" |

**启用交易 ID 存储** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

在记录 *`transactionID`* 值之前，必须为报表包管理器中选中的报表包启用[!UICONTROL 交易 ID 存储]。此设置位于

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

要查看是否为报表包启用了 *`transactionID Storage`*，请转到

```
Analytics > Admin > Data Sources > Manage
```

**语法和可能值** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

*`transactionID`* 只能包含字母数字字符。如果在一次点击中记录多个 [!UICONTROL transactionID]，可使用逗号分隔多个值。

**示例** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**缺陷、问题和提示** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* 如果未启用 *`transactionID`* 记录，则 *`transactionID`* 的值将会丢失，无法与[!UICONTROL 集成数据源]一起使用。确保在设置了 *`transactionID`* 的页面上设置转化变量或事件（eVar 或事件变量）。否则，将不会为 *`transactionID`*.

* 如果您要记录多个系统（例如购买和商机）的 [!UICONTROL transactionIDs]，请确保 *`transactionID`* 中的值始终是唯一的。可通过向 ID 添加前缀（例如 lead_1234 和 purchase_1234）来达到这一目的。如果某个独特 *`transactionID`* 出现两次，则[!UICONTROL 集成数据源]不能按预期工作（[!UICONTROL 数据源]数据将绑定到错误的数据）。

* 默认情况下，*`transactionID`* 值将会保留 90 天。如果离线互动过程的时间超过 90 天，请联系客户关怀延长该期限。

> [!NOTE]*`transactionID`* 变量可以包含逗号以外的任何字符。它应在指定字符限制（100 字节）的相同位置。如果使用多字节字符，则必须启用多字节字符支持，以避免 *`transactionID`*。
