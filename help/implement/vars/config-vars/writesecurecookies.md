---
title: writeSecureCookies
description: 允许 AppMeasurement 使用“安全”属性设置 Cookie。
translation-type: tm+mt
source-git-commit: defb701d01747685a421b89a553f47efe40f1432
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 86%

---


# writeSecureCookies

`writeSecureCookies` 变量允许 AppMeasurement 为 Analytics 设置[安全 Cookie](https://en.wikipedia.org/wiki/Secure_cookie)。此设置适用于由 AppMeasurement 设置的访客 ID Cookie，以及您使用 `Util.CookieWrite()` 方法设置的 Cookie。它需要 AppMeasurement 2.18.0 或更高版本。

>[!IMPORTANT]
>
> 如果启用 `writeSecureCookies` 变量，请确保网站上的所有内容都通过 HTTPS 协议来安全地提供。如果启用了此变量，并且您的页面上有不安全的内容，则 AppMeasurement 将不起作用。

## 在 Adobe Experience Platform Launch 中编写安全 Cookie

[!UICONTROL 配置Adobe Analytics扩展] 时，“Cookie”折叠 [!UICONTROL 面板下] ,“编写安全Cookie”是一个复选框。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
4. 展开Cookies [!UICONTROL 折叠面板] ，该面板显示“写入安 [!UICONTROL 全cookies”复] 选框。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.writeSecureCookies

`s.writeSecureCookies` 变量是一个布尔值，用于确定 AppMeasurement 在创建 Cookie 时是否为 Cookie 设置了安全属性。其默认值为 `false`。如果网站上的所有内容都安全，并且您希望 AppMeasurement 设置的 Cookie 具有“安全”属性，请将此变量设置为 `true`。

```js
s.writeSecureCookies = true;
```
