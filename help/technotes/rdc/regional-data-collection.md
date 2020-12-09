---
title: 地区数据收集
description: 关于区域数据收集的信息
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 77%

---


# 地区数据收集

Adobe Experience Cloud 使用区域数据收集 (RDC)，这样，您的最终用户与 Adobe Experience Cloud 之间的交互就会尽可能靠近您的最终用户。这项更改可提高网站/应用程序性能，并确保尽快收集数据，以优化最终用户体验。在数据收集中心 (DCC) 对数字资产中的数据进行地区性收集后，这些收集的数据会通过安全连接转发到数据处理中心 (DPC) 进行处理，然后提供给 Adobe Experience Cloud 中的产品。

>[!IMPORTANT]
>
>中国RDC（中国性能优化）附加组件是Adobe Analytics的收费附加组件。 Adobe在中国大陆的业绩优化使中国境内的客户能够直接将数据发送到中国边缘节点，而不是全球其他地点。 与将数据发送到中国境外的节点相比，这提高了页面加载时间和数据准确性。 请联系您的Adobe销售代表以了解更多信息。

RDC 目前包括以下位置（可能发生变化）：

## 第三方和 HTTP 数据收集

| RDC 类型 | 数据收集中心 |
|---------------------|-------------------|
| 默认 | 俄勒冈、弗吉尼亚、爱尔兰、巴黎、孟买、新加坡、东京、悉尼 |

Note: If your Analytics image request is sent to the `adobedc`, `2o7.net` or `omtrdc.net` endpoints, then you have third-party data collection. 如果您在请求的 URL 中看到了任一端点，则可以确定这一点。

## 第一方 HTTPS 数据收集

| RDC 类型 | 数据收集中心 |
|---------------------|-------------------|
| 全局（默认） | 俄勒冈、弗吉尼亚、爱尔兰、巴黎、孟买、新加坡、东京、悉尼 |
| 仅限美洲 | 俄勒冈州、弗吉尼亚州 |
| 仅限欧洲 | 爱尔兰、巴黎 |
| 仅限亚太地区 | 孟买、新加坡、东京、悉尼 |

注意：Experience Edge Global 可为最终用户提供最佳性能。如果您希望使用替代 RDC 类型，请联系 Adobe 客户服务以寻求帮助。

## RDC 工作原理

以下列表描述了 Adobe 使用的数据收集过程：

1. DNS 会自动将收集主机名解析为距访客最近的数据收集中心的 IP 地址。
1. 访客将数据发送到该地址。
1. 届时，数据会立即通过安全连接转发到数据处理中心进行处理，然后提供给 Adobe Experience Cloud 中的产品。
