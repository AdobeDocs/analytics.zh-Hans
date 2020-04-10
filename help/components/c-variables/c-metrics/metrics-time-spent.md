---
description: Adobe Analytics优惠了各种花费时间指标和维度。 了解它们是什么以及如何计算。
title: 逗留时间
topic: Metrics
translation-type: tm+mt
source-git-commit: 8df1fdfb048dd69b4926b7b812ec5dfea4a97b89

---


# [!UICONTROL Time spent]

Various [!UICONTROL 'time spent'] metrics and dimensions are offered across Adobe Analytics products.

## [!UICONTROL 'Time spent'] 量度

| 量度 | 定义 | 在 |
|---|---|---|
| [!UICONTROL Total seconds spent] | 表示访客与特定维度项目交互所用的总时间。包括所有后续点击中的值和持久性的实例。对于 prop，也会在后续链接事件中统计逗留时间。 | Analysis Workspace、Reports &amp; Analytics、Report Builder（称为“总逗留时间”）、Data Warehouse、Ad Hoc Analysis |
| [!UICONTROL Time spent per visit] (Seconds) | *所用总秒数/（访问次数 - 跳出次数）*<br>表示访客在每次访问期间与特定维度项目交互所用的平均时间。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL Time spent per visitor] (Seconds) | *所用总秒数/独特访客&#x200B;*<br>表示在访客的存留期（访客 Cookie 的时长）内，访客与特定维度项目交互所用的平均时间。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL Average time spent on site] (Seconds) | 表示每个序列中与特定维项目交互的总时间访客数和维项目。 它不仅仅限于“站点”平均值，正如其名称所暗示的。 有关序列的详细信息，请参阅“‘逗留时间’的计算方式”部分。<br>**注意&#x200B;**：由于计算中所用的分母不同，因此，此量度很可能会与维度项目级别的“每次访问逗留时间”有所不同。 | Analysis Workspace、Reports &amp; Analytics（以分钟为单位显示）、Report Builder（以分钟为单位显示）、Ad Hoc Analysis |
| [!UICONTROL Average time spent on page] | 已弃用的量度。<br>如果需要维度项目的平均时间，我们建议您使用“网站平均逗留时间”。 | Report Builder（当请求中包含维度时） |
| [!UICONTROL Total session length], a.k.a. [!UICONTROL Previous session length] | 仅限移动设备应用程序 SDK。<br>对于前一会话，在下次启动应用程序时进行确定。以秒计算，此度量在应用程序处于后台时（仅在使用中时）不计数。 这是一个会话级别的量度。<br>例如：我们安装了应用程序 ABC 并将其启动，在使用了 2 分钟后关闭了该应用程序。在此会话时间内不会发送任何相关数据。The next time we launch the app, [!UICONTROL Previous Session Length] will be sent with a value of 120. | Analysis Workspace、Reports &amp; Analytics、Report Builder、Mobile Services UI |
| [!UICONTROL Average session length] (移动设备) | *会话总时长/（启动次数 – 首次启动次数）*<br>仅限移动设备应用程序 SDK。这是一个会话级别的量度。 | Report Builder、Mobile Services UI、Ad Hoc Analysis |

## “逗留时间”维度

| 维度 | 定义 | 在 |
|---|---|---|
| [!UICONTROL Time spent per visit - granular] | 访问期间的总逗留时间将精确至秒，且应用于访问中的每次点击。这是一个访问级别的维度。 | Analysis Workspace、Ad Hoc Analysis |
| [!UICONTROL Time spent per visit - bucketed] | 粒度尺寸分为9个不同的范围。 这是一个访问级别的维度。范围包括：<ul><li>不到1分钟</li><li>1-5 分钟</li><li>5-10 分钟</li><li>10-30 分钟</li><li>30-60 分钟</li><li>1-2 小时</li><li>2-5 小时</li><li>5-10 小时</li><li>10-15 小时</li></ul>**注意**：不会有更高的时段，因为一次访问在活动 12 小时后就会过期。 | Analysis Workspace、Reports &amp; Analytics、Report Builder、Ad Hoc Analysis |
| [!UICONTROL Time spent on page - granular] | 每次点击的总逗留时间，精确至秒。这是一个点击级别的维度，包括页面查看次数和链接事件。尽管其名称中包含页面，但它并不限于“页面”维度。 | Analysis Workspace、Ad Hoc Analysis |
| [!UICONTROL Time spent on page - bucketed] | 粒度分布在10个不同的范围内；但是，分时段的维度仅计算页面视图(不包括链接事件)。 这是点击级维度。 范围包括：<ul><li>少于 15 秒</li><li>15-29 秒</li><li>30-59 秒</li><li>1到3分钟</li><li>3到5分钟</li><li>5到10分钟</li><li>10到15分钟</li><li>15到20分钟</li><li>20到30分钟</li><li>超过30分钟</li></ul> | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |

## ‘逗留时间’的计算方式

Adobe Analytics uses explicit values (including link events and video views) to calculate [!UICONTROL Time Spent].

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. For similar reasons, [!UICONTROL Bounce Visits] (i.e. visits with a single hit) also does not have a &#39;time spent&#39; associated with it.

在所有逗留时间的计算中，**分子**&#x200B;都是“所用总秒数”。

