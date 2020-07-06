---
title: 事件序列化
description: 帮助删除网站上的重复量度。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 100%

---


# 事件 ID 序列化

事件序列化是实施措施以防止重复事件进入 Analytics 报告的过程。如果您不希望量度由于访客刷新页面而虚增，删除重复事件很重要。

>[!NOTE]
>
>数据源不支持事件序列化或删除重复事件。

## 设置事件序列化

您必须先在报表包设置中将事件的[!UICONTROL 独特事件记录]设置为[!UICONTROL 使用事件 ID]。请参阅管理员用户指南中的[成功事件](/help/admin/admin/c-success-events/success-event.md)。

使用事件 ID 时，会在以下级别进行重复数据删除：

* 每个变量都使用自己的表进行重复数据删除。例如，`event1:ABC` 和 `event2:ABC` 都被计入到报表中。
* 可在所有访客中进行重复数据删除。如果访客 A 发送 `event1:ABC`，然后访客 B 也发送 `event1:ABC`，则 Adobe 会忽略访客 B 的第二个实例。
* 重复数据删除不会过期。如果访客发送 `event1:ABC`，然后 2 年后返回并再次发送 `event1:ABC`，则 Adobe 将忽略第二个实例。

>[!TIP]
>
> 如果要删除重复的 [`purchase`](event-purchase.md) 事件，请改用 [`purchaseID`](../purchaseid.md) 变量。

## 在 Adobe Experience Platform Launch 中使用事件 ID

您可以在配置 Analytics 扩展时（全局变量）设置事件 ID 字段，也可以根据规则执行此操作。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 事件]部分，其中每个事件都包含一个[!UICONTROL 事件 ID] 字段。

有效值是长度不超过 20 字节的字母数字字符。

## 在 AppMeasurement 和 Launch 自定义代码编辑器中使用事件 ID

事件序列化是 `s.events` 变量的一部分。在字符串中使用冒号为每个事件分配一个 ID。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

如果某个事件已启用序列化，但不包含序列化 ID，则始终会计算该事件。
