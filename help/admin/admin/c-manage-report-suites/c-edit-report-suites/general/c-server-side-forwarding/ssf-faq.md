---
description: 关于服务器端转发相关特性、功能和问题的常见问题解答。
title: 服务器端转发常见问题解答
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 100%

---

# 服务器端转发常见问题解答

关于服务器端转发相关特性、功能和问题的常见问题解答。

## 跟踪服务器 {#section_28E5BECC2034484AB9726E513F2CCFB7}

| 问题 | 回答 |
|--- |--- |
| 问：如果我当前使用的是基于跟踪服务器的旧版服务器端转发，该怎么办？ | 基于跟踪服务器的旧版服务器端转发方法会继续将数据从 Analytics 转发到 Audience Manager，但是如果您希望将 Audience Manager 区段发送到 Analytics 中，则需要使用基于报表包的新版服务器端转发。此外，在您的跟踪服务器配置之上为报表包启用服务器端转发没有任何坏处 — 每当发生冲突时，都将使用新的报表包服务器端转发设置。 |
| 问：我应该将基于跟踪服务器的旧版服务器端转发迁移到基于报表包的新版服务器端转发吗？ | 在可预见的将来，我们会继续支持基于跟踪服务器的服务器端转发，但是如果您希望利用从 Audience Manager 到 Analytics 的集成（将区段共享到 Analytics），则您将需要为所有适用的报表包启用基于报表包的新版服务器端转发。不过，目前并无迫切的理由要禁用基于跟踪服务器的旧版服务器端转发。 |

## 标记和报告 {#section_71391BA901AC47B9A2286281644FF281}

| 问题 | 回答 |
|--- |--- |
| 问：如果我的网站上有多包标记，该怎么办？服务器端转发会将我对 Audience Manager 的服务器调用次数加倍吗？ | 不会，从 Analytics 转发到 Audience Manager 的点击将只会转发到 Audience Manager 一次，这与点击中的报表包数量无关。如果您在 Audience Manager 中有对应于点击中每个报表包的数据源，则将相应地填充该单次点击中的每个报表包。但是请记住，如果您当前使用客户端数据收集 (DIL)，并且在未安装受众管理模块的情况下启用了服务器端转发，则无论您的 Analytics 点击中有多少个报表包，都会使您对 Audience Manager 的服务器调用次数加倍。 |
| 问：如果我的多包标记报表包映射到不同的 Experience Cloud 组织，该怎么办？ | 您决不应该将来自单次 Analytics 点击的数据发送到两个属于不同 Experience Cloud 组织的报表包，但如果这样做了，我们只会将点击转发到与页面中的 Identity 服务设置相匹配的 Experience Cloud 组织。 |
| 问：如果我有多包标记并且只有一个报表包映射到我的 Experience Cloud 组织，而其他报表包则没有映射，该怎么办？ | 我们会将点击转发到映射的报表包上的 Experience Cloud 组织对应的数据收集服务器，但是由于未映射的报表包在 Audience Manager 中没有关联的数据源，因此不会在 Audience Manager 中为未映射的报表包记录任何数据。 |
| 问：如果我有一个报表包被映射到多个 Experience Cloud 组织，我该怎么做？ | Analytics 会将此报表包视为未映射的报表包，并且不允许为此报表包启用服务器端转发。请联系客户关怀团队以解决此映射问题。 |
| 问：基于报表包的服务器端转发方法会比基于跟踪服务器的服务器端转发更慢吗？ | 不会，响应时间将是相同的。 |
| 问：如果我有两个 Experience Cloud 组织（或 Adobe Audience Manager 实例）并希望在这两个 Experience Cloud 组织之间共享数据，该怎么办？我可以在服务器端将一个 Analytics 点击转发到多个 Experience Cloud 组织吗？ | 不可以。如果您需要将一个 Experience Cloud 组织下收集的数据共享到另一个 Experience Cloud 组织，我们建议使用受众市场将一个 Audience Manager 实例中的任何适用受众发送到另一个实例。 |
| 问：服务器端转发会导致 Audience Manager 或 Analytics 中产生任何额外计费吗？ | 在 Analytics 中，不会产生任何额外计费。在 Audience Manager 中，转发的点击将会像任何其他点击一样进行处理并加以计费。这就是为什么切勿同时启用 DIL 和服务器端转发的原因，因为这样做会导致双重计费以及数据重复。 |

>[!MORELIKETHIS]
>
>* [服务器端转发](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
