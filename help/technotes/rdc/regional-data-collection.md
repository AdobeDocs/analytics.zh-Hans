---
title: 地区数据收集
description: 关于区域数据收集的信息
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 88d6edd99c96d19980464e0f1cfa5cc867baf645
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 38%

---

# 地区数据收集

Adobe Experience Cloud使用区域数据收集(RDC)，以便访客与Adobe之间的交互尽可能靠近访客。 在数据收集中心(DCC)对数据进行地区性收集后，这些收集数据会通过安全连接转发到数据处理中心(DPC)。 处理后，该数据便可用于Adobe Experience Cloud中的产品。

区域数据收集流程使用以下步骤：

1. DNS会自动将收集主机名解析为距访客最近的数据收集中心的IP地址。
1. 访客将数据发送到该地址。
1. 届时，数据会立即通过安全连接转发到数据处理中心进行处理，然后提供给 Adobe Experience Cloud 中的产品。

使用区域数据收集具有以下几个好处：

* **性能**:通过RDC，您的访客可以连接到最近的DCC。 此优化提供了最快的响应时间，从而实现更准确的跟踪和更快的加载时间。
* **冗余**:如果DCC与DPC之间的通信中断，则Adobe的RDC基础架构会将数据保存在本地，然后在通信恢复后将其转发到DPC。

RDC 目前包括以下位置（可能发生变化）：

## 第三方数据收集

| RDC 类型 | 数据收集中心 |
| --- | --- |
| 默认 | 俄勒冈、弗吉尼亚、爱尔兰、巴黎、孟买、新加坡、东京、悉尼、中国* |

{style=&quot;table-layout:auto&quot;}

*中国 RDC 需要中国加载项包。请参阅 [中国绩效优化](#china-performance-optimization) 下。

>[!NOTE]
>
>如果您的 Analytics 图像请求发送到了 `adobedc`、`2o7.net` 或 `omtrdc.net` 端点，则表明您使用的是第三方数据收集。 如果您在自己的请求的 URL 中看到其中任意一个端点，即可确定这一点。

## 第一方数据收集

| RDC 类型 | 数据收集中心 |
| --- | --- |
| 全局（默认） | 俄勒冈、弗吉尼亚、爱尔兰、巴黎、孟买、新加坡、东京、悉尼 |
| 全球 + 中国* | 中国*、俄勒冈、弗吉尼亚、爱尔兰、巴黎、孟买、新加坡、东京、悉尼 |
| 仅限美洲 | 俄勒冈州、弗吉尼亚州 |
| 仅限欧洲 | 爱尔兰、巴黎 |
| 仅限亚太地区 | 孟买、新加坡、东京、悉尼 |
| 仅限中国* | 北京 |

{style=&quot;table-layout:auto&quot;}

*“仅限中国”和“全球 + 中国”RDC 类型需要中国加载项包。 全球+中国将源自中国的数据路由到Adobe的中国RDC，同时将源自中国以外的数据路由到位于中国以外的最近RDC。 请参阅 [中国绩效优化](#china-performance-optimization) 下。

## 中国绩效优化

China RDC(China Performance Optimization)附加组件包是Adobe Analytics的收费附加组件。 Adobe在中国大陆的性能优化功能，允许具有中国境内用户的客户将该数据直接发送到中国境内的Adobe数据收集服务器，而不是发送到全球其他位置。 与将数据发送到中国以外的位置相比，此优化可缩短页面加载时间并提高数据准确性。 数据最终会传输到Adobe在中国境外的一个数据处理中心(DPC)。 有关更多信息，请联系您的Adobe销售代表。

>!![NOTE]
不支持的China RDC附加组件包 [Web SDK](/help/implement/aep-edge/overview.md).

