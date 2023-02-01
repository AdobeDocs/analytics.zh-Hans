---
title: 使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics
description: 使用 Adobe Experience Platform 数据收集中的 Mobile SDK 扩展将数据发送到 Adobe Analytics。
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 28%

---

# 使用 Adobe Experience Platform Mobile SDK 实施 Adobe Analytics

Adobe Experience Platform Mobile SDK 有助于在您的移动应用程序中支持 Adobe 的 Experience Cloud 解决方案和服务。 它适用于Android™、iOS和各种跨平台开发框架。 通过 Adobe Experience Platform 数据收集处理配置。
>[!IMPORTANT]
>
>Adobe Experience Platform 数据收集中还提供了 Adobe Analytics 扩展。如果安装此扩展，则不会利用 XDM 或 Edge Network。

## Adobe Experience Platform SDK

实施任务的高级概述：

![Adobe Analytics使用Analytics扩展工作流](../../assets/mobilesdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任务</b></th><th style="width:35%"><b>更多信息</b></th>
</tr>

<tr>
<td>1</td>
<td>确保您 <b>定义了报表包</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">报表包管理器</a></td>
</tr>

<tr>
<td>2</td>
<td><b>设置架构和数据集</b>. 为了标准化数据收集以在利用Adobe Experience Platform的应用程序中使用，Adobe创建了公开且有文档记录的标准Experience Data Model(XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hans">架构UI概述</a> 和 <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh_Hans">数据集UI概述</a></td>
</tr>

<tr>
<td>3</td>
<td><b>配置数据流</b>. 数据流表示实施Adobe Experience Platform Web SDK时的服务器端配置。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">配置数据流<a></td> 
</tr>

<td>4</td>
<td><b>添加Adobe Analytics服务</b> 到您的数据流。 该服务控制数据是否以及如何发送到Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">将Adobe Analytics服务添加到数据流</a></td>
</tr>

<tr>
<td>5</td>
<td><b>创建移动资产</b>. 资产是一个容器，可在其中填充扩展、规则、数据元素和库。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">设置移动资产</a></tr>

<tr>
<td>6</td>
<td><b>安装Adobe Experience Platform Edge Network扩展</b> 在移动标记属性中，并在扩展中配置数据流。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform边缘网络</a>
</tr>

<tr>
<td>7</td>
<td><b>在您的应用程序中使用代码</b> 注册必要的扩展并加载标记配置。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">设置配置</a></td>
</tr>

<tr>
<td>8</td>
<td><b>实施和测试功能</b> 在应用程序中使用标记的数据元素、规则、其他扩展和SDK API调用的组合。 Inspect、验证和调试移动应用程序的数据收集和体验。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">使用示例应用程序</a>
</tr>

<tr>
<td>9</td>
<td><b>扩展并验证移动设备应用程序实施</b> 然后再推出生产。</td>
<td></td> 
</tr>

</table>


## Adobe Analytics 扩展.

实施任务的高级概述：

![Adobe Analytics使用Analytics扩展工作流](../../assets/mobilesdk-analytics-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任务</b></th><th style="width:35%"><b>更多信息</b></th>
</tr>

<tr>
<td>1</td>
<td>确保您 <b>定义了报表包</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">报表包管理器</a></td>
</tr>

<tr>
<td>2</td>
<td><b>设置架构和数据集</b>. 为了标准化数据收集以在利用Adobe Experience Platform的应用程序中使用，Adobe创建了公开且有文档记录的标准Experience Data Model(XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hans">架构UI概述</a> 和 <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh_Hans">数据集UI概述</a></td>
</tr>

<tr>
<td>3</td>
<td><b>安装Adobe Analytics扩展</b> 在移动标记属性中，并配置扩展以指向您的报表包。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Adobe Analytics移动资产扩展</a>
</tr>

<tr>
<td>4</td>
<td><b>在您的应用程序中使用代码</b> 注册必要的扩展并加载标记配置。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">设置配置</a></td>
</tr>

<tr>
<td>5</td>
<td><b>实施和测试功能</b> 在应用程序中使用标记的数据元素、规则、其他扩展和SDK API调用的组合。 Inspect、验证和调试移动应用程序的数据收集和体验。</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">使用示例应用程序</a>
</tr>

<tr>
<td>6</td>
<td><b>扩展并验证移动设备应用程序实施</b> 然后再推出生产。</td>
<td></td> 
</tr>

</table>

## 其他资源

- [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#?lang=zh-Hans)

- [移动 SDK 文档](https://developer.adobe.com/client-sdks/documentation/)



