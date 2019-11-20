---
description: Adobe Analytics 提供了多种逗留时间量度和维度。了解它们的含义以及它们的计算方式。
solution: Analytics
title: 逗留时间
topic: Metrics
translation-type: tm+mt
source-git-commit: e04051a655a842092f3d99ba784a738e86d65eb2

---


# [!UICONTROL 所花费的时间]

Adobe [!UICONTROL Analytics产品提供了各种] “花费时间”指标和维度。

## [!UICONTROL “停留时间”指标]

| 量度 | 定义 | 适用的功能领域 |
|---|---|---|
| [!UICONTROL 所用总秒数] | 表示访客与特定维度项目交互所用的总时间。包括所有后续点击中的值和持久性实例。 对于 prop，也会在后续链接事件中统计逗留时间。 | Analysis Workspace、Reports &amp; Analytics、Report Builder（称为“总停留时间”）、Data Warehouse、Ad Hoc Analysis |
| [!UICONTROL 每次访问所花费的时间] （秒） | *所用秒数/（访问——弹回次数）*<br>表示访客在每次访问期间与特定维度项目交互的平均时间。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL 每位访客的停留时间] （秒） | *停留的秒数／唯一访*<br>客总数表示访客在整个访客生命周期中与特定维度项目交互的平均时间（Cookie的长度）。 | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |
| [!UICONTROL 网站平均停留时间] （秒） | 表示访客与特定维度项目交互所用的总时间，其中每个序列包含一个维度项目。它并非像其名称所暗示的那样仅限于“网站”平均值。有关序列的详细信息，请参阅“如何计算所花费的时间”部分。<br>**注意**:由于计算中的分母差异，此度量很可能与维项目级别的“每次访问的时间”不同。 | Analysis Workspace、Reports &amp; Analytics（以分钟为单位显示）、Report Builder（以分钟为单位显示）、Ad Hoc Analysis |
| [!UICONTROL 页面平均逗留时间] | 已弃用的量度。<br> 相反，如果需要维度项目的平均时间，建议您使用“平均在站点上停留的时间”。 | Report Builder（当请求中包含维度时） |
| [!UICONTROL 会话总长]，又称上一 [!UICONTROL 会话长度] | 仅限移动设备应用程序 SDK。<br>对于前一会话，在下次启动应用程序时进行确定。以秒为单位进行计算，此量度只有在应用程序处于使用状态时才会统计，在应用程序处于后台时则不会统计。这是一个会话级别的量度。<br>示例：我们安装应用程序ABC，启动并使用它2分钟，然后关闭该应用程序。 不会发送有关此会话时间的数据。 The next time we launch the app, [!UICONTROL Previous Session Length] will be sent with a value of 120. | Analysis Workspace, Reports &amp; Analytics, Report Builder,Mobile Services UI |
| [!UICONTROL 平均会话长度] （移动） | *会话总长度/（启动项——首次启动项）*<br>仅限移动应用程序SDK。 这是一个会话级别的量度。 | Report Builder,Mobile Services UI, Ad Hoc Analysis |

## “停留时间”维度

| 维度 | 定义 | 适用的功能领域 |
|---|---|---|
| [!UICONTROL 每次访问逗留时间 - 粒度] | 访问期间的总逗留时间将精确至秒，且应用于访问中的每次点击。这是一个访问级别的维度。 | Analysis Workspace，临时分析 |
| [!UICONTROL 每次访问逗留时间 - 分段统计] | 粒度维度分为 9 个不同的范围。这是一个访问级别的维度。这些范围包括：<ul><li>少于 1 分钟</li><li>1-5 分钟</li><li>5-10 分钟</li><li>10-30 分钟</li><li>30-60 分钟</li><li>1-2 小时</li><li>2-5 小时</li><li>5-10 小时</li><li>10-15 小时</li></ul>**注意**:不能存在高于此的时段，因为访问在12小时的活动后过期。 | Analysis Workspace, Reports &amp; Analytics, Report Builder，临时分析 |
| [!UICONTROL 页面逗留时间 - 粒度] | 每次点击的总逗留时间，精确至秒。这是一个点击级别维度，它包含页面查看和链接事件。 尽管其名称不限于“页面”维。 | Analysis Workspace，临时分析 |
| [!UICONTROL 页面逗留时间 - 分段统计] | 粒度维度分为 10 个不同的范围；但是，分段统计的维度只计算页面查看次数（不包括链接事件）。这是一个点击级别的维度。这些范围包括：<ul><li>少于 15 秒</li><li>15-29 秒</li><li>30-59 秒</li><li>1-3 分钟</li><li>3-5 分钟</li><li>5-10 分钟</li><li>10-15 分钟</li><li>15-20 分钟</li><li>20-30 分钟</li><li>多于 30 分钟</li></ul> | Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis |

## 如何计算“停留时间”

Adobe Analytics 使用显式值（包括链接事件和视频查看次数）来计算[!UICONTROL 逗留时间]。

