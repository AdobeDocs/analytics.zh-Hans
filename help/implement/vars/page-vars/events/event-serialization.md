---
title: 事件序列化
description: 帮助消除网站上的重复指标。
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# 事件ID序列化

事件序列化是实施措施以防止重复事件进入 Analytics 报告的过程。如果您不希望访客刷新页面而夸大指标，重复数据消除很重要。

> [!NOTE]数据源不支持事件序列化或删除重复事件。

## 设置事件序列化

必须首先在报告包设置中将活 [!UICONTROL 动的唯一活动录制][!UICONTROL 设置为使用活动ID] 。 See [Success Events](../../../../admin/admin/c-success-events/success-event.md) in the Admin user guide.

使用事件ID时，重复数据消除会发生在以下级别：

* 每个变量都使用自己的表进行重复数据消除。 例如，和 `event1:ABC` 都 `event2:ABC` 计入报告中。
* 重复数据消除功能可跨所有访客实现。 如果访客A发送， `event1:ABC` 则访客B也发送， `event1:ABC`则Adobe会忽略访客B的第二个实例。
* 重复数据消除不会过期。 如果访客发送 `event1:ABC` 后在2年后返回并再次发送， `event1:ABC` 则Adobe将忽略第二个实例。

> [!TIP] 如果要消除事件重复项， `purchase` 请改用 `purchaseID` 变量。

## 在Adobe Experience Platform Launch中使用活动ID

您可以在配置Analytics扩展时（全局变量）设置事件ID字段，也可以设置为规则中的操作。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“ [!UICONTROL 事件] ”部分，其中每个事件都包含一 [!UICONTROL 个“事件ID] ”字段。

有效值是长度不超过20字节的字母数字字符。

## 在AppMeasurement和Launch自定义代码编辑器中使用事件ID

事件序列化是变量的一 `s.events` 部分。 使用字符串中的冒号为每个事件分配一个ID。

```js
// Assign custom ID serialization to a single value
s.events = "event1:ABC123";

// Assign custom ID serialization to multiple values
s.events = "event1:ABC123,event2:ABC123";
```

如果某个事件已启用序列化，但不包含序列化ID，则始终会计算该事件。
