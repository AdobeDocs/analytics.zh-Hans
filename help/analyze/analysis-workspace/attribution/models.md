---
title: 归因模型和回顾时间范围
description: 不同类型的归因如何在维度项目之间划分点数。
feature: Attribution
role: User, Admin
exl-id: f36de41e-1c53-477d-b326-528fbd4ec9ec
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '1603'
ht-degree: 94%

---

# 归因模型和回顾时间范围

Adobe Analytics 中的归因概念包含两个组件：

* **归因模型：**&#x200B;此模型描述某个群组中点击的转化分布。例如，首次接触或最后接触。
* **归因回顾窗口：**&#x200B;回顾窗口描述针对每个模型考虑的点击分组。例如，访问或访客。

## 归因模型

| UI 图标 | 归因模型 | 定义 | 使用时间 |
| --- | --- | --- | --- |
| ![最后接触](assets/last_touch1.png) | 最后接触 | 将 100% 的点数分给转化前最近发生的接触点。 | 最基本也是最常见的归因模型。它通常用于转化，并且考虑周期短。最后接触模型通常由管理搜索营销或分析内部搜索关键字的团队使用。 |
| ![首次接触](assets/first_touch.png) | 首次接触 | 将 100% 的点数分给在归因回顾时间范围中看到的首次接触点。 | 这是另一种常见的归因模型，可用于对旨在提升品牌认知度或促进客户获取的营销渠道进行分析。它经常由展示广告或社交渠道营销团队使用，但其对于评估现场产品推荐的有效性也很有帮助。 |
| ![同一接触](assets/same_touch.png) | 同一接触 | 将 100% 的点数分给发生转化的同一点击。如果在转化的同一点击中没有发生接触点，则它将存储在“无”下。 | 在对转化时立即呈现的内容或用户体验进行评估时，这个模型将会很有帮助。产品或设计团队通常会使用此模型来对发生转化的页面有效性进行评估。 |
| ![线性](assets/linear.png) | 线性 | 将相同的点数分给促成转化的每个接触点。 | 对于需要更频繁的客户参与且具有较长考虑周期或用户体验的转化，此模型将非常有用。它通常由负责对移动设备应用程序通知有效性进行衡量的团队使用，或用于基于订阅的产品。 |
| ![U 型](assets/u_shaped.png) | U 型 | 将 40% 的点数分给首次交互，40% 的点数分给最后交互，并将剩余 20% 的点数分给这两次交互之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于具有两个接触点的转化，两个接触点各分得 50% 的点数。 | 此模型非常适用于那些重视引入或关闭转化交互，但同时希望识别辅助交互的用户。U 型归因通常由采取更均衡方法但同时希望更多归功于找到或结束转化的渠道的团队使用。 |
| ![J 曲线](assets/j_shaped.png) | J 曲线 | 将 60% 的点数分给最后一次交互，20% 的点数分给首次交互，并将剩余 20% 的点数分给这两次交互之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于具有两个接触点的转化，将 75% 的点数分给最后一次交互，将 25% 的点数分给首次交互。 | 此模型非常适合那些优先考虑首次接触和最后接触，但同时更加关注最后互动的人。J 曲线归因通常由采取更均衡方法但同时希望更多归功于结束转化的渠道的团队使用。 |
| ![反向 J 型](assets/inverse_j.png) | 反向 J | 将 60% 的点数分给首次接触点，20% 的点数分给最后接触点，并将剩余 20% 的点数分给这两次接触点之间的任意接触点。对于具有单一接触点的转化，它将分得 100% 的点数。对于具有两个接触点的转化，将 75% 的点数分给首次交互，将 25% 的点数分给最后一次交互。 | 此模型非常适合那些优先考虑首次接触和最后接触，但同时更加关注首次互动的人。反向 J 归因由采取更均衡方法但同时希望更多归功于启动转化的渠道的团队使用。 |
| ![自定义](assets/custom.png) | 自定义 | 允许您指定要赋予给“首次接触点”、“最后接触点”以及“这两次交互之间的任意接触点”的权重。即便输入的自定义数字相加之和并不等于 100，指定的值也会被标准化为 100%。对于具有单一接触点的转化，它将分得 100% 的点数。对于具有两个接触点的交互，中间参数会被忽略。然后，首次接触点和最后接触点会被标准化为 100%，并相应地分配点数。 | 此模型非常适合那些希望完全控制其归因模型，并具有其他归因模型所不具备的特定需求的人。 |
| ![时间衰减](assets/time_decay.png) | 时间衰减 | 采用具有自定义半衰期参数的指数衰减，默认值为 7 天。每个渠道的权重，取决于在接触点启动与最终转化之间流逝的时间。用于确定点数的公式是 `2^(-t/halflife)`，其中 `t` 是接触点与转化之间流逝的时间。然后，所有接触点均被标准化为 100%。 | 非常适合定期运行视频广告或针对预定日期的事件进行营销的团队。营销活动后发生转化所需的时间越长，获得的点数就越少。 |
| ![参与率](assets/participation.png) | 参与率 | 将 100% 的点数分给所有独特的接触点。与其他归因模型相比，转化总数被夸大。参与率会对重复出现的渠道进行重复数据删除。 | 非常适用于了解客户参与特定交互的频率。媒体组织经常使用此模型来计算内容速率。零售组织通常使用此模型来了解其网站的哪些内容对于转化至关重要。 |
| ![算法](assets/algorithmic.png) | [算法](algorithmic.md) | 使用统计技术动态确定所选量度的最佳点数分配。 | 有助于避免在为业务选择正确的归因模型时进行猜测或推断。 |