在 Adobe Analytics 中，**分母**&#x200B;不可作为单独的量度使用。对于点击级别的“逗留时间”量度，分母即是序列。一个序列是一组连续的点击，其中给定的变量包含相同的值（不论是设置、扩展还是保留的值）。“扩展”是指为了计算逗留时间，而在页面查看事件之间（即在后续链接事件中）持续保留 prop。

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL 'Instances'] or [!UICONTROL 'Page Views'], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* 由于“逗留时间”无从知晓，因此跳出和退出点击量也会从分母中删除。

## 常见问题解答

**问题 1：能否将所有“逗留时间”量度应用于任何维度？**

答案：可应用于任何维度的“逗留时间”量度包括：

* [!UICONTROL Total seconds spent]

* [!UICONTROL Time spent per visit] (Seconds)

* [!UICONTROL Time spent per visitor] (Seconds)

* [!UICONTROL Average time spent on site] (Seconds)

**问题 2：哪个逗留时间维度最适合用于包含其他维度的划分？**

答：维 [!UICONTROL Time Spent on Page – granular] 是命中级维。 按其他维度划分此维度将显示点击持续的秒数，其中也会显示划分维度。在下面的示例中，搜索词“分类”与 54 秒、59 秒等的点击时间相关联，这可能表示访客正在花时间阅读针对该搜索词返回的内容。

![](assets/time-spent1.png)

**第三季度：哪些度量适合于的维度[!UICONTROL Time Spent on Page – granular]?**

答案：任何量度均合适。此维度将显示发生事件的具体点击的逗留时间。逗留时间越长意味着访客在发生事件的页面（点击）中停留的时间越长。

![](assets/time-spent2.png)

**第4季度：有何[!UICONTROL Average Time Spent on Site]不同[!UICONTROL Time Spent per Visit]?**

答案：这些量度的不同之处在于分母：

* [!UICONTROL Average time spent on site] 使用包含尺寸项的序列。

* [!UICONTROL Time spent per visit] 使用访问计数

因此，这些量度可能会在访问级别产生相似的结果，但在点击级别则将产生不同的结果。

**问题5:为什么细分总数与[!UICONTROL Average Time Spent on Site]父行项目不匹配？**

答：因为 [!UICONTROL Average Time Spent on Site] 这取决于维度的未损坏序列，而内部报表在计算这些运行时不依赖于外部报表。

例如，请考虑以下访问。
|hit#|1|2|3||—|—|—||**所用秒**|30|100|10||**页面名称**|主页|产品|主页||**日期**|Jan 1|Jan 1|Jan 1|Jan 1|

在计算主页的时间时，它将为(30+10)/2=20，但按天划分时间将给出(30+10)/1=40，因为该日的运行在1月1日是单次未中断的。

因此，这些量度可能会在访问级别产生相似的结果，但在点击级别则将产生不同的结果。

## 计算示 [!UICONTROL Time Spent] 例

假定下面一组服务器调用针对的是单次访问中的单个访客：

| 访问点击次数 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **访问经过的时间（秒）** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **花费的秒数** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **点击类型** | 页面 | 链接 | 页面 | 页面 | 页面 | 页面 | 页面 |
| **页面名称** | 主页 | - | 产品 | 主页 | 主页（重新加载） | 购物车 | 订单确认 |
|  |  |  |  |  |  |  |  |
| **prop1** | A（集） | A（扩展） | 未设置 | B（设置） | B（设置） | A(set) | C（集） |
| **prop1花费的秒数** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | 红色（设置） | 红色（已保留） | （过期） | 蓝色（设置） | 蓝色（设置） | 蓝色（已保留） | 红色（设置） |
| **eVar1 所用秒数** | 30 | 50 | - | 10 | 40 | 60 | - |

根据以上表格，逗留时间量度计算如下：

| prop1 | 所用总秒数 | 每次访问逗留时间 | 每位访客逗留时间 | 序列计数 | 网站平均逗留时间 |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| 未归属的时间 | 100 | - | - | - | - |

| eVar1 | 所用总秒数 | 每次访问逗留时间 | 每位访客逗留时间 | 序列计数 | 网站平均逗留时间 |
|---|---|---|---|---|---|
| 红色 | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| 蓝色 | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| 未归属的时间 | 100 | - | - | - | - |

每次访问逗留时间（粒度）：290
页面逗留时间（粒度）：10、30、40、50、60、100

支持此示例的一些其他注释：

* 所有逗留时间计算都基于访问经过的时间，该时间在访问的首次点击时以零开始统计。

* “所用秒数”是当前点击的时间戳和下次点击的时间戳之间的差值。因此，访问（和弹回）的最后一次点击没有花费时间。

* “序列”是连续的一组点击，其中给定变量包含相同的值（无论是通过设置、向前扩展还是持续）。 例如，prop1 &quot;A&quot;有两个序列：点击1和2，点击6。 访问上次点击的值不会开始新序列，因为上次点击没有停留时间。 网站平均停留时间使用序列作为分母。

   * 仅出于计算逗留时间的目的，prop 会从页面点击“扩展”到后续链接点击，如上面点击 2 的 prop1 所示。这允许点击 1（“A”）中为 prop1 所设置的值累计点击 2 的逗留时间。

   * eVar 可累计任何设置或保留 eVar 的点击的逗留时间。eVar 持久性由“Analytics”>“管理员”中的 eVar 设置定义。

