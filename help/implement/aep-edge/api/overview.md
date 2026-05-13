---
title: 使用Adobe Experience Platform Edge Network API实施Adobe Analytics
description: 使用Adobe Experience Platform Edge Network API将数据发送到Adobe Analytics。
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/lvnplKx6dPwmmbZWgSShGvZXD2TtUoigi-HNiKutZSg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 42%

---

# 使用Adobe Experience Platform Edge Network API实施Adobe Analytics

从物联网设备、机顶盒、桌面应用程序等设备收集数据时，通常使用Experience Platform Edge Network API在服务器端而不是客户端收集数据。 然后，将该数据发送到Edge网络和Adobe Analytics等服务。

当您要求安全地收集敏感数据并在整个网络中进行身份验证时，还可以考虑Edge Network API。 有关详细信息，请参阅[身份验证](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html)。

实施任务的高级概述：

![使用 Analytics 扩展工作流的 Adobe Analytics](../../assets/edge-network-server-api-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>任务</b></th><th style="width:35%"><b>更多信息</b></th>
</tr>

<tr>
<td>1</td>
<td>确保您已<b>定义报告包</b>。</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">报告包管理器</a></td>
</tr>

<tr>
<td>2</td>
<td><b>设置架构</b>。 为了标准化数据收集以在利用 Adobe Experience Platform 的应用程序中使用，Adobe 创建了开放且公开记录的标准，即体验数据模型 (XDM)。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hans">架构UI概述</a></td>
</tr>

<tr>
<td>3</td>
<td><b>配置数据流</b>。 数据流表示使用Adobe Experience Platform Edge Network API中的API时的服务器端配置。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans">配置数据流<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>使用单事件数据和批次事件数据收集API实施和测试数据收集</b>。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=zh-Hans">单事件数据收集</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=zh-Hans">批次事件数据收集</a>
</tr>

<td>5</td>
<td><b>将 Adobe Analytics 服务</b>添加到您的数据流。 该服务控制数据是否以及如何发送到 Adobe Analytics。</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=zh-Hans">与Adobe Analytics交互</a></td>
</tr>


</table>

有关详细信息，请参阅[Edge Network API文档](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=zh-Hans)。

