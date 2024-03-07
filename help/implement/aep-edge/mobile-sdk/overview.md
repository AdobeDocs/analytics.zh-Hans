---
title: 使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics
description: 使用 Adobe Experience Platform 数据收集中的 Mobile SDK 扩展将数据发送到 Adobe Analytics。
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 97%

---

# 使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics

Adobe Experience Platform Mobile SDK 有助于在您的移动应用程序中支持 Adobe 的 Experience Cloud 解决方案和服务。 它可用于 Android™、iOS 和各种跨平台开发框架。 通过 Adobe Experience Platform 数据收集处理配置。

>[!IMPORTANT]
>
>Adobe Experience Platform 数据收集中还提供了 Adobe Analytics 扩展。如果安装此扩展，则不会利用 XDM 或 Edge Network。

## Adobe Experience Platform SDK

实施任务的高级概述：

![使用 Analytics 扩展工作流的 Adobe Analytics](../../assets/mobilesdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任务</b></th><th style="width:35%"><b>更多信息</b></th>
</tr>

<tr>
<td>1</td>
<td>确保您已<b>定义报告包</b>。</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">报告包管理器</a></td>
</tr>

<tr>
<td>2</td>
<td><b>设置架构。</b>。为了标准化数据收集以在利用 Adobe Experience Platform 的应用程序中使用，Adobe 创建了开放且公开记录的标准，即体验数据模型 (XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hans">架构UI概述</a></td>
</tr>

<tr>
<td>3</td>
<td><b>配置数据流</b>。 数据流表示实施 Adobe Experience Platform Web SDK 时的服务器端配置。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans">配置数据流<a></td> 
</tr>

<td>4</td>
<td><b>将 Adobe Analytics 服务</b>添加到您的数据流。 该服务控制数据是否以及如何发送到 Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">将 Adobe Analytics 服务添加到数据流</a></td>
</tr>

<tr>
<td>5</td>
<td><b>创建移动属性</b>。 属性是您填充扩展、规则、数据元素和库的容器。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">设置移动属性</a></tr>

<tr>
<td>6</td>
<td><b>在移动标记属性中安装 Adobe Experience Platform Edge Network 扩展</b>，并在扩展中配置数据流。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>7</td>
<td><b>在您的应用程序中使用代码</b>来注册必要的扩展并加载您的标记配置。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">设置配置</a></td>
</tr>

<tr>
<td>8</td>
<td><b>在您的应用中结合标记的数据元素、规则、附加扩展和 SDK API 调用来实施和测试功能</b>。 检查、验证和调试移动应用程序的数据收集和体验。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">使用示例应用程序</a>
</tr>

<tr>
<td>9</td>
<td><b>将您的移动应用程序实施</b>推向生产环境之前，对其进行扩展和验证。</td>
<td></td> 
</tr>

</table>


## Adobe Analytics 扩展.

实施任务的高级概述：

![使用 Analytics 扩展工作流的 Adobe Analytics](../../assets/mobilesdk-analytics-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任务</b></th><th style="width:35%"><b>更多信息</b></th>
</tr>

<tr>
<td>1</td>
<td>确保您已<b>定义报告包</b>。</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">报告包管理器</a></td>
</tr>

<tr>
<td>2</td>
<td><b>设置架构</b>. 为了标准化数据收集以在利用 Adobe Experience Platform 的应用程序中使用，Adobe 创建了开放且公开记录的标准，即体验数据模型 (XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hans">架构UI概述</a></td>
</tr>

<tr>
<td>3</td>
<td><b>在移动标记属性中安装 Adobe Analytics 扩展</b>，并将扩展配置为指向您的报告包。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">用于移动属性的 Adobe Analytics 扩展</a>
</tr>

<tr>
<td>4</td>
<td><b>在您的应用程序中使用代码</b>来注册必要的扩展并加载您的标记配置。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">设置配置</a></td>
</tr>

<tr>
<td>5</td>
<td><b>在您的应用中结合标记的数据元素、规则、附加扩展和 SDK API 调用来实施和测试功能</b>。 检查、验证和调试移动应用程序的数据收集和体验。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">使用示例应用程序</a>
</tr>

<tr>
<td>6</td>
<td><b>将您的移动应用程序实施</b>推向生产环境之前，对其进行扩展和验证。</td>
<td></td> 
</tr>

</table>

## 其他资源

- [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#?lang=zh-Hans)

- [移动 SDK 文档](https://developer.adobe.com/client-sdks/documentation/)
