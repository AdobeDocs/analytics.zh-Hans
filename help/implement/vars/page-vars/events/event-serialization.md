---
title: 事件序列化
description: 帮助删除网站上的重复量度。
feature: Appmeasurement Implementation
exl-id: 54de0fd7-9056-44af-bd59-b8eb55fc816e
role: Admin, Developer
TQID: https://experienceleague.adobe.com/43YfbDVjSH7ZJ8kqlXwAnb8UsIEoG3Ei-NRnkLLW63Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 87%

---

# 事件 ID 序列化

事件序列化是实施措施以防止重复事件进入 Analytics 报告的过程。 如果您不希望量度由于访客刷新页面而虚增，删除重复事件很重要。

>[!NOTE]
>
>数据源不支持事件序列化或删除重复事件。

## 设置事件序列化

您必须先在报表包设置中将事件的[!UICONTROL 独特事件记录]设置为[!UICONTROL 使用事件 ID]。 请参阅《管理员用户指南》中的[成功事件](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)。

使用事件 ID 时，会在以下级别进行重复数据删除：

* 每个变量都使用自己的表进行重复数据删除。 例如，`event1:ABC` 和 `event2:ABC` 都被计入到报表中。
* 可在所有访客中进行重复数据删除。 如果访客 A 发送 `event1:ABC`，然后访客 B 也发送 `event1:ABC`，则 Adobe 会忽略访客 B 的第二个实例。
* 重复数据删除不会过期。 如果访客发送 `event1:ABC`，然后 2 年后返回并再次发送 `event1:ABC`，则 Adobe 将忽略第二个实例。

>[!TIP]
>
>如果要删除重复的 [`purchase`](event-purchase.md) 事件，请改用 [`purchaseID`](../purchaseid.md) 变量。

## 通过 Web SDK 使用事件 ID

如果使用&#x200B;[**XDM对象**](/help/implement/aep-edge/xdm-var-mapping.md)，则事件序列化使用所需事件的XDM字段`id`。 完整的 XDM 路径取决于要序列化的事件。

例如，如果要序列化购物车添加量度，请将`xdm.commerce.productListAdds.id`设置为所需的序列化值。 如果要序列化自定义事件20，请将`xdm._experience.analytics.event1to100.event20.id`设置为所需的序列化值。

如果使用&#x200B;[**数据对象**](/help/implement/aep-edge/data-var-mapping.md)，则事件序列化使用`data.__adobe.analytics.events`，遵循AppMeasurement字符串语法。

## 通过 Adobe Analytics 扩展使用事件 ID

您可以在配置 Analytics 扩展时（全局变量）设置事件 ID 字段，也可以根据规则执行此操作。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 事件]部分，其中每个事件都包含一个[!UICONTROL 事件 ID] 字段。

有效值是长度不超过 20 字节的字母数字字符。 如果输入的值超过 20 个字节，系统会将其截断为前 20 个字节。

## 在 AppMeasurement 和 Analytics 扩展自定义代码编辑器中使用事件 ID

事件序列化是 `s.events` 变量的一部分。 在字符串中使用冒号为每个事件分配一个 ID。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

如果某个事件已启用序列化，但不包含序列化 ID，则始终会计算该事件。
