---
title: 使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics
description: 使用 Adobe Experience Platform 数据收集中的 Mobile SDK 扩展将数据发送到 Adobe Analytics。
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 89%

---

# 使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics

Adobe Experience Platform Mobile SDK 有助于在您的移动应用程序中支持 Adobe 的 Experience Cloud 解决方案和服务。 它可用于 Android、iOS 和各种跨平台开发框架。 配置通过Adobe Experience Platform数据收集进行处理。

要使用 Mobile SDK 将数据发送到 Adobe Experience Edge，请执行以下操作：

1. 登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 从列表中选择所需的属性，或[设置移动属性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。
3. 前往“拓展”选项卡，安装 [Edge Network 身份](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network)扩展。
4. 安装 [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension)。
5. [配置数据流](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams)，将 Adobe Analytics 添加为指向所需报告包的服务。
6. 在您的移动应用程序上[安装 SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk)。

>[!IMPORTANT]
>
>Adobe Experience Platform数据收集中还提供了Adobe Analytics扩展。 如果安装此扩展，则不会利用 XDM 或 Edge Network。
