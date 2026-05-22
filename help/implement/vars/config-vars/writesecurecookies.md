---
title: writeSecureCookies
description: 允许 AppMeasurement 使用“安全”属性设置 Cookie。
feature: Appmeasurement Implementation
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/Eifs1WrhCzcOdHJ2HJADqZrIkNFgC7h76do3W56otjA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 278
ht-degree: 77%

---

# writeSecureCookies

`writeSecureCookies` 变量允许 AppMeasurement 为 Analytics 设置[安全 Cookie](https://en.wikipedia.org/wiki/Secure_cookie)。 此设置适用于由 AppMeasurement 设置的访客 ID Cookie，以及您使用 `Util.CookieWrite()` 方法设置的 Cookie。 它需要 AppMeasurement 2.18.0 或更高版本。

`writeSecureCookies` 仅适用于 AppMeasurement JavaScript 设置的 Cookie（`s_fid`、`s_cc` 和 `s_sq`）。 通过联系 Adobe 客户关怀部门，可以将 `https` 响应所设置的 Cookie（`s_vi` 和 `s_ecid`）设置为“安全”。

在[此处](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=zh-Hans)了解有关 Analytics Cookie 的详细信息。

>[!WARNING]
>
>如果启用 `writeSecureCookies` 变量，请确保网站上的所有内容都通过 HTTPS 协议来安全地提供。 如果启用了此变量，并且您的页面上有不安全的内容，则数据收集无法正常运行。

## 在Web SDK中使用安全Cookie

如果您的网站使用HTTPS协议，则会为Web SDK设置的所有Cookie设置“安全”属性。

## 使用Adobe Analytics扩展编写安全Cookie

在配置 Adobe Analytics 扩展时，[!UICONTROL 编写安全 Cookie]是 [!UICONTROL Cookie] 折叠面板下的一个复选框。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;]**配置**[!UICONTROL &#x200B;按钮。
4. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 编写安全 Cookie] 复选框。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.writeSecureCookies

`s.writeSecureCookies` 变量是一个布尔值，用于确定 AppMeasurement 在创建 Cookie 时是否为 Cookie 设置了安全属性。 其默认值为 `false`。 如果网站上的所有内容都安全，并且您希望 AppMeasurement 设置的 Cookie 具有“安全”属性，请将此变量设置为 `true`。

```js
s.writeSecureCookies = true;
```
