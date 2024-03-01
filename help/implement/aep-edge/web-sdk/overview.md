---
title: 使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics
description: 使用 Adobe Experience Platform 数据收集中的 Web SDK 扩展将数据发送到 Adobe Analytics。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 76%

---

# 使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) 向 Adobe Analytics 发送数据。 此实施方法通过将[体验数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) 转换为 Analytics 使用的格式来工作。

您可以使用将数据直接发送到Experience Edge。 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/overview.html?lang=en)或通过Tags中的Web SDK扩展执行的其他操作。

## Web SDK

实施任务的高级概述：

![如何使用Web SDK工作流实施Adobe Analytics，如本节所述。](../../assets/websdk-annotated.png)

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
<td><b>创建数据层</b>来管理您网站上的数据跟踪。</td>
<td><a href="../../prepare/data-layer.md">创建数据层</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>安装预构建的独立版本</b>。 您可以直接在页面上引用 CDN 上的库 (<code>alloy.js</code>) 或下载并托管在您自己的基础设施上。 或者，您可以使用 NPM 包。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hans#option-2%3A-installing-the-prebuilt-standalone-version">安装预构建的独立版本</a>和<a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hans#option-3%3A-using-the-npm-package">使用 NPM 包</a></td>
</tr>

<tr>
<td>5</td>
<td><b>配置数据流</b>。 数据流表示实施 Adobe Experience Platform Web SDK 时的服务器端配置。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans">配置数据流<a></td> 
</tr>

<td>6</td>
<td><b>将 Adobe Analytics 服务</b>添加到您的数据流。 该服务控制是否以及如何将数据发送到Adobe Analytics，以及具体将数据发送到哪些报表包。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans#analytics">将 Adobe Analytics 服务添加到数据流</a></td>
</tr>

<tr>
<td>7</td>
<td><b>配置 Web SDK</b>。 确保使用数据流ID(以前称为边缘配置ID (<code>edgeConfigId</code>)，组织id (<code>orgId</code>)，以及其他可用选项。 确保正确映射变量。 </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans">配置Web SDK</a><br/><a href="https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en">Analytics变量映射</a><br/><a href="https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=en">手动映射变量</a></td>
</tr>

<tr>
<td>8</td>
<td><b>执行命令</b>和/或<b>跟踪事件</b>。 在您的网页上实施基础代码后，您可以开始使用 SDK 执行命令和跟踪事件。
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=zh-Hans">执行命令</a>和<a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=zh-Hans">跟踪事件</a></td>
</tr>

<tr>
<td>9</td><td><b>将您的实施</b>推向生产环境之前，对其进行扩展和验证。</td><td></td> 
</tr>
</table>


## Web SDK 扩展

实施任务的高级概述：

![如何使用Web SDK扩展工作流实施Adobe Analytics，如本节所述。](../../assets/websdk-extension-annotated.png)

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
<td><b>创建数据层</b>来管理您网站上的数据跟踪。</td>
<td><a href="../../prepare/data-layer.md">创建数据层</a></td>
</tr>

<tr>
<td>4</td>
<td><b>配置数据流</b>。 数据流表示实施 Adobe Experience Platform Web SDK 时的服务器端配置。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans">配置数据流<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>将 Adobe Analytics 服务</b>添加到您的数据流。 该服务控制是否以及如何将数据发送到Adobe Analytics，以及具体将数据发送到哪些报表包。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hans#analytics">将 Adobe Analytics 服务添加到数据流</a></td>
</tr>

<tr>
<td>6</td>
<td><b>创建标记属性</b>。属性是用于引用标记管理数据的总容器。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=zh-Hans#for-web">为 Web 创建或配置标签属性</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>在您的标记属性中安装和配置 Web SDK 扩展</b>。配置 Web SDK 扩展以将数据发送到在步骤 4 中配置的数据流。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=zh-Hans">Adobe Experience Platform Web SDK 扩展概述</a></td>
</tr>

<tr>
<td>8</td>
<td><b>迭代、验证并发布</b>到生产环境。 嵌入代码以将标记资产包含到网站页面。 然后使用数据元素、规则等来定制您的实施。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=en#embed-code">嵌入代码</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hans">发布概述</a></td>
</tr>

</table>


## 其他资源

标记可高度定制。详细了解如何通过在实施中包含正确的数据来充分利用 Adobe Analytics。

- [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#?lang=zh-Hans)：了解界面的使用方式和可用的扩展。

- [Adobe Experience Platform Web SDK 文档](https://experienceleague.adobe.com/docs/web-sdk.html?lang=zh-Hans)
