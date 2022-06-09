---
title: 使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics
description: 使用 Adobe Experience Platform 数据收集中的 Web SDK 扩展将数据发送到 Adobe Analytics。
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---


# 使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=zh-Hans) 向 Adobe Analytics 发送数据。 此实施方法通过将[体验数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) 转换为 Analytics 使用的格式来工作。

## 设置

要设置 Analytics 以接收 XDM 数据，请执行以下操作：

1. 安装并[配置](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans) [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hans)。

1. 确保将适用的报告包映射到所需的数据。XDM 数据会自动从 Adobe Experience Edge 流向报告包。
