---
title: Adobe Analytics 使用的 IP 和域
description: 如果贵组织的防火墙阻止源自 Adobe 的 IP 地址，请使用此列表更新您的防火墙设置。
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: ea859717c6a40b4eeeb9eca54b95718859af9c7b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 32%

---

# Adobe Analytics 使用的 IP 和域

某些防火墙配置会阻止Adobe Analytics作为其产品界面所依赖的域。 您可以使用此域列表来更改组织的网络设置，以允许从组织内部访问产品。

## 允许相关的技术域

Adobe Analytics 使用以下主机来改进性能和产品体验。Adobe建议允许这些域通过贵组织的防火墙，以获得最佳的Adobe Analytics使用体验。

| 技术 | 域 |
| --- | --- |
| Adobe Analytics 域 | `adobe.com`、`adobe.net`、`adobe.io` |
| Adobe Analytics 旧域 | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft Azure Blob 存储 | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud IP地址块

除了上述域之外，Adobe Analytics还依靠多个IP地址块来收集和导出报表。

有关IP范围的完整列表，请参阅Adobe Experience Cloud IP地址。

## 中国性能优化IP地址

中国性能优化附加组件包是一项额外的付费服务，可改善中国境内访客的AppMeasurement数据收集性能。 请联系您的Adobe客户团队，了解有关使用此功能的更多信息。

>[!IMPORTANT]
>
>中国RDC不可用于Web SDK数据收集。 这些服务器仅适用于AppMeasurement库。

中国的地区数据收集服务器使用以下IP地址：

| 位置 | 主机 |
| --- | --- |
| 中国 | `52.80.168.159` |
| 中国 | `52.80.199.104` |
| 中国 | `54.223.199.8` |

{style="table-layout:auto"}
