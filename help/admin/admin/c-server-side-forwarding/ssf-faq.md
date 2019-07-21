---
description: 关于服务器端转发相关特性、功能和问题的常见问题解答。
seo-description: 关于服务器端转发相关特性、功能和问题的常见问题解答。
seo-title: 服务器端转发常见问题解答
title: 服务器端转发常见问题解答
uuid: ed0bc9b-ef7-414e-88a2-ebba3 fd75 c92
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 服务器端转发常见问题解答

关于服务器端转发相关特性、功能和问题的常见问题解答。

## 跟踪服务器 {#section_28E5BECC2034484AB9726E513F2CCFB7}

| 问题 | 回答 |
|--- |--- |
| 问：如果我当前使用的是基于跟踪服务器的旧版服务器端转发，该怎么办？ | 基于跟踪服务器的旧版服务器端转发方法会继续将数据从 Analytics 转发到 Audience Manager，但是如果您希望将 Audience Manager 区段发送到 Analytics 中，则需要使用基于报表包的新版服务器端转发。此外，在您的跟踪服务器配置之上为报表包启用服务器端转发没有任何坏处 - 每当发生冲突时，都将使用新的报表包服务器端转发设置。 |
| 问：我应该将基于跟踪服务器的旧版服务器端转发迁移到基于报表包的新版服务器端转发吗？ | 在可预见的将来，我们会继续支持基于跟踪服务器的服务器端转发，但是如果您希望利用从 Audience Manager 到 Analytics 的集成（将区段共享到 Analytics），则您将需要为所有适用的报表包启用基于报表包的新版服务器端转发。不过，目前并无迫切的理由要禁用基于跟踪服务器的旧版服务器端转发。 |

## 标记和报告 {#section_71391BA901AC47B9A2286281644FF281}

| 问题 | 回答 |
|--- |--- |
| 问：如果我的网站上有多包标记，该怎么办？服务器端转发会将我对 Audience Manager 的服务器调用次数加倍吗？ | 不会，从 Analytics 转发到 Audience Manager 的点击将只会转发到 Audience Manager 一次，这与点击中的报表包数量无关。如果您在 Audience Manager 中有对应于点击中每个报表包的数据源，则将相应地填充该单次点击中的每个报表包。但是请记住，如果您当前使用客户端数据收集 (DIL)，并且在未安装受众管理模块的情况下启用了服务器端转发，则无论您的 Analytics 点击中有多少个报表包，都会使您对 Audience Manager 的服务器调用次数加倍。 |
| 问：如果我已将多包标记报表包映射到单独的Experience Cloud Ocs，该怎么办？ | 您不得从单个Analytics点击发送数据至属于单独Experience Cloud Ors的两个报表包，但如果发生这种情况，我们只会将点击转发到Experience Cloud Org与页面上的Identity Service设置相匹配。 |
| 问：如果我有多包标记，并且只有一个报表包映射到我的Experience Cloud Org，而另一个报表包没有映射到该产品包，那么该怎么办？ | 我们会在映射的报告套件中将点击转发至Experience Cloud组织对应的数据收集服务器，然而，由于未映射的报告套件在Audience Manager中将没有关联的数据源，因此Audience Manager中未映射的报告套件不会记录数据。 |
| 问：如果我有一个映射到多个Experience Cloud Os的报表包，该怎么办？ | Analytics 会将此报表包视为未映射的报表包，并且不允许为此报表包启用服务器端转发。请联系客户关怀团队以解决此映射问题。 |
| 问：基于报表包的服务器端转发方法会比基于跟踪服务器的服务器端转发更慢吗？ | 不会，响应时间将是相同的。 |
| 问：如果我们有两个Experience Cloud Os(或AAM实例)，并希望在Experience Cloud Ocs之间共享数据，该怎么办？我是否可以将一个Analytics转发给多个Experience Cloud Ocs？ | 不会。如果您需要将在一个Experience Cloud Org下收集的数据共享到另一个Experience Cloud Org，我们建议使用受众市场将任何适用的受众从一个Audience Manager实例发送到另一个。 |
| 问：服务器端转发会导致 Audience Manager 或 Analytics 中产生任何额外计费吗？ | 在 Analytics 中，不会产生任何额外计费。在 Audience Manager 中，转发的点击将会像任何其他点击一样进行处理并加以计费。这就是为什么切勿同时启用 DIL 和服务器端转发的原因，因为这样做会导致双重计费以及数据重复。 |

>[!MORE_LIKE_THIS]
>
>* [服务器端转发](ssf.md#concept_9563FCADF29748928E770EC5221B2685)

