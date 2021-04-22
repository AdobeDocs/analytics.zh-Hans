---
title: cookieLifetime
description: 覆盖由 AppMeasurement 创建的 Cookie 的到期时间。
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '229'
ht-degree: 100%

---

# cookieLifetime

由 AppMeasurement 设置的 Cookie 通常有 2 年期限。使用 `cookieLifetime` 变量可覆盖由 AppMeasurement 设置的 Cookie 的过期日期。

>[!NOTE]
>
>此变量可影响独特访客计数和归因。设置此变量时请务必小心。

## Adobe Experience Platform Launch 中的“Cookie 生命周期”

“Cookie 生命周期”是在配置 Adobe Analytics 扩展时显示在 [!UICONTROL Cookie] 折叠面板中的一个下拉列表。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
4. 展开 [!UICONTROL Cookie] 折叠面板，这会显示 [!UICONTROL Cookie 生命周期]下拉字段。

此下拉字段包含以下值：

* **默认**：Cookie 在 2 年后过期。
* **无**：AppMeasurement 未设置 Cookie。
* **会话**：Cookie 在访客会话结束时过期。
* **秒**：Cookie 在指定的秒数后过期。例如，如果将此下拉字段设置为[!UICONTROL 秒]，并将 `86400` 放入此自定义字段，则会强制 Cookie 在 24 小时后过期。

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
```
