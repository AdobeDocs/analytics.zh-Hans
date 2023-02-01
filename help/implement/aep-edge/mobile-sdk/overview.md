---
title: 使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics
description: 使用 Adobe Experience Platform 数据收集中的 Mobile SDK 扩展将数据发送到 Adobe Analytics。
source-git-commit: 5adc3fe1eab0a358573ebdc12e51c6753e85b14c
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 20%

---

# 使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics

Adobe Experience Platform Mobile SDK 有助于在您的移动应用程序中支持 Adobe 的 Experience Cloud 解决方案和服务。 它适用于Android™、iOS和各种跨平台开发框架。 通过 Adobe Experience Platform 数据收集处理配置。
>[!IMPORTANT]
>
>Adobe Experience Platform 数据收集中还提供了 Adobe Analytics 扩展。如果安装此扩展，则不会利用 XDM 或 Edge Network。

## Adobe Experience Platform SDK

实施任务的高级概述：

![Adobe Analytics使用Analytics扩展工作流](../../assets/mobilesdk-annotated.png)

| |任务 |更多信息 | |-|—|—| | 1 |确保您拥有 **定义了报表包**. | [报表包管理器](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **设置架构和数据集**. 为了标准化数据收集以在利用Adobe Experience Platform的应用程序中使用，Adobe创建了公开且有文档记录的标准Experience Data Model(XDM)。 | [设置架构和数据集](https://developer.adobe.com/client-sdks/documentation/getting-started/set-up-schemas-and-datasets/) | | 3 | **配置数据流**. 数据流表示实施Adobe Experience Platform Web SDK时的服务器端配置。 | [配置数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 4 | **添加Adobe Analytics服务** 到您的数据流。 该服务控制数据是否以及如何发送到Adobe Analytics。 | [将Adobe Analytics服务添加到数据流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 5 | **创建移动资产**. 资产是一个容器，可在其中填充扩展、规则、数据元素和库。 | [设置移动资产](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 6 | **安装Adobe Experience Platform Edge Network扩展** 在移动标记属性中，并在扩展中配置数据流。 | [Adobe Experience Platform边缘网络](https://developer.adobe.com/client-sdks/documentation/edge-network/) | | 7 | **在您的应用程序中使用代码** 注册必要的扩展并加载标记配置。 | [设置配置](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 8 | **实施和测试功能** 在应用程序中使用标记的数据元素、规则、其他扩展和SDK API调用的组合。 Inspect、验证和调试移动应用程序的数据收集和体验。 | [使用示例应用程序](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 9 | **扩展并验证移动设备应用程序实施** 然后再推出生产。 | |


## Adobe Analytics 扩展.

实施任务的高级概述：

![Adobe Analytics使用Analytics扩展工作流](../../assets/mobilesdk-analytics-annotated.png)

| |任务 |更多信息 | |-|—|—| | 1 |确保您拥有 **定义了报表包**. | [报表包管理器](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **创建移动资产**. 资产是一个容器，可在其中填充扩展、规则、数据元素和库。 | [设置移动资产](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 3 | **安装Adobe Analytics扩展** 在移动标记属性中，并配置扩展以指向您的报表包。 | [Adobe Analytics移动资产扩展](https://developer.adobe.com/client-sdks/documentation/adobe-analytics/) | | 4 | **在您的应用程序中使用代码** 注册必要的扩展并加载标记配置。 | [设置配置](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 5 | **实施和测试功能** 在应用程序中使用标记的数据元素、规则、其他扩展和SDK API调用的组合。 Inspect、验证和调试移动应用程序的数据收集和体验。 | [使用示例应用程序](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 6 | **扩展并验证移动设备应用程序实施** 然后再推出生产。 | |

## 其他资源

- [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#?lang=zh-Hans)

- [移动 SDK 文档](https://developer.adobe.com/client-sdks/documentation/)



