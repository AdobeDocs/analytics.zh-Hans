---
title: 品牌可见度集成
description: 将品牌可见度与Adobe Analytics集成
feature:
role: User
source-git-commit: 841b09d487fb965fb2a5fce4a39a7480a5b01012
workflow-type: tm+mt
source-wordcount: '2637'
ht-degree: 1%
---

# Adobe Brand Visibility集成

[Adobe Brand Visibility](https://experienceleague.adobe.com/zh-hans/docs/llm-optimizer/using/home)是创新型人工智能优先的创新型引擎优化应用程序，旨在帮助品牌在人工智能驱动的搜索环境中增强可见性、准确性和影响力。 品牌可见度提供对AI生成答案中品牌存在感的洞察、提供规范性内容建议，并自动化优化修复。

人工智能已成为一个主要的发现渠道。 大型语言模型(LLM)代理（如ChatGPT、Claude、Copilot和Perplexity）抓取品牌内容。

>[!NOTE]
>
>品牌可见度以前称为&#x200B;**LLM Optimizer (LLMO)**。 某些Adobe文档在过渡期间可能会继续使用以前的LLMO术语。


>[!PREREQUISITES]
>
>您必须配置品牌可见度付费产品，并通过托管连接器连接到您的Experience Platform配置。


>[!IMPORTANT]
>
>作为这种集成的一部分，美国会对品牌可见度数据进行一些临时处理。 数据最终会存储在您在Adobe Analytics合同中配置的指定区域。

如果您使用Customer历程分析，则更丰富的单独入站集成会通过Adobe Experience Platform将相同的基础CDN流量数据接入Customer Journey Analytics。 该集成现已推出。 查看[品牌可见度与Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv)的集成。 如果您拥有Customer Journey Analytics，请首先查看该集成，因为它会公开更多字段，并支持将品牌可见度数据与其他数据集联接起来。 本指南中描述的Analytics集成专为使用Adobe Analytics但没有访问权限或Customer Journey Analytics许可证的客户而设计。


## 用例

您可以通过两种方式从Adobe Analytics与Brand Visibility之间的集成中受益：

* **入站集成**：使用Adobe Analytics中的品牌可见度数据测量现有Web和移动数据以及由LLM驱动的流量（机器人爬虫、RAG请求、代理活动）。 例如，您可以：

  * 在传统渠道的同时，按代理源测量LLM驱动的流量。

  * 识别LLM大量使用但在人工转化中表现不佳的内容。

  * 检测LLM-agent请求在关键路径上的失败位置。

  * 在URL和主机级别匹配，将某个页面的LLM机器人需求与Web数据中的页面转化率和收入进行比较。

* **出站集成**：将Adobe Analytics性能数据发送到Brand Visibility中，以便您能够优化向您发送宝贵流量的LLM源（如ChatGPT或Perplexity）的AI可见性。 例如，您可以：

  * 查看哪些LLM来源会向继续转化或产生收入的人类访客发送信息。 Adobe Analytics从引用的Web流量（而不是机器人数据集）测量此值。
  * 按发送的人类访客的下游值对LLM源进行排名，然后将AI可见性工作集中在表现最佳的源上。


## 入站集成

本节介绍&#x200B;**→Adobe Analytics**&#x200B;入站集成的先决条件和设置步骤。


入站Adobe Analytics连接器是通过&#x200B;**报表包管理器**&#x200B;为每个报表包配置的，如第6节所述。

>[!PREREQUISITES]
>
>对于每个品牌可见度站点，必须已将CDN访问日志转发到Adobe Brand Visibility并由其接收，然后才能启用品牌可见度→Adobe Analytics连接器。
>
>此要求适用于&#x200B;**每个品牌可见度站点**。 不应假定一个站点、域或子域的CDN配置或日志馈送涵盖另一个站点，除非Adobe确认涵盖范围。
>
>
>在启用连接器之前，请确认：
>
>1. 相关的CDN或日志管道配置为将所需的访问日志转发到Adobe提供的目标。
>1. 品牌可见度已确认接收并检测到相关站点的日志。
>1. 可在您网站的品牌可见度代理流量功能板中显示数据。
>
>BYOCDN日志转发提供用于代理流量分析的服务器端CDN请求数据。 数据并不依赖于浏览器中运行的JavaScript标记。 如果没有所需的CDN日志馈送，连接器将没有要引入报表包的流量数据。
>
>有关详细信息，请参阅[BYOCDN日志转发引用](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)。


>[!IMPORTANT]
>
>作为这种集成的一部分，美国会对品牌可见度数据进行一些临时处理。 数据最终会存储在您在Adobe Analytics合同中配置的指定区域。


### 工作原理

Adobe Analytics集成→入站品牌可见度向报表包中添加了一组&#x200B;**保留的变量**。 这些变量包含有关在网站上检测到的机器人和自动代理流量的摘要级别数据，包括基于LLM的流量，这些流量源自[先决条件](#inbound-integration)中描述的相同CDN访问日志。

此流量通常不会运行浏览器JavaScript标签，也不会通过您现有的Adobe Analytics实施来捕获。 通过保留变量，您可以在已用于网站的同一报表包中查看此流量。

在启用连接器时，会添加以下保留变量：

| 报告为 | 类型 | 注释 |
|---|---|---|
| URL | 维度 | 与请求关联的页面URL。 |
| 机器人类型 | 维度 | 发出请求的机器人或自动代理的类型（例如，指定的AI爬虫）。 |
| 用户代理 | 维度 | 机器人或代理报告的用户代理字符串。 |
| 状态 | 维度 | 为请求返回的HTTP状态代码。 |
| Referer | 维度 | 请求的HTTP引用值（如果存在）。 |
| 请求 | 量度 | 机器人和代理CDN请求的计数。 |


#### 与Customer Journey Analytics相比的覆盖范围

CJA入站集成基于更广泛的CDN请求摘要数据集构建，并支持其他字段（例如，主机和CDN提供商）以及与Customer Journey Analytics中的其他数据集连接。 Adobe Analytics集成是一组较小的报表包原生保留变量，旨在用于Analytics的现有数据模型。 如果您的报表需求超出了上面列出的字段，请评估CJA集成。

#### 重要限制

- 不包括访客ID、ECID、访问次数或独特用户数据。 这是汇总、不与访客相关的摘要数据。
- 保留变量不支持分配类型或到期类型设置，因为它们未与访客绑定。
- 数据无法像在Customer Journey Analytics中那样与其他Analytics数据集或维度联接。
- 使用&#x200B;**请求**&#x200B;度量度量来测量机器人和代理流量。 请勿将其与报表包中其他基于访问或基于点击的量度互换使用。

启用连接器后，应根据报表包的变量配置确认确切的可用字段集。

### 责任

入站连接器的设置和配置将针对[Adobe](#adobe-managed-responsibilities)和[您作为客户](#customer-owned-responsibilities)负责。

#### Adobe管理的职责

1. 检测并确认每个已载入品牌可见度站点的CDN日志转发。
2. 在确认BYOCDN日志转发后，使保留的变量可用于配置。
3. 为报表包启用连接器后，运行90天的回填并持续每小时同步。

#### 客户拥有的责任

1. 正在为每个站点完成品牌可见度载入和BYOCDN日志转发。
2. 在启用连接器之前，确认数据在品牌可见度代理流量仪表板中可见。
3. 选择每个品牌可见度站点连接到的报表包（每个报表包一个站点）。
4. 通过报告包管理器启用连接器。
5. 生成使用[中列出的保留变量的报表、区段或数据视图（如果适用）。其工作方式](#how-it-works)。

### 开始之前

在启用连接器之前，请确认以下各项：

- 您已为要连接的站点完成Adobe Brand Visibility载入。
- 已为该站点设置并确认BYOCDN日志转发（请参阅[先决条件](#inbound-integration)）。
- 数据将显示在该网站的Adobe Brand Visibility代理流量仪表板中。
- 您知道要将站点连接到哪个报表包。

每个Adobe Brand Visibility站点只能连接到一个报表包。 如果要为多个品牌可见度站点导入数据，请将每个站点连接到单独的报表包。


### 启用连接器

连接器在报表包的&#x200B;**编辑设置**&#x200B;菜单中处于打开和关闭状态。

要打开报表包的Adobe Brand Visibility设置，请执行以下操作：

1. 登录到Adobe Analytics。
1. 转到&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 选择要连接的报表包。
1. 选择&#x200B;**[!UICONTROL 编辑设置]**。
1. 从上下文菜单中选择&#x200B;**[!UICONTROL Adobe Brand Visibility]**。

要设置连接器，请执行以下操作：

1. 选择&#x200B;**配置Adobe Brand Visibility Data Connector**。
1. 查看将添加到此报表包的维度和量度（在[工作方式](#how-it-works)中列出）。
1. 在&#x200B;**选择Adobe Brand Visibility站点**&#x200B;下，选择要连接到此报表包的站点。 连接后，网站的摘要数据每小时会同步到此报表包。
1. 选择&#x200B;**启用**。

   启用后，这些变量将无法从此报表包中删除。 启用连接器将开始90天的回填，从而将过去90天的Adobe Brand Visibility数据导入此报表包。

   在启用连接器之前，请确认您已完成[中描述的步骤。在开始](#before-you-start)之前，这包括验证数据是否已显示在Adobe Brand Visibility代理流量仪表板中。

启用连接器后，留出时间完成初始回填和首次每小时同步。 然后，确认在您的报表包中填充了[其工作方式](#how-it-works)中提到的保留变量。 请参阅第8节第3步)。

### 禁用连接器

>[!WARNING]
>
>禁用连接器为&#x200B;**不可逆**。 禁用将停止每小时同步并删除此报表包的Adobe Brand Visibility历史数据。

要禁用连接器，请执行以下操作：

1. 转到&#x200B;**管理员→报表包→编辑Adobe Brand Visibility→的设置**。
1. 选择&#x200B;**取消配置Adobe Brand Visibility Data Connector**。
1. 确认列出的Adobe Brand Visibility站点是您打算断开的站点。
1. 选择&#x200B;**禁用**。
1. 确认警告以进行确认。

如果只想暂时暂停报告，请不要禁用连接器。 请联系您的Adobe客户团队，讨论在禁用之前暂停报告的选项。

### 设置完成条件

在确认以下所有条件后，集客集成即可进行报告：

* Adobe Brand Visibility会将CDN日志转发到站点并由其接收。
* 数据在网站的Adobe Brand Visibility代理流量功能板中可见。
* 连接器已通过报表包管理器为预期报表包启用。
* 初始回填和至少一个小时同步已完成。
* 第4节中的保留变量在报表中返回预期值。

### 验证程序

验证过程包含以下步骤：

1. 确认品牌可见度站点和CDN日志准备就绪：

   * 确认您计划连接的确切站点或域。
   * 确认该站点的CDN日志正在转发，且品牌可见度已确认接收。
   * 确认数据在该网站的代理流量仪表板中可见。

1. 确认连接器已启用：

   1. 转到&#x200B;**管理员→报表包→编辑目标报表包→Adobe Brand Visibility**&#x200B;的设置。
   1. 确认页面将连接器显示为已启用，并列出连接的品牌可见度站点。

1. 确认报表中的数据：

   1. 针对连接的报表包打开Analysis Workspace（或标准报表工作流）。
   1. 使用按&#x200B;**机器人类型**&#x200B;划分的&#x200B;**请求**&#x200B;量度生成表或可视化图表。
   1. 确认最近日期范围内出现请求量。
   1. 确认&#x200B;**URL**、**用户代理**、**状态**&#x200B;和&#x200B;**Referer**&#x200B;维度返回预期值。

   数据出现的确切时间取决于[启用连接器](#enable-the-connector)中所述的回填和同步计划。



### 故障排除

请参阅以下问题以及如何解决这些问题。

| 问题 | 疑难解答 |
|---|---|
| 连接器将无法启用，或者站点列表为空。 | 检查是否：<ul><li>该站点的Adobe Brand Visibility载入已完成。</li><li>已为站点配置并确认BYOCDN日志转发。</li><li>您使用正确的报表包。</li><ul> |
| 连接器已启用，但未显示任何数据。 | 检查是否： <ul><li>所连接站点的代理流量仪表板中会显示数据（如果没有，则问题位于Analytics的上游）。</li><li>最初的90天回填间隔了足够长的时间，并且至少每小时同步一次。</li><li> — 报表中的选定日期范围包含启用连接器的时间段。</li></ul> |
| 数据显示不完整或意外。 | 检查是否： <ul><li>此外，报表包不应接收其他品牌可见度站点的数据（每个报表包只能连接到一个站点）。</li><li>您正在读取&#x200B;**请求**&#x200B;量度，而不是对报表包中其他位置的行或点击进行计数。</li><li>您正在查看的维度与第4节中的列表相匹配；同一报表包中无关的evar或事件不属于此集成。</li></ul> |

>[!MORELIKETHIS]
>
>[品牌可见度/LLMO集成参考](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv)
>[BYOCDN日志转发引用](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)

---

## 文档草稿说明（不用于发布）

此部分供内部审查，应在发布之前删除。

- **使用的Source真实值：**&#x200B;字段名称、保留的变量列表以及报表包管理器工作流源自[AN-468884](https://jira.corp.adobe.com/browse/AN-468884)（David Wardell，状态为2026-08-28的新增），它比原始文档请求[AN-449989](https://jira.corp.adobe.com/browse/AN-449989)（Rob In der Maur，状态为New）更新、更具体。 Provision/Deprovision屏幕的页面副本包含了2026-08-28年度内部审核(`2026-08-28-an468884-abv-report-suite-ui-review.md`)的措辞细化，该内部审核在面向客户的文本中将原始票证的“ABV”缩写替换为“Adobe Brand Visibility”。
- **在发布之前要协调的字段集差异：** AN-449989的原始维度列表为“主机”、“URL/页面路径”、“CDN提供程序”、“用户代理”和“LLM机器人类型”，只有一个代理请求计数量度。 AN-468884的实际保留变量列表是URL、机器人类型、用户代理、状态和引用，其中仅有一个请求事件。 在AN-468884中，主机和CDN提供程序不是作为单独的保留变量存在；状态是新的。 此草稿遵循AN-468884作为引擎票证的权威标准，但在最终确定之前，应将两者与Aaron Kern / David Wardell进行协调，因为客户看到的字段名称可能与客户团队使用旧版AN-449989语言描述的内容不匹配。
- **尚未确认，在发布的版本**&#x200B;中不要声明为事实
  - 确切正式发布日期。 AN-431416带有FixVersion H2 2026（2026-11-30发布窗口），并且从2026-09-01起处于“执行”状态；AN-468884（保留变量实施）和AN-449989（此文档）都是新版本。 在发出引擎之前请勿发布。
  - 在生产中使用的保留evar上是否完全禁止显示分配类型/到期类型。 《2026-08-28》评测标记了测试报表包当前显示这些eVar并将“分配”设置为“最近（最后一个）”，这可能是需要清除的默认值，而不是确认的最终行为。
  - 截至2026-08-26票证注释，按IMS组织列出ABV站点的LLMO API端点（填充“站点选择”下拉列表）和取消置备/禁用API仍在Joe Bass挂起。
  - CJA字段数的准确比较。 AN-449989的原始票证声称CJA具有“9个额外的维度”和“5个额外的量度”，但其中几个量度（LLM会话存储段、LLM唯一会话计数、LLM请求重复计数）在2026-06-18审核时未确认存在于已交付的`cdn-requests-summary`字段组中。 因此，此草稿会刻意避免在CJA比较中引用特定计数。
  - 此AA路径的同步节奏在此处表示为每小时，与AN-468884的票证语言（“运行每小时同步”/“每小时同步过程”）匹配。 这尚未像CJA节奏那样针对生产AA数据源行为单独进行验证。


## 出站集成

本指南仅介绍入站品牌可见度集成，该集成会将机器人和自动代理流量数据添加到Analytics报表包。 发布的集成文档还描述了出站方向，在该方向中，Analytics性能数据可用于品牌可见度在品牌可见度产品中。 该方向不在本指南的范围之内。 有关出站集成的详细信息，请参阅[品牌可见度文档](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/adobe-analytics-integration)。