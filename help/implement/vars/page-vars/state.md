---
title: 州
description: （已停用）填充了不再可用的“访客所在州报表”。
feature: Appmeasurement Implementation
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
TQID: https://experienceleague.adobe.com/3GhnJJj6gxEt0Qiefd4siS6-YzDbOw4hdY4IsNhwYDU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 87%

---

# 州

>[!IMPORTANT]
>
>此变量已停用，且在 Analysis Workspace 中不是可用维度。 请改用[美国州](/help/components/dimensions/us-states.md)维度，AppMeasurement会根据访客的位置自动收集该维度。

在 Adobe Analytics 的早期版本中，访客在零售网站上填写送货信息时，会使用 `state` 变量。 它的功能与 prop 相同，但在 Analysis Workspace 中不可用。

## 使用 Adobe Analytics 扩展程序的州

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置州。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 州]部分。

您可以将州设置为任何字符串值或数据元素。

## AppMeasurement 和 Analytics 扩展自定义代码编辑器中的 s.state

`s.state` 变量是一个字符串，通常包含访客所在州或省份。 完整的州名称或双字母代码均有效。 其值的最大长度为 50 字节；超出此长度的值会被截断。 其默认值是空字符串。

```js
s.state = "Utah";
```
