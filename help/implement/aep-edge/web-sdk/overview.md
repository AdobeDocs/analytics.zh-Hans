---
title: 使用Adobe Experience Platform Web SDK实施Adobe Analytics
description: 使用Adobe Experience Platform数据收集中的Web SDK扩展将数据发送到Adobe Analytics。
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 33%

---


# 使用Adobe Experience Platform Web SDK实施Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) 发送数据到Adobe Analytics。 此实施方法通过将 [体验数据模型(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) 格式。

## 设置

要设置 Analytics 以接收 XDM 数据，请执行以下操作：

1. 安装并[配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans) [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hans)。

1. 确保将适用的报表包映射到您需要的数据。 XDM数据会自动从Adobe Experience Edge流向报表包。
