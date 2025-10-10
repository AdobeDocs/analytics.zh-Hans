---
title: cookieDomainPeriods
description: （已弃用）帮助AppMeasurement确定当网站的顶级域包含句点时，要将Cookie存储在何处。
feature: Appmeasurement Implementation
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 18%

---

# cookieDomainPeriods

>[!IMPORTANT]
>此变量已弃用。 如果您使用以下任一项：
>
>* AppMeasurement v2.26.x或更高版本
>* Adobe Analytics扩展v1.9.4或更高版本
>* Adobe Experience Cloud ID服务
>
>此变量不执行任何操作，因为适用的库会自动检测要设置Cookie的域。

`cookieDomainPeriods`变量指示顶级域中有一个额外的句点，从而帮助AppMeasurement确定在何处设置Analytics Cookie。 此变量允许AppMeasurement处理顶级域中的额外句点，并在正确的位置设置Cookie。 如果您网站的顶级域不包含额外的句点，则不需要此变量。

* 对于 `example.co.uk` 或 `www.example.co.jp` 等域，将此变量设置为 `"3"`。
* 对于类似`example.nsw.gov.au`的域，将此变量设置为`"4"`。
* 对于`example.com`或`products.example.org`等域，省略设置此变量或将其设置为`"2"`。

>[!TIP]
>
>此变量不考虑子域。例如，不要在示例 URL `store.toys.example.com` 上设置 `cookieDomainPeriods`。AppMeasurement识别Cookie存储在`example.com`上，甚至存储在具有许多子域的URL上。

对于AppMeasurement v2.26.x或更高版本上的实施，[`s_ac`](https://experienceleague.adobe.com/zh-hans/docs/core-services/interface/data-collection/cookies/analytics) Cookie用于帮助自动确定正确的Cookie域。 库首先尝试写入包含两个域名的Cookie。 如果设置此Cookie失败，它会再次尝试，包括更多域周期，直到它成功。 一旦设置，此Cookie将立即删除。

## 使用Web SDK的Cookie域名段

Web SDK会自动确定设置Cookie的正确域。

## 使用Adobe Analytics扩展的Cookie域名段

**[!UICONTROL 域名段]**&#x200B;是配置Adobe Analytics扩展时位于[!UICONTROL Cookie]折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击所需的标记属性。
1. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
1. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 域名段]字段。

仅在包含句点的顶级域上将此字段设置为`3`。 否则，可将此字段留空。

## AppMeasurement和Analytics扩展自定义代码编辑器中的Cookie域名段

`cookieDomainPeriods`变量是一个字符串，通常设置为`"3"`，并且仅在包含句点的顶级域上设置。 其默认值为`"2"`，该值适用于大多数顶级域，如`.com`和`.org`。

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