>[!NOTE]
>
>Without link events like [!UICONTROL Video Views] or [!UICONTROL Exit Links], time spent on the last hit of a visit cannot be known. For similar reasons, [!UICONTROL Bounce Visits] (i.e. visits with a single hit) also does not have a 'time spent' associated with it.

The **numerator** in all time spent calculations is total seconds spent.

The **denominator** is not available as a separate metric in Adobe Analytics. 对于点击级别的“停留时间”指标，分母是序列。 一个序列是一组连续的点击，其中给定的变量包含相同的值（不论是设置、扩展还是保留的值）。“向前扩展”是指为计算所花费的时间而在页面查看之间（即在后续链接事件之间）保留prop。

* For example, in the case of [!UICONTROL Page Name] or other dimensions at the hit level, the denominator is essentially [!UICONTROL 'Instances'] or [!UICONTROL 'Page Views'], but with reloads and unset values (e.g. link events) counted as a single interaction (a sequence).

* 跳出和退出点击也会从分母中删除，因为无法知道“停留时间”。

## 常见问题解答

**第1季度：是否可以将所有“所花时间”指标应用于任何维度？**

答：可应用于任何维度的“停留时间”指标包括：

* [!UICONTROL 所用总秒数]

* [!UICONTROL 每次访问所花费的时间] （秒）

* [!UICONTROL 每位访客的停留时间] （秒）

* [!UICONTROL 网站平均停留时间] （秒）

**第2季度：在与其他维度进行细分时，最好使用哪个时间维度？**

A: The [!UICONTROL Time Spent on Page – granular] dimension is a hit-level dimension. 按其他维度划分此维度将显示点击持续的秒数，其中也会显示划分维度。在以下示例中，搜索词“classifieds”与54秒、59秒等的点击时间相关联，这可能表示访客花时间阅读该词返回的内容。

![](assets/time-spent1.png)

**第三季度：针对页面停留时间——粒度[!UICONTROL 维度，哪些指标合适]?**

答：任何指标。 维度将显示在发生事件的确切点击上花费的时间。 逗留时间越长意味着访客在发生事件的页面（点击）中停留的时间越长。

![](assets/time-spent2.png)

**第4季度：网站平[!UICONTROL 均停留时间与每次访问][!UICONTROL 停留时间有何不同]?**

答：区别在于度量中的分母：

* [!UICONTROL 网站平均停留时间] ，使用包含维度项的序列。

* [!UICONTROL 每次访问所花费的时间] ，使用访问计数

因此，这些量度可能会在访问级别产生相似的结果，但在点击级别则将产生不同的结果。

## 逗留时间 [!UICONTROL 计算示例]

假定下面一组服务器调用针对的是单次访问中的单个访客：

| 访问点击次数 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **访问已用时间（以秒为单位）** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **所用秒数** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **点击类型** | 页面 | 链接 | 页面 | 页面 | 页面 | 页面 | 页面 |
| **页面名称** | 主页 | - | 产品 | 主页 | 主页（重新加载） | 购物车 | 订单确认 |
|  |  |  |  |  |  |  |  |
| **prop1** | A（设置） | A（向前扩展） | 未设置 | B（集） | B（集） | A（设置） | C（设置） |
| **prop1 所用秒数** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | 红色（设置） | 红色（已保留） | （过期） | 蓝色（设置） | 蓝色（设置） | 蓝色（持续） | 红色（设置） |
| **eVar1秒** | 30 | 50 | - | 10 | 40 | 60 | - |

根据上表，逗留时间指标按如下方式计算：

| prop1 | 所用总秒数 | 每次访问所花费的时间 | 每位访客的停留时间 | 序列计数 | 网站平均停留时间 |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| 未归类的时间 | 100 | - | - | - | - |

| eVar1 | 所用总秒数 | 每次访问所花费的时间 | 每位访客的停留时间 | 序列计数 | 网站平均停留时间 |
|---|---|---|---|---|---|
| 红色 | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| 蓝色 | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| 未归类的时间 | 100 | - | - | - | - |

每次访问所花费的时间（粒度）:290页面停留时间（粒度）:10、30、40、50、60、100

支持此示例的一些其他注释：

* 所有花费的时间计算均基于访问的已用时间，该时间在访问的第一次点击时从零开始。

* “所花费的秒数”是当前点击的时间戳与下一次点击的时间戳之间的差异。 因此，访问的最后一次点击（和跳出）没有逗留时间。

* “序列”是指一组连续的点击，其中给定的变量包含相同的值（不论是设置、扩展还是保留的值）。例如，prop1“A”有两个序列：点击 1 &amp; 2 和点击 6。访问的最后一次点击的值不会开始一个新序列，因为最后一次点击没有逗留时间。网站平均逗留时间使用序列作为分母。

   * 仅出于停留时间的目的，prop从页面点击“向前扩展”到后续链接点击，如上所示，在点击2时prop1会“向前扩展”。 这允许点击 1（“A”）中为 prop1 所设置的值累计点击 2 的逗留时间。

   * eVar可累计在设置或保留eVar的任何点击上所花费的时间。 eVar持久性由“分析”&gt;“管理”中的eVar设置定义。

