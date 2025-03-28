---
description: Adobe 提供了各种可供您使用的计算量度。此页面列出了这些量度及其预期用途。
title: 默认计算量度
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: ht
source-wordcount: '735'
ht-degree: 100%

---

# 默认计算量度

Adobe Analytics 通过提供各种计算量度来涵盖最常见的用例。这些计算量度在 Analysis Workspace 中默认可用。

以下是 Adobe 提供的每个计算量度的列表，包括其预期函数以及用于计算的基本公式：

>[!NOTE]
>
>除了本页描述的默认计算量度之外，您还可以向报告包中添加其他计算量度。
>
>您可以：
>
> * 为流媒体集合添加默认计算量度，如[计算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)中所述
> * 从现有量度中创建自定义计算量度，如[计算量度和高级计算量度](/help/components/c-calcmetrics/cm-overview.md)中所述。


| 计算量度名称 | 功能 | 公式 |
| --- | --- | --- |
| 获取链接点击次数 | 人员点击旨在产生网站流量的链接的次数。 | `[Campaign Click-throughs]` |
| 操作 | 在应用程序中执行的操作总数 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| 应用程序用户数 | 移动应用程序的用户总数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 平均会话时长（移动） | 单次会话期间访客在网站上逗留的平均时长。 | 空白 |
| 网站平均逗留时间 | 访客在离开或导航到别处之前在网站上逗留的平均时长。 | `[Average Time Spent on Site (Seconds)]` |
| 跳出率 | 包含一次点击的访问次数与该页面上的访问次数之间的比率。此量度可以帮助您了解哪个维度项的跳出率最高，或查看一段时间内网站的累计总跳出率。 | `[Bounces] / [Entries]` |
| 机器人页面查看率 | 机器人页面查看率与页面查看总次数之比。 | `[Bot Page Views] / [Page Views]` |
| 内容周转率 | 在网站上创建和发布新内容的速度以及新内容能够多快地吸引用户参与。 | `[Page Views] / [Visits]` |
| 转化率 | 执行了所需操作（如进行了购买）的访客的百分比。 | `[Orders] / [Visits]` |
| 登录率 | 在指定页面上进入网站的访客占网站上会话总数的百分比。 | `[Entries] / [Visits]` |
| 估计的独特访客量（ITP 2.1） | 对于 ITP 访客（Safari 浏览器上的用户），将独特访客量除以 2 或更少。该计算量度假设您使用客户端 JavaScript（而不是使用 CNAME 实施）设置 Cookie。从 ITP 2.1 开始，使用客户端 JavaScript 设置 Cookie 的实施会受到影响。有关详情，请参阅[智能防跟踪](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID 覆盖 | 拥有 Experience Cloud ID 的访客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 退出率 | 查看特定页面后离开网站的访客的百分比。 | `[Exits] / [Visits]` |
| ITP 2.1 独特访客量 / 独特访客量 | 使用受 ITP 2.1 Cookie 限制影响的浏览器的独特访客量百分比。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 订单助手 | 渠道或来源促成客户历程向购买推进但最终未购买的次数。 | `[Orders (Visit Participation)] - [Orders]` |
| 订单 / 访问次数 | 访问网站并完成交易的百分比。 | `[Orders] / [Visits]` |
| 订单 / 访客人数 | 每个访问网站的单独访客产生的平均订单数或交易数 | `[Orders] / [Unique Visitors]` |
| 页面查看次数 / 估计的独特访客量（ITP 2.1） | 估计的独特访客量（ITP 2.1）查看的平均页数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| 页面查看次数 / 独特访客量 | 每个访问网站的独特访客查看的平均页数。 | `[Page Views] / [Unique Visitors]` |
| 页面查看次数 / 访问次数 | 用户单次访问网站期间查看的平均页数。 | `[Page Views] / [Visits]` |
| 页面速度 | 一条内容产生的额外页面查看次数。该量度可以帮助您确定哪些内容可以带来更多参与。 | `[Page Views] / [Visits]` |
| 重新加载次数 / 页面查看次数 | 导致重新加载或刷新页面的页面查看次数的百分比。 | `[Reloads] / [Page Views]` |
| 收入 / 订单 | 网站上每笔完成的交易或订单所产生的平均收入金额。 | `[Revenue] / [Orders]` |
| 收入 / 访问次数 | 单次访问网站产生的平均收入金额。 | `[Revenue] / [Visits]` |
| 收入 / 访客 | 每个访问网站的单独访客产生的平均收入金额。 | `[Revenue] / [Unique Visitors]` |
| 状态查看次数 | 对应用程序的不同状态或屏幕的查看次数 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| 逗留时间/用户（状态） | 访客在访问网站上处于特定状态的平均时长 | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 独特访客量 / 在 7 天后回访的独特访客量 | 在 7 天或更长时间后回访的独特访客的百分比。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| 用户（移动） | 移动应用程序的用户总数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 访问次数 / 访客 | 独特访客对于网站的平均访问次数。 | `[Visits] / [Unique Visitors]` |
| 加权跳出率 | 功能 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
