---
description: Adobe提供了多种您可以使用的计算指标。 本页列出了这些量度及其预期用途。
title: 默认计算量度
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: 1382d8901b980db016521a3051de23d8d5b71f57
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 40%

---

# 默认计算量度

Adobe Analytics提供了各种计算指标以涵盖最常见的用例。 默认情况下，这些计算量度在Analysis Workspace中可用。

以下是Adobe提供的每个计算指标及其目标函数以及用于计算它的基础公式的列表：

>[!NOTE]
>
>除了此页面上描述的默认计算指标之外，您还可以向报表包添加其他计算指标。
>
>您可以：
> * 为流媒体收集加载项添加默认的计算量度，如[计算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)中所述
> * 从现有量度创建自定义计算量度，如[计算量度和高级计算（派生）量度](/help/components/c-calcmetrics/cm-overview.md)中所述。


| 计算量度名称 | 功能 | 公式 |
| --- | --- | --- |
| 客户获取链接点击次数 | 人员点击旨在产生网站流量的链接的次数。 | `[Campaign Click-throughs]` |
| 操作 | 应用程序中执行的操作总数 | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| 应用程序用户 | 移动应用程序的用户总数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 平均会话时长（移动设备） | 在一次会话期间访客在网站上逗留的平均时间。 | 空白 |
| 网站平均逗留时间 | 访客离开或导航离开之前在网站上逗留的平均时间。 | `[Average Time Spent on Site (Seconds)]` |
| 跳出率 | 包含一次点击的访问次数与该页面上的访问次数之间的比率。 此量度可帮助您了解哪些维度项目的跳出率最高，或查看一段时间内网站的累计总跳出率。 | `[Bounces] / [Entries]` |
| 机器人页面查看率 | 机器人页面查看次数与页面查看总次数之间的比率。 | `[Bot Page Views] / [Page Views]` |
| 内容周转率 | 在网站上创建和发布新内容的速度以及新内容能够多快地吸引用户参与。 | `[Page Views] / [Visits]` |
| 转化率 | 执行了所需操作（如进行了购买）的访客的百分比。 | `[Orders] / [Visits]` |
| 登录率 | 在指定页面上进入网站的访客占网站上会话总数的百分比。 | `[Entries] / [Visits]` |
| 预计独特访客(ITP 2.1) | 对于ITP访客（Safari浏览器中的用户），将独特访客除以2或更小。 此计算量度假定您是使用客户端JavaScript（而不是使用CNAME实施）设置的Cookie。 从ITP 2.1开始，使用客户端JavaScript设置Cookie的实施会受到影响。有关详细信息，请参阅[智能防跟踪](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Experience Cloud ID 覆盖 | 拥有 Experience Cloud ID 的访客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 退出率 | 查看特定页面后离开网站的访客的百分比。 | `[Exits] / [Visits]` |
| ITP 2.1独特访客/独特访客 | 使用受ITP 2.1 Cookie限制影响的浏览器的独特访客百分比。 | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| 订购协助 | 渠道或来源促成客户历程向购买推进但最终未购买的次数。 | `[Orders (Visit Participation)] - [Orders]` |
| 订购/访问 | 访问网站并完成交易的百分比。 | `[Orders] / [Visits]` |
| 订单/访客 | 网站每位访客生成的平均订单数或交易数 | `[Orders] / [Unique Visitors]` |
| 页面查看数/估计的独特访客数 (ITP 2.1) | 估计的独特访客数 (ITP 2.1) 查看的平均页数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| 页面查看次数/独特访客 | 每个访问网站的独特访客查看的平均页数。 | `[Page Views] / [Unique Visitors]` |
| 页面查看/访问 | 用户单次访问网站期间查看的平均页数。 | `[Page Views] / [Visits]` |
| 页面周转率 | 一段内容生成的其他页面查看次数。 此量度可帮助您确定哪些内容可推动更多参与。 | `[Page Views] / [Visits]` |
| 重新载入/页面查看 | 导致重新加载或刷新页面的页面查看次数的百分比。 | `[Reloads] / [Page Views]` |
| 收入/订单 | 网站上每笔完成的交易或订单所产生的平均收入金额。 | `[Revenue] / [Orders]` |
| 收入/访问 | 单次访问网站产生的平均收入金额。 | `[Revenue] / [Visits]` |
| 收入/访客 | 每个访问网站的单独访客产生的平均收入金额。 | `[Revenue] / [Unique Visitors]` |
| 状态视图 | 查看应用程序的不同状态或屏幕的次数 | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| 逗留时间/用户（状态） | 平均访客在网站上处于特定状态所花费的时间 | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 独特访客/7天后回访的独特访客 | 在 7 天或更长时间后回访的独特访客的百分比。 | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| 用户（移动设备） | 移动应用程序的用户总数 | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| 访问/访客 | 独特访客对于网站的平均访问次数。 | `[Visits] / [Unique Visitors]` |
| 加权跳出率 | 功能 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
