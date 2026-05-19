---
description: 关于服务器端转发相关特性、功能和问题的常见问题解答。
title: 服务器端转发常见问题解答
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
TQID: https://experienceleague.adobe.com/3i6RY7JRPlJc-9NjsQXBPn5SEOn0m4JrtL85Kl84ilM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 707
ht-degree: 47%

---

# 服务器端转发常见问题解答

关于服务器端转发相关特性、功能和问题的常见问题解答。

## 跟踪服务器 {#section_28E5BECC2034484AB9726E513F2CCFB7}

| 问题 | 回答 |
|--- |--- |
| 问：如果我当前使用的是基于跟踪服务器的旧版服务器端转发，该怎么办？ | 基于跟踪服务器的旧版服务器端转发方法将继续将数据从Analytics转发到Audience Manager，但是，如果您希望将Audience Manager区段发送到Analytics，则需要基于报表包的新版服务器端转发。 此外，在您的跟踪服务器配置之上为报表包启用服务器端转发没有任何坏处 — 每当发生冲突时，都将使用新的报表包服务器端转发设置。 |
| 问：我应该将基于跟踪服务器的旧版服务器端转发迁移到基于报表包的新版服务器端转发吗？ | 在可预见的将来，我们将继续支持基于跟踪服务器的服务器端转发，但是，如果您想要利用从Audience Manager到Analytics的集成（将区段共享到Analytics），则您需要为所有适用的报表包启用新的基于报表包的服务器端转发。 但是，没有迫切需要禁用基于旧版跟踪服务器的服务器端转发。 |

## 标记和报告 {#section_71391BA901AC47B9A2286281644FF281}

| 问题 | 回答 |
|--- |--- |
| 问：如果我的网站上有多包标记，该怎么办？ 服务器端转发会将我对 Audience Manager 的服务器调用次数加倍吗？ | 不会，从 Analytics 转发到 Audience Manager 的点击将只会转发到 Audience Manager 一次，这与点击中的报表包数量无关。 如果您在 Audience Manager 中有对应于点击中每个报表包的数据源，则将相应地填充该单次点击中的每个报表包。  但是请记住，如果您当前使用客户端数据收集 (DIL)，并且在未安装受众管理模块的情况下启用了服务器端转发，则无论您的 Analytics 点击中有多少个报表包，都会使您对 Audience Manager 的服务器调用次数加倍。 |
| 问：如果我有映射到不同CX Enterprise组织的多包标记报表包，该怎么办？ | 您决不应该将来自单个Analytics点击的数据发送到两个属于不同CX Enterprise Organization的报表包，但如果这样做了，我们只会将点击转发到与页面上的Identity Service设置相匹配的CX Enterprise Org。 |
| 问：如果我有多包标记并且只有一个报表包映射到我的CX Enterprise组织，而其他报表包则没有映射，该怎么办？ | 我们会将点击转发到映射的报表包上的CX Enterprise组织对应的数据收集服务器，但是由于未映射的报表包在Audience Manager中没有关联的数据源，因此不会在Audience Manager中为未映射的报表包记录任何数据。 |
| 问：如果我有一个报表包映射到多个CX企业组织，该怎么办？ | Analytics会将此报表包视为未映射，不允许为此报表包启用服务器端转发。 请联系客户关怀以解决此映射问题。 |
| 问：基于报表包的服务器端转发方法会比基于跟踪服务器的服务器端转发更慢吗？ | 不会，响应时间将是相同的。 |
| 问：如果我们有两个CX Enterprise组织（或Adobe Audience Manager实例）并希望在这两个CX Enterprise组织之间共享数据，该怎么办？ 我是否可以在服务器端将单个Analytics点击转发到多个CX Enterprise组织？ | 否。 如果您需要将一个CX Enterprise组织下收集的数据共享到另一个CX Enterprise组织，我们建议使用受众市场将一个Audience Manager实例中的任何适用受众发送到另一个实例。 |
| 问：服务器端转发会导致 Audience Manager 或 Analytics 中产生任何额外计费吗？ | 在 Analytics 中，不会产生任何额外计费。 在 Audience Manager 中，转发的点击将会像任何其他点击一样进行处理并加以计费。  这就是为什么切勿同时启用 DIL 和服务器端转发的原因，因为这样做会导致双重计费以及数据重复。 |

>[!MORELIKETHIS]
>
>* [服务器端转发](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