## 回顾窗口

回顾窗口是指转化应回顾以包含接触点所花费的时间。在查看不同回顾窗口时，为首次交互分配更多点数的归因模型存在较大的差异。

* **访问回顾窗口：**&#x200B;回顾到发生转化的访问之初。访问回顾窗口比较狭隘，因为不考虑访问之外的其他因素。访问回顾窗口会遵守虚拟报表包中修改的访问定义。

* **访客回顾窗口：**&#x200B;回顾到当前日期范围当月 1 日的所有访问。访客回顾窗口比较广泛，因为考虑范围包括多次访问。访客回顾时间范围会考虑报表日期范围月初的所有值。例如，如果报表日期范围为 9 月 15 日到 9 月 30 日，则访客回顾日期范围将为 9 月 1 日到 9 月 30 日。

* **自定义回顾时间范围：**&#x200B;允许您将归因时间范围扩展到超出报表日期范围（最多 90 天）。会对报表期内的每次转化评估其自定义回顾时间范围。例如，对于2月20日发生的转化，10天的回顾时间范围将评估归因模型中2月10日至2月20日的所有维度接触点。

>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自定义回看窗口期](https://video.tv.adobe.com/v/40042?quality=12&learn=on&captions=chi_hans){target="_blank"}。

>[!ENDSHADEBOX]


## 示例

请仔细研究下面的示例：

1. 9 月 15 日，某位访客通过付费搜索广告访问您的网站，然后离开。
2. 9 月 18 日，该访客通过朋友提供的社交媒体链接再次访问您的网站。他将多个物品添加到购物车，但没有购买任何物品。
3. 9 月 24 日，您的营销团队向他们发送一封电子邮件，其中包含购物车中某些物品的产品建议券。他应用了产品建议券，但访问了其他几个网站，查看是否有其他产品建议券可用。他通过展示广告找到另一个网站，并最终购买了价值 50 美元的物品。

根据您的回顾窗口和归因模型，渠道会收到不同比例的点数。以下是一些典型的有趣示例：

* 使用&#x200B;**首次接触**&#x200B;和&#x200B;**访问回顾窗口**，归因仅考虑第三次访问。在电子邮件与展示广告之间，电子邮件是首次接触点，因此电子邮件在 50 美元的购买中获得 100% 的点数。
* 使用&#x200B;**首次接触**&#x200B;和&#x200B;**访客回顾窗口**，归因会考虑所有三次访问。付费搜索是首次接触点，因此它在 50 美元的购买中获得 100% 的点数。
* 使用&#x200B;**线性归因模型**&#x200B;和&#x200B;**访问回顾窗口**，则电子邮件与展示广告平分点数。这两个渠道各自获得贡献 25 美元的点数。
* 使用&#x200B;**线性归因模型**&#x200B;和&#x200B;**访客回顾窗口**，则付费搜索、社交、电子邮件与展示广告平分点数。每个渠道各自获得此次购买中贡献 12.50 美元的点数。
* 使用 **J 形归因模型**&#x200B;和&#x200B;**访客回顾窗口**，则付费搜索、社交、电子邮件和展示广告均可获得点数。
   * 将 60% 的点数分给展示广告，其贡献价值是 30 美元。
   * 将 20% 的点数分给付费搜索，贡献价值是 10 美元。
   * 剩余的 20% 点数分给社交和电子邮件，二者的贡献价值均为 5 美元。
* 使用&#x200B;**时间衰减归因模型**&#x200B;和&#x200B;**访客回顾窗口**，则付费搜索、社交、电子邮件和展示广告均可获得点数。使用默认的 7 天半衰期：
   * 显示接触点与转化之间的间隔为 0 天。`2^(-0/7) = 1`
   * 电子邮件接触点与转化之间的间隔为 0 天。`2^(-0/7) = 1`
   * 社交接触点与转化之间的间隔为 6 天。`2^(-6/7) = 0.552`
   * 付费搜索接触点与转化之间的间隔为 9 天。`2^(-9/7) = 0.41`
   * 将这些值标准化处理之后得到以下结果：
      * 展示广告：33.8%，贡献价值是 16.88 美元
      * 电子邮件：33.8%，贡献价值是 16.88 美元
      * 社交：18.6%，贡献价值是 9.32 美元
      * 付费搜索：13.8%，贡献价值是 6.92 美元
* 使用&#x200B;**参与率**&#x200B;和&#x200B;**访客回顾窗口**，整个$50归因于付费搜索、社交、电子邮件和显示。 如果您将收入视为趋势报表，而不是排名报表，则会在访客接触给定营销渠道的每一天分别看到$50。

>[!TIP]
>
>此外，如果点数属于多个渠道，则其他转化事件（例如订单或自定义事件）也会获得点数。例如，如果使用线性归因模型分析得出两个渠道参与了自定义事件，则这两个渠道将分别获得 50% 的点数。这些事件分数在所有访问中相加，然后在报表中四舍五入到最接近的整数。
