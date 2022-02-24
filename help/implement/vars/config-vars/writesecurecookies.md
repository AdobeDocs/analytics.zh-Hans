---
title: writeSecureCookies
description: 允许 AppMeasurement 使用“安全”属性设置 Cookie。
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '242'
ht-degree: 100%

---

# writeSecureCookies

`writeSecureCookies` 变量允许 AppMeasurement 为 Analytics 设置[安全 Cookie](https://en.wikipedia.org/wiki/Secure_cookie)。此设置适用于由 AppMeasurement 设置的访客 ID Cookie，以及您使用 `Util.CookieWrite()` 方法设置的 Cookie。它需要 AppMeasurement 2.18.0 或更高版本。

`writeSecureCookies` 仅适用于 AppMeasurement JavaScript 设置的 Cookie（`s_fid`、`s_cc` 和 `s_sq`）。通过联系 Adobe 客户关怀部门，可以将 `https` 响应所设置的 Cookie（`s_vi` 和 `s_ecid`）设置为“安全”。

在[此处](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=zh-Hans)了解有关 Analytics Cookie 的详细信息。

>[!IMPORTANT]
>
>如果启用 `writeSecureCookies` 变量，请确保网站上的所有内容都通过 HTTPS 协议来安全地提供。如果启用了此变量，并且您的页面上有不安全的内容，则 AppMeasurement 将不起作用。

## 使用 Adobe Experience Platform 中的标记的“编写安全 Cookie”

在配置 Adobe Analytics 扩展时，[!UICONTROL 编写安全 Cookie]是 [!UICONTROL Cookie] 折叠面板下的一个复选框。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
4. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 编写安全 Cookie] 复选框。

## AppMeasurement 和自定义代码编辑器中的 s.writeSecureCookies

`s.writeSecureCookies` 变量是一个布尔值，用于确定 AppMeasurement 在创建 Cookie 时是否为 Cookie 设置了安全属性。其默认值为 `false`。如果网站上的所有内容都安全，并且您希望 AppMeasurement 设置的 Cookie 具有“安全”属性，请将此变量设置为 `true`。

```js
s.writeSecureCookies = true;
```
