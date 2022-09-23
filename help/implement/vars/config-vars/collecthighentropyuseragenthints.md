---
title: collectHighEntropyUserAgentHints
description: 使用collectHighEntropyUserAgentHints变量可确定Adobe是否将从Chromium浏览器(例如Google Chrome和Microsoft Edge)请求高熵提示。
source-git-commit: 0a23ad56a661a420dd44e2875c22927f9734dedf
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---


# collectHighEntropyUserAgentHints

Adobe Analytics使用高熵客户端提示来改进设备和浏览器标识。 有关客户端提示的更多信息，请参阅 [此概述和常见问题解答](/help/technotes/client-hints.md) 以及 [Google博客](https://web.dev/user-agent-client-hints/).

## 使用Web SDK收集高熵提示

高熵客户端提示是Web SDK中上下文类别的一部分。 请参阅 [配置平台Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) 以了解更多详细信息。

## 使用Adobe Analytics扩展收集高熵提示

**[!UICONTROL 收集高熵用户代理提示]** 是配置Adobe Analytics扩展时位于常规折叠面板下的复选框。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/#/@adobepm/data-collection) 使用您的Adobe ID凭据。

1. 单击所需的 [!UICONTROL 标记属性].

1. 转到 [!UICONTROL 扩展] ，然后单击 [!UICONTROL 配置] 在Adobe Analytics下。

1. 展开 [!UICONTROL 常规] 折叠面板，这会显示 [!UICONTROL 收集高熵用户代理提示] 复选框。 默认情况下，该复选框处于未选中状态。

## AppMeasurement中的collectHighEntropyUserAgentHints

的 `s.collectHighEntropyUserAgentHints` 变量可确定AppMeasurement是否从Chromium浏览器(例如Google Chrome和Microsoft Edge)请求高熵提示。 Adobe Analytics会使用这些提示来改进设备和浏览器标识。

如果设置为TRUE，则将从浏览器请求所有高熵提示。

`s.collectHighEntropyUserAgentHints = TRUE`

`s.collectHighEntropyUserAgentHints = FALSE`