---
title: 地区数据收集
description: 关于区域数据收集的信息
feature: Regional Data Collection
exl-id: 295e9736-2a58-48a8-9968-5dfa33b70d95
source-git-commit: 88d6edd99c96d19980464e0f1cfa5cc867baf645
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---

# 地区数据收集

Adobe Experience Cloud 使用区域数据收集 (RDC)，这样，您的访客与 Adobe 之间的交互就会尽可能靠近您的访客。在数据收集中心 (DCC) 收集区域数据后，它会通过安全连接转发到数据处理中心 (DPC)。处理后，数据可用于 Adobe Experience Cloud 中的产品。

区域数据收集过程使用以下步骤：

1. DNS 会自动将收集主机名解析为距访客最近的数据收集中心的 IP 地址。
1. 访客将数据发送到该地址。
1. 届时，数据会立即通过安全连接转发到数据处理中心进行处理，然后提供给 Adobe Experience Cloud 中的产品。

使用区域数据收集提供了以下好处：

* **性能**：通过 RDC，访客将连接到最近的 DCC。这优化将提供最快的响应速度，从而实现更准确的跟踪和更快的加载速度。
* **冗余**：如果 DCC 与 DPC 之间出现通信中断，则 Adobe 的 RDC 基础设施会在本地保存数据，然后在通信恢复后将数据转发到 DPC。

RDC 目前包括以下位置（可能发生变化）：

## 第三方数据收集

| RDC 类型 | 数据收集中心 |
| --- | --- |
| 默认 | 俄勒冈、弗吉尼亚、爱尔兰、巴黎、孟买、新加坡、东京、悉尼、中国* |

{style=&quot;table-layout:auto&quot;}

*中国 RDC 需要中国加载项包。请参阅下面的[中国性能优化](#china-performance-optimization)。

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

*“仅限中国”和“全球 + 中国”RDC 类型需要中国加载项包。“全球 + 中国”会将源自中国境内的数据路由到 Adobe 的中国 RDC，同时将源自中国境外的数据路由到中国境外最近的 RDC。请参阅下面的[中国性能优化](#china-performance-optimization)。

## 中国性能优化

中国 RDC（中国性能优化）加载项包是 Adobe Analytics 的收费加载项。Adobe 在中国大陆推出的性能优化使在中国境内拥有用户的客户能够将数据直接发送到中国境内的 Adobe 数据收集服务器，而不用发送到全球其他位置。与将数据发送到中国以外的位置相比，此性能优化可缩短页面加载时间，并提高数据准确性。数据最终会传输到中国境外的 Adobe 数据处理中心 (DPC) 之一。有关更多信息，请与您的 Adobe 销售代表联系。

>!![NOTE]
中国 RDC 加载项包不支持 [Web SDK](/help/implement/aep-edge/overview.md)。

