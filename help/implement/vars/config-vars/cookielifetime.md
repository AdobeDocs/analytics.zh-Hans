---
title: cookieLifetime
description: 覆盖由 AppMeasurement 创建的 Cookie 的有效期限。
feature: Appmeasurement Implementation
exl-id: 2cd64301-9f12-4e77-abae-af431e4b499d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 64%

---

# cookieLifetime

由 AppMeasurement 设置的 Cookie 通常有 2 年期限。使用 `cookieLifetime` 变量可覆盖由 AppMeasurement 设置的 Cookie 的过期日期。

>[!NOTE]
>
>此变量可影响独特访客计数和归因。设置此变量时请务必小心。

## 使用Web SDK的“Cookie生命周期”

Web SDK尚不提供对其设置的Cookie生命周期的自定义。

## 使用Adobe Analytics扩展的“Cookie生命周期”

“Cookie生命周期”是配置Adobe Analytics扩展时位于[!UICONTROL Cookie]折叠面板下的下拉列表。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开[!UICONTROL Cookie]折叠面板，这会显示[!UICONTROL Cookie生命周期]下拉列表。

此下拉列表包含以下值：

* **默认**：Cookie 在 2 年后过期。
* **无**：AppMeasurement 未设置 Cookie。
* **会话**：Cookie 在访客会话结束时过期。
* **秒**：Cookie 在指定的秒数后过期。例如，将此下拉列表设置为[!UICONTROL 秒]并将`86400`放入自定义字段会强制Cookie在24小时后过期。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.cookieLifetime

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
