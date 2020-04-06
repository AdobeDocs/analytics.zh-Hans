---
title: cookieLifetime
description: 覆盖由 AppMeasurement 创建的 Cookie 的到期时间。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# cookieLifetime

由 AppMeasurement 设置的 Cookie 通常有 2 年期限。使用 `cookieLifetime` 变量可覆盖由 AppMeasurement 设置的 Cookie 的过期日期。

>[!NOTE] 此变量可影响独特访客计数和归因。设置此变量时请务必小心。

## Adobe Experience Platform Launch 中的“Cookie 生命周期”

Cookie Lifetime is a dropdown under the [!UICONTROL Cookies] accordion when configuring the Adobe Analytics extension.

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展开折叠 [!UICONTROL Cookies] 面板，该面板显示下拉 [!UICONTROL Cookie Lifetime] 菜单。

此下拉字段包含以下值：

* **默认**：Cookie 在 2 年后过期。
* **无**：AppMeasurement 未设置 Cookie。
* **会话**：Cookie 在访客会话结束时过期。
* **秒**：Cookie 在指定的秒数后过期。For example, setting this dropdown to [!UICONTROL Seconds] and placing `86400` into the custom field forces cookies to expire after exactly 24 hours.

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.cookieLifetime

`s.cookieLifetime` 变量是一个字符串，可确定由 AppMeasurement 设置的 Cookie 的到期日期。

* 如果设置为 `SESSION`，则由 AppMeasurement 设置的 Cookie 将在浏览器会话完成后过期。
* 如果设置为 `NONE`，则 AppMeasurement 不会尝试设置 Cookie。
* 如果设置为一个整数字符串，则由 AppMeasurement 设置的 Cookie 将在指定的秒数后过期。

```js
// Expire cookies after each session
s.cookieLifetime = "SESSION";

// Expire cookies after exactly 24 hours
s.cookieLifetime = "86400";

