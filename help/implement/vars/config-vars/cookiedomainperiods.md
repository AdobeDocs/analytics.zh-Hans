---
title: cookieDomainPeriods
description: 帮助 AppMeasurement 了解当您的域的后缀中有句点时，应使用哪个域来存储 Cookie。
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 43%

---


# cookieDomainPeriods

AppMeasurement 可通过检查域和域的后缀确定其 Cookie 位置。对于像 `example.com` 这样的域，AppMeasurement 会将 Cookie 设置到正确位置中。但是，对于其他域（如 `example.co.uk`），AppMeasurement 可能会错误地将 Cookie 设置到 `co.uk` 上。大多数浏览器会拒绝在此无效域上设置的 Cookie，而这会导致无法正确访客识别。

`cookieDomainPeriods` 变量会声明域后缀中含有额外的句点，从而可帮助 AppMeasurement 确定在何处设置 Analytics Cookie。此变量允许 AppMeasurement 处理域后缀中的额外句点，并在正确的位置设置 Cookie。

* 对于 `example.com` 或 `www.example.com` 等域，无需设置此变量。如果需要，可将此变量设置为 `"2"`。
* 对于 `example.co.uk` 或 `www.example.co.jp` 等域，将此变量设置为 `"3"`。


>[!IMPORTANT]
>
>此变量不考虑子域。例如，不要在示例 URL `store.toys.example.com` 上设置 `cookieDomainPeriods`。默认情况下，AppMeasurement 允许将 Cookie 存储在 `example.com` 上，甚至存储在具有许多子域的 URL 上。


## Cookie域名段、第三方Cookie和旧版访客识别

仅当您使用旧版Adobe Analytics访客识别(而不是推荐的Experience Cloud身份服务)时，的隐式或显式配置才会出现 `cookieDomainPeriods` 可能会对识别访客的方式产生影响，具体取决于是否阻止第三方Cookie。

下表说明了四种可能的情况。

| 场景 | `cookieDomainPeriods` 配置是…… | 第三方Cookie被阻止？ | 使用旧版Adobe Analytics访客识别服务时的结果 |
|:---:|---|---|---|
| 1 | <span style="color:green">正确</span> | 否 | 访客使用 `s_vi` Cookie，设置服务器端。 |
| 2 | <span style="color:green">正确</span> | 是 | 使用回退标识访客 `s_fid` Cookie，设置客户端（第一方页面域）。 |
| 3 | <span style="color:red">不正确</span> | 否 | 根据用户代理和IP地址的组合，使用回退标识符来标识访客。 <br/>AppMeasurement被迫将Cookie设置为第三方Cookie。<br/> 此 `s_vi` Cookie可能在以下情况下进行设置： `cookieDomainPeriods` 未正确传输。 |
| 4 | <span style="color:red">不正确</span> | 是 | 根据用户代理和IP地址的组合，使用回退标识符来标识访客。<br/>AppMeasurement被迫将Cookie设置为被阻止的第三方Cookie，因此不设置Cookie。 |

>[!CAUTION]
>
>您可能无意中配置了 `cookieDomainPeriods` <span style="color:red">不正确</span> (将其保留为默认值 `"2"`)，而使用域(如 `example.co.uk`. 这种隐含的不正确配置导致您在情景3或4之后识别访客。
>
>AppMeasurement版本2.26.x或更高版本配置 `cookieDomainPeriods` 自动使用正确的值，以便仅场景1或2。 当您更新到AppMeasurement版本2.26.x或更高版本时，虽然当前识别访客的方式不正确（场景3或4），但更新会产生重大影响。
>
>* 正在重置访客标识符，并且访客将显示为新访客。 无法将新活动绑定到先前的访客标识符。
>* 设置Cookie(例如，用于链接跟踪或Activity Map，`s_sq` cookie)，从而导致报表的突然差异。
>
>正确配置时 `cookieDomainPeriods` 将改进AppMeasurement和Analytics功能，因此建议您评估是否因升级AppMeasurement库而导致的更改而受到影响。
>
> 请参阅 [Analytics Cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=zh-Hans) 以详细了解CookieAppMeasurement使用的。

## 使用Web SDK的Cookie域名段

在没有此变量的情况下，Web SDK可以确定正确的Cookie存储域。

## 使用Adobe Analytics扩展的Cookie域名段

“域名段”是在配置 Adobe Analytics 扩展时显示在 [!UICONTROL Cookie] 折叠面板中的一个字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 域名段]字段。

仅当域的后缀中包含句点时，才会将此字段设置为 `3`。否则，可将此字段留空。

## 代码AppMeasurement和Analytics扩展自定义代码编辑器中的Cookie域名段

您可以设置 `cookieDomainPeriods` AppMeasurement变量，或者在Analytics扩展的自定义代码编辑器中。

`cookieDomainPeriods` 变量是一个字符串，一般而言，仅对于后缀中包含句点的域，才会将该变量设置为 `"3"`。其默认值是 `"2"`，该值适用于大多数域。

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
