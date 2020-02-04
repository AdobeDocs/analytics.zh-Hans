---
title: cookieLifetime
description: 覆盖AppMeasurement创建的Cookie的到期时间。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# cookieLifetime

由AppMeasurement设置的Cookie通常有2年的到期时间。 使用该 `cookieLifetime` 变量可覆盖由AppMeasurement设置的Cookie的过期日期。

> [!NOTE] 此变量会影响唯一访客计数和归因。 设置此变量时请务必小心。

## Adobe Experience Platform Launch中的Cookie生命周期

Cookie生命周期是配置Adobe Analytics扩展时 [!UICONTROL Cookies] accordion下的下拉菜单。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“扩 [!UICONTROL 展] ”选项卡，然后单击Adobe Analytics [!UICONTROL 下的] “配置”按钮。
4. 展开 [!UICONTROL Cookies折叠] ，该面板显示 [!UICONTROL Cookie生命周期下拉列表] 。

此下拉框包含以下值：

* **默认**:Cookie在2年后过期。
* **无**:AppMeasurement未设置cookie。
* **会话**:Cookie在访客会话结束时过期。
* **秒**:Cookie在指定的秒数过后过期。 例如，将此下拉列表设置为 [!UICONTROL 秒] ，并放入自定 `86400` 义字段会强制cookie在24小时后过期。

## s.cookieLifetime in AppMeasurement and Launch自定义代码编辑器

该 `s.cookieLifetime` 变量是一个字符串，它确定AppMeasurement设置的Cookie的到期日期。

* 如果设置为， `SESSION`则AppMeasurement设置的Cookie将在浏览器会话完成后过期。
* 如果设置为， `NONE`则AppMeasurement不会尝试设置cookie。
* 如果设置为整数字符串，则AppMeasurement设置的Cookie将在指定的秒数过后过期。

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

