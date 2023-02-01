---
title: 使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics
description: 使用 Adobe Experience Platform 数据收集中的 Web SDK 扩展将数据发送到 Adobe Analytics。
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 28%

---

# 使用 Adobe Experience Platform Web SDK 实施 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) 向 Adobe Analytics 发送数据。 此实施方法通过将[体验数据模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans) 转换为 Analytics 使用的格式来工作。

您可以使用Web SDK直接将数据发送到Experience Edge，或通过标记中的Web SDK扩展将数据发送到Experience Edge。

## Web SDK

实施任务的高级概述：

![使用Web SDK工作流实施Adobe Analytics](../../assets/websdk-annotated.png)

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
<td><b>创建数据层</b> 用于管理网站上数据的跟踪。</td>
<td><a href="../../prepare/data-layer.md">创建数据层</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>安装预建的独立版本</b>. 您可以引用库(<code>alloy.js</code>)，或在您自己的基础架构下载并托管CDN。 或者，您也可以使用NPM包。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version">安装预建的独立版本</a> 和 <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package">使用NPM包</a></td>
</tr>

<tr>
<td>5</td>
<td><b>配置数据流</b>. 数据流表示实施Adobe Experience Platform Web SDK时的服务器端配置。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">配置数据流<a></td> 
</tr>

<td>6</td>
<td><b>添加Adobe Analytics服务</b> 到您的数据流。 该服务控制数据是否以及如何发送到Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">将Adobe Analytics服务添加到数据流</a></td>
</tr>

<tr>
<td>7</td>
<td><b>配置Web SDK</b>. 确保您在步骤4中安装的库已正确配置数据流ID(以前称为边缘配置ID(<code>edgeConfigId</code>)，组织id(<code>orgId</code>)和其他可用选项。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hans">配置Web SDK</a></td>
</tr>

<tr>
<td>8</td>
<td><b>执行命令</b> 和/或 <b>跟踪事件</b>. 在您的网页上实施基础代码后，您可以使用SDK开始执行命令和跟踪事件。
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en">执行命令</a> 和 <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en">跟踪事件</a></td>
</tr>

<tr>
<td>9</td><td><b>扩展并验证实施</b> 然后再推出生产。</td><td></td> 
</tr>
</table>


## Web SDK 扩展

实施任务的高级概述：

![使用Web SDK扩展工作流实施Adobe Analytics](../../assets/websdk-extension-annotated.png)

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
<td><b>创建数据层</b> 用于管理网站上数据的跟踪。</td>
<td><a href="../../prepare/data-layer.md">创建数据层</a></td>
</tr>

<tr>
<td>4</td>
<td><b>配置数据流</b>. 数据流表示实施Adobe Experience Platform Web SDK时的服务器端配置。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">配置数据流<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>添加Adobe Analytics服务</b> 到您的数据流。 该服务控制数据是否以及如何发送到Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">将Adobe Analytics服务添加到数据流</a></td>
</tr>

<tr>
<td>6</td>
<td><b>创建标记属性</b>.属性是用于引用标签管理数据的总容器。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web">为Web创建或配置标记属性</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>安装和配置Web SDK扩展</b> 在标记属性中。 配置Web SDK扩展，以将数据发送到步骤4中配置的数据流。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en">Adobe Experience Platform Web SDK扩展概述</a></td>
</tr>

<tr>
<td>8</td>
<td><b>迭代、验证和发布</b> 生产。 将标记属性添加到您的网站。 然后，使用数据元素、规则等自定义您的实施。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hans">发布概述</a></td>
</tr>

</table>


## 其他资源

标记可高度定制。详细了解如何通过在实施中包含正确的数据来充分利用 Adobe Analytics。

- [标记文档](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#?lang=zh-Hans)：了解界面的使用方式和可用的扩展。

- [Adobe Experience Platform Web SDK文档](https://experienceleague.adobe.com/docs/web-sdk.html?lang=zh-Hans)
