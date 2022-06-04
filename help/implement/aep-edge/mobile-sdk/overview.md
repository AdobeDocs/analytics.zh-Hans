---
title: 使用Adobe Experience Platform Mobile SDK实施Adobe Analytics
description: 使用Adobe Experience Platform数据收集中的Mobile SDK扩展将数据发送到Adobe Analytics。
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---


# 使用Adobe Experience Platform Mobile SDK实施Adobe Analytics

Adobe Experience Platform Mobile SDK可帮助在您的移动设备应用程序中为Adobe的Experience Cloud解决方案和服务提供支持。 它适用于Android、iOS和各种跨平台开发框架。 配置通过Adobe Experience Platform数据收集UI进行处理。

要使用Mobile SDK将数据发送到Adobe Experience Edge，请执行以下操作：

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection).
2. 从列表中选择所需的属性，或 [设置移动资产](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. 转到扩展选项卡，然后安装 [边缘网络的标识](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network) 扩展。
4. 安装 [Adobe Experience Platform边缘网络](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [配置数据流](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams)，将Adobe Analytics添加为指向所需报表包的服务。
6. [安装SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) 在您的移动设备应用程序上。

>[!IMPORTANT]
>
>数据收集UI中还提供了Adobe Analytics扩展。 如果安装此扩展，则不会利用XDM或边缘网络。
