---
title: collectHighEntropyUserAgentHints
description: 使用 collectHighEntropyUserAgentHints 变量可确定 Adobe 是否将从 Chromium 浏览器（例如 Google Chrome 和 Microsoft Edge）请求高熵提示。
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/jipxox--J6tVTjpES3YuOTOqL-SXvCMLSvvbpj620Q4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 100%

---

# collectHighEntropyUserAgentHints

Adobe Analytics 使用高熵客户端提示来改进设备和浏览器识别。 自 2.23.0 版的 AppMeasurement.js 开始提供此选项。 请参阅[此概述和常见问题](/help/technotes/client-hints.md)以及 [Google 博文](https://web.dev/user-agent-client-hints/)，详细了解客户端提示。

## 使用 Web SDK 收集高熵提示

高熵客户端提示是 Web SDK 中的上下文类别的一部分。 有关更多详细信息，请参阅[配置 Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans)。

## 使用 Adobe Analytics Extension 收集高熵提示

**[!UICONTROL 收集高熵用户代理提示]**&#x200B;是配置 Adobe Analytics Extension 时“常规”折叠面板下的复选框。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/#/@adobepm/data-collection)。
1. 单击所需的[!UICONTROL 标记属性]。
1. 转至[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]。
1. 展开[!UICONTROL 常规]折叠面板，这将显示[!UICONTROL 收集高熵用户代理提示]复选框。 默认情况下，该复选框处于未选中状态。

## AppMeasurement 中的 collectHighEntropyUserAgentHints

`s.collectHighEntropyUserAgentHints` 变量确定 AppMeasurement 是否从 Chromium 浏览器（例如 Google Chrome 和 Microsoft Edge）请求高熵提示。 Adobe Analytics 使用这些提示来改进设备和浏览器识别。

如果将此变量设置为 `true`，则将从浏览器请求所有高熵提示。

```js
s.collectHighEntropyUserAgentHints = true;
```
