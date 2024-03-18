---
title: referrer
description: 覆盖点击的自动收集的反向链接。
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 80%

---

# referrer

`referrer` 变量将覆盖报表中自动收集的反向链接。当反向链接可能丢失时，例如重定向访客或将访客临时转发给支付处理器时，此变量很有帮助。此变量有助于填充“反向链接”和“反向链接域”维度。

## 使用Web SDK的反向链接

反向链接映射到以下变量：

* [XDM对象](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.web.webReferrer.URL`
* [数据对象](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.referrer`

Web SDK自动包含 `web.webReferrer.URL` 每个已发送事件时（如果可用）。

## 使用Adobe Analytics扩展的反向链接

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置反向链接。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 设置 [!UICONTROL 扩展名] Adobe Analytics的下拉列表，以及 [!UICONTROL 操作类型] 到 [!UICONTROL 设置变量].
6. 找到[!UICONTROL 反向链接]部分。

您可以将反向链接设置为任何字符串值，包括数据元素。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.referrer

`s.referrer` 变量是一个包含上一页 URL 的字符串。此变量最多可存储 255 字节；大于 255 字节的值会被截断。AppMeasurement 会自动将此变量设置为 `document.referrer`；除非要覆盖自动收集的值，否则无需设置此变量。

```js
s.referrer = "https://example.com";
```

如果使用`digitalData` [数据层](../../prepare/data-layer.md)：

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>避免将此变量设置为非 URL 值。请勿剥离 URL 的协议。

## 示例

许多组织都会处理有关重定向的实施。如果您的网站可使用 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) 实用程序，则可以使用该实用程序从 URL 获取反向链接。确保您会对查询字符串中包含的任何值进行 URL 编码。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
