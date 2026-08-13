---
title: Adobe Analytics使用的IP地址
description: 如果贵组织的防火墙阻止源自 Adobe 的 IP 地址，请使用此列表更新您的防火墙设置。
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
TQID: https://experienceleague.adobe.com/-4XZdprTBXpIaFnHeXBQsAr5YoZMW4ocnZRY50bHGUs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 32%

---

# Adobe Analytics使用的IP地址

一些防火墙配置会阻止源自 Adobe 数据收集服务器或负责访问数据的服务器的 IP 地址。 您可以使用此范围列表来更改贵组织的防火墙设置，以允许从组织内访问和发送数据。

Adobe Analytics使用的所有IP地址都是CX Enterprise[&#128279;](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)使用的IP地址的一部分，但“中国性能优化”附加组件包除外。

## 中国性能优化IP地址

中国性能优化附加组件包是一项额外的付费服务，可提高AppMeasurement对中国境内访客的数据收集性能。 请联系您的Adobe客户团队，了解有关使用此功能的更多信息。

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

>[!MORELIKETHIS]
>
>CX Enterprise使用的[个IP地址](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)
>
>Adobe Analytics使用的[域](domains.md)
