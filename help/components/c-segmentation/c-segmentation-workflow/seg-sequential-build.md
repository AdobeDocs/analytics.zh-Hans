---
description: 顺序区段使用 THEN 运算符（而非 AND 或 OR）创建。THEN 意味着出现一个区段标准后，接着出现另一个区段标准。默认情况下，顺序区段会标识所有匹配数据，并显示过滤器“包含每个人”。可以使用“仅在序列前”和“仅在序列后”选项将顺序区段进一步过滤为匹配点击的子集。
seo-description: 顺序区段使用 THEN 运算符（而非 AND 或 OR）创建。THEN 意味着出现一个区段标准后，接着出现另一个区段标准。默认情况下，顺序区段会标识所有匹配数据，并显示过滤器“包含每个人”。可以使用“仅在序列前”和“仅在序列后”选项将顺序区段进一步过滤为匹配点击的子集。
seo-title: 构建顺序区段
solution: Analytics
title: 构建顺序区段
topic: 区段
uuid: fb9f1c7-a738-416a-aa2-d77 e40 fa7 e61
translation-type: tm+mt
source-git-commit: b21f741216af8edc631cc271618f638d46a16a96

---


# 构建顺序区段

顺序区段使用 THEN 运算符（而非 AND 或 OR）创建。THEN 意味着出现一个区段标准后，接着出现另一个区段标准。默认情况下，顺序区段会标识所有匹配数据，并显示过滤器“包含每个人”。可以使用“仅在序列前”和“仅在序列后”选项将顺序区段进一步过滤为匹配点击的子集。

![](assets/before-after-sequence.png)

此外，您还可以使用[After 和 Within 运算符](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_07708877D06742998C6237DD9FD194EA)将顺序区段限制为检查点之间的特定持续时间、粒度和计数。

## 包含每个人 {#section_75ADDD5D41F04800A09E592BB2940B35}

在创建一个设置了“包含每个人”的区段时，该区段能够识别匹配整个给定模式的路径。这是一个基本的序列区段示例，用于查找同一访客访问的一个点击（页面 A）及下一个点击（页面 B）。将区段设置为“包含每个人”。

![](assets/sequence-filter.png)

| 如果结果… | 序列 |
|--- |--- |
| 匹配 | A then B<br>A then (in a different visit) B<br>A then D then B |
| 不匹配 | B -&gt; A |

## “仅在序列前”和“仅在序列后” {#section_736E255C8CFF43C2A2CAAA6D312ED574}

**[!UICONTROL 仅在序列前]** 和 **仅在序列后[!UICONTROL 选项可将区段过滤为指定序列之前或之后的数据子集。]**

* **仅在序列前**：包含序列之前的所有点击 + 该序列自身的第一次点击（见示例 1、3）。如果序列在路径中出现多次，则“仅在序列前”包括该序列最后一个实例的第一次点击和之前的所有点击（见示例 2）。
* **仅在序列后**：包含序列之后的所有点击 + 该序列自身的最后一次点击（见示例 1、3）。如果序列在路径中出现多次，则“仅在序列后”包括该序列首个实例的最后一次点击和之后的所有点击（见示例 2）。

以 B -&gt; D 序列为例。三种过滤器将按以下方式确定点击量：

**示例 1：B -&gt; D 出现一次**

| 示例 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|
| 包含每个人 | A | B | C | D | E | F |
| 仅在序列前 | A | B |  |  |  |  |
| 仅在序列后 |  |  |  | D | E | F |

**示例 2：B -&gt; D 出现多次**

| 示例 | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| 包含每个人 | A | B | C | D | B | C | D | E |
| 仅在序列前 | A | B | C | D | B |  |  |  |
| 仅在序列后 |  |  |  | D | B | C | D | E |

我们还可以使用“点击深度”维度来描述这个概念。

**示例 3：点击深度 3 -&gt; 5**

![](assets/hit-depth.png)

## 维度约束 {#section_EAFD755F8E674F32BCE9B642F7F909DB}

在“THEN”语句之间的“within”子句中，您可以添加“在 1 个搜索关键字实例之内”、“在 1 个 eVar 47 实例之内”。此条件可将区段限制在维度的一个实例之内。

在规则之间设置“在维度之内”子句，能够使区段将数据限制为满足此子句的序列。请参见以下示例，其中约束条件被设置为“在 1 个页面之内”：

![](assets/sequence-filter4.png)

| 如果结果… | 序列 |
|--- |--- |
| 匹配 | A -&gt; B |
| 不匹配 | A then C then B (because B was not within 1 page of A)<br>**Note:**  If the dimension restriction is taken out, &quot;A then B&quot; and &quot;A then C then B&quot; would both match. |

## 简单页面查看序列

确定查看某个页面并随后查看另一个页面的访客。点击级别数据将过滤该序列，但不考虑之前、过去或中间的访问会话或它们之间的时间或页面查看次数。

**** 示例：访客查看了页面A，然后在同一或其他访问中查看了页面B。

**用例**

以下是如何使用该区段的示例：

1. 体育站点的访客查看足球登录页面，然后按顺序（但不必在同一次访问中）查看篮球登录页面。这提示促销活动在足球赛季期间向足球观众推送篮球内容。
1. 汽车经销商确定登录客户忠诚度页面，然后在该次访问或另一次访问期间的任何时候转到视频页面的访客之间的关系。

**创建此区段**

在顶级[!UICONTROL 访客]容器中嵌套两个页面规则，然后使用 [!UICONTROL THEN] 运算符序列化页面点击。

![](assets/segment_sequential_1.png)

## 跨访问的访客序列

确定退出促销活动但随后在另一个会话中返回页面查看序列的访客。

**** 示例：访客在一次访问中查看了页面A，然后在另一次访问中查看了页面B。

**用例**

以下是如何使用这种类型区段的示例：

* 访客先访问新闻站点的“体育”页面，然后在另一个会话中再次访问“体育”页面。
* 服装零售商可以查看访客先在一个会话内访问登录页面，然后在另一个会话中直接进入支付页面之间的关系。

**创建此区段**

此示例将两个 **[!UICONTROL 访问]** 容器嵌套至顶级 **[!UICONTROL 访客]容器，并使用[!UICONTROL THEN]运算符对区段进行排序。**

![](assets/visitor_seq_across_visits.png)

## 混合级序列

识别在次数不定的访问中查看两个页面，然后在单独的访问中查看第三个页面的访客。

**** 示例：访客访问页面A，然后在一次或多次访问中访问页面B，然后在单独访问中访问页面C。

**用例**

以下是如何使用这种类型区段的示例：

* 访客首先访问新闻站点，然后在同一次访问中查看体育页面。在另一次访问中，访客访问天气页面。
* 经销商确定进入主页，然后转到“我的帐户”页面，并在另一次访问中访问“查看购物车”页面的访客。

**创建此区段**

1. 从左侧窗格中拖动两个页面维度到顶级[!UICONTROL 访客]容器中。
1. 在两个维度之间添加 THEN 运算符。
1. Click **[!UICONTROL Options]** &gt; **[!UICONTROL Add container]** and add a [!UICONTROL Visit] container underneath the [!UICONTROL Visitor] level and sequenced using the [!UICONTROL THEN] operator.

![](assets/mixed_level_checkpoints.png)

## 聚合容器

通过在[!UICONTROL 访客]容器中添加多个[!UICONTROL 点击]容器，您可以在相同类型的容器之间使用相应的运算符，使用规则和维度（如页数和访问次数）定义页面查看以及在[!UICONTROL 点击]容器中提供序列维度。通过在点击级别应用逻辑，您可以在[!UICONTROL 访客]容器中的相同点击级别限制和合并匹配项，从而生成各种不同类型的区段。

**示例**：在页面查看序列中的第一次点击（示例中的页面 D）后，访客访问页面 A，然后访问页面 B 或页面 C，而与访问次数无关。

**用例**

以下是如何使用这种类型区段的示例：

* 确定在一次访问中转到主登录页面，然后在另一次访问中查看男士服装页面，接着在其他访问中查看女士或儿童服装登录页面的访客。
* e-zine 捕获在一次访问中转到主页，在另一次访问中查看体育页面，在其他访问中查看意见页面的访客。

**创建此区段**

1. 选择[!UICONTROL 访客]容器作为顶级容器。
1. 添加两个[!UICONTROL 点击]级别容器，这是一个使用 [!UICONTROL AND] 和 [!UICONTROL OR] 运算符在相同[!UICONTROL 点击]级别联接相应数值维度的维度。
1. 在[!UICONTROL 访问]容器中，再添加一个[!UICONTROL 点击]容器，并嵌套两个使用 [!UICONTROL OR] 或 [!UICONTROL AND] 运算符联接的其他[!UICONTROL 点击]容器。

   使用 [!UICONTROL THEN] 运算符排列这些嵌套的[!UICONTROL 点击]容器。

![](assets/aggregate_checkpoints2.png)

## 顺序区段中的“嵌套”

通过在[!UICONTROL 访问]和[!UICONTROL 点击]级别放置检查点，您可以限制区段以满足特定访问以及特定点击中的要求。

**** 示例：访客访问了页面A，然后在同一访问中访问了页面B。接下来，访客在新的访问中访问页面 C。

**创建此区段**

1. 在顶级[!UICONTROL 访问]容器下，拖入两个页面维度。
1. Multi-select both rules, click **[!UICONTROL Options]** &gt; **[!UICONTROL Add container from selection]** and change it to a [!UICONTROL Visit] container.
1. 使用 [!UICONTROL THEN] 运算符将二者联接起来。
1. 创建一个点击容器作为[!UICONTROL 访问]容器的对等容器并拖入一个页面维度。
1. 使用另一个 [!UICONTROL THEN] 运算符，将[!UICONTROL 访问]容器中的嵌套序列与[!UICONTROL 点击]容器联接在一起。

![](assets/nesting_sequential_seg.png)

## 排除点击

区段规则包括所有数据，除非您明确使用[!UICONTROL 排除]规则排除[!UICONTROL 访客]、[!UICONTROL 访问]或[!UICONTROL 点击]数据。这样，您就可以排除一般数据，创建更具目标性的区段。或者，您可以在创建区段时排除找到的组，以确定其余数据集，例如，创建一个规则以包括成功下订单的访客，然后将他们排除以确定非顾客。不过，在大多数情况下，最好创建规则以[!UICONTROL 排除]大多数的值，而不是尝试使用排除规则排除特定的包含值。

例如：

* **排除页面**。使用区段规则从报表中排除特定页面（如*`Home Page`*) 从报表中创建一个点击规则，在该规则中页面等于“主页”，然后将其排除。此规则自动包括 Home Page 以外的所有值。
* **排除反向链接域**。使用仅包括 Google.com 中的反向链接域并排除所有其他域的规则。
* **确定非顾客**。确定订单大于零的[!UICONTROL 访客]，然后将其排除。

可以使用 [!UICONTROL Exclude] 运算符确定访客没有执行特定访问或点击的序列。[!UICONTROL 排除检查点]也可以包含在 [逻辑组](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_23CE0E6071E14E51B494CD21A9799112).

## 在检查点之间排除

执行逻辑以细分符合以下条件的访客：某个检查点没有明确出现在两个其他检查点之间。

**** 示例：访问页面A然后访问页面C的访客，但未访问页面B。

**用例**

以下是如何使用这种类型区段的示例：

* 访客访问“日常生活”页面，然后访问“剧院”部分，但未访问“艺术”页面。
* 汽车零售商可以看到那些先访问主登录页面，然后不访问“汽车”页面而直接进入“免付利息”促销活动的访客之间的关系。

**创建此区段**

Create a segment as you would for a simple, mixed-level, or nested sequential segment and then set the [!UICONTROL EXCLUDE] operator for the container element. 下面的示例是一个聚合区段，其中将三个[!UICONTROL 点击]容器拖到画布中，分配 [!UICONTROL THEN] 运算符以联接容器逻辑，然后排除中间的页面查看容器以仅包含从序列中的页面 A 访问页面 C 的访客。

![](assets/exclude_between_checkpoints.png)

## 在序列开始时排除

如果排除检查点位于顺序区段开头，则它确保排除的页面查看不会位于第一个非排除的点击前面。

**** 示例：访客访问了页面A而非页面B。

**用例**

以下是如何使用此类区段的示例用例：

* 访客访问页面 A，没有访问页面 B。
* 餐馆想要查看避开主登录页面，直接转到 Order Out 页面的铁杆用户。

**创建此区段**

在顶级“访客”容器中创建两个单独的“点击”容器。然后，为第一个容器设置 [!UICONTROL EXCLUDE] 运算符。

![](assets/exclude_beginning_sequence.png)

## 在序列结尾处排除

如果排除检查点位于序列末尾，则它确保在上一非排除的检查点和访客序列结束之间不会出现检查点。

**** 示例：访客访问页面A，然后在当前或后续访问中访问页面B。

**用例**

以下是如何使用这种类型区段的示例：

* 访客访问页面 A，没有访问页面 B。
* 餐馆想要查看避开主登录页面，直接转到 Order Out 页面的铁杆用户。

**创建此区段**

Build a simple sequence segment by dragging two [!UICONTROL Hit] containers to the canvas and connecting them using the [!UICONTROL THEN] operator. 接下来，将 [!UICONTROL EXCLUDE] 运算符分配给序列中的第二个[!UICONTROL 点击]容器。

![](assets/exclude_end_sequence.png)

## 逻辑组容器

在顺序区段中，需要按照[容器层次结构](../../../components/c-segmentation/seg-overview.md#concept_A38E7000056547399E346559D85E2551)中的严格顺序排列容器。[!UICONTROL 逻辑组]容器设计用于以下场合：需要在顺序区段中使用较高级别容器以进一步过滤访客，以及提供复杂、嵌套和访客级别的约束以优化区段。

| 标准容器层次结构 |
|---|
| ![](assets/nesting_container.png) |
| 在[!UICONTROL 访客]容器中，按顺序嵌套[!UICONTROL 访问]和[!UICONTROL 点击]容器，以便根据点击数、访问次数和访客提取区段。 |

>[!NOTE]
>
>[!UICONTROL 逻辑组] 只能在顺序区段中定义，这意味着 [!UICONTROL 在表达式中使用THEN] 运算符。

[!UICONTROL 逻辑组]容器将一些检查点视为无序的组。例如，无法在[!UICONTROL 访客]容器中嵌套[!UICONTROL 访客]容器。相反，您可以将[!UICONTROL 逻辑组]容器嵌套在具有特定[!UICONTROL 访问]和[!UICONTROL 点击]级别检查点的[!UICONTROL 访客]容器中。

| 逻辑容器非标准层次结构 |
|---|
| ![](assets/logic_group_hierarchy.png) |
| 在[!UICONTROL 逻辑组]容器外部，也需要使用标准容器层次结构。但在[!UICONTROL 逻辑组]容器内，检查点不需要采用设置的顺序或层次结构；采用任意顺序的访客都可以满足这些检查点的要求。 |

## Build a Logic Group segment {#section_A5DDC96E72194668AA91BBD89E575D2E}

Like other containers, the [!UICONTROL Logic Group] containers can be built in multiple ways within the [!UICONTROL Segment Builder]. 下面是嵌套[!UICONTROL 逻辑组]容器的首选方法：

1. 从左侧窗格拖动维度、事件或区段。
1. 将顶部容器更改为[!UICONTROL 访客]容器。
1. 将默认插入的 [!UICONTROL AND] 或 [!UICONTROL OR] 运算符更改为 THEN 运算符。
1. Select the [!UICONTROL Hit] containers (the Dimension, Event, or Item) and click **[!UICONTROL Options]** &gt; **[!UICONTROL Add container from selection]**.
1. Click the container icon and select **[!UICONTROL Logic Group]**.  ![](assets/logic_group_checkpoints.png)
1. 现在，您可以在[!UICONTROL 逻辑组]容器中设置[!UICONTROL 点击]，而与层次结构无关。

## 按任意顺序进行逻辑组检查点

通过使用[!UICONTROL 逻辑组]，您可以满足该组中不在序列范围内的条件。This allows you to build segments where a [!UICONTROL Visit] or [!UICONTROL Hit] container happens irrespective of the normal hierarchy.****

**** 示例：访问页面A的访客，然后按任意顺序访问页面B和页面C。

**创建此区段**

将页面 B 和 C 嵌套到外部[!UICONTROL 访客]容器的[!UICONTROL 逻辑组]容器中。页面 A 的[!UICONTROL 点击]容器后跟[!UICONTROL 逻辑组]容器，并使用 [!UICONTROL AND] 运算符指定页面 B 和 C。由于它位于[!UICONTROL 逻辑组]中，因此，未定义该序列，点击页面 B 或 C 将满足该条件。

![](assets/logic_group_any_order2.png)

## 逻辑组第一次匹配

通过使用[!UICONTROL 逻辑组]，您可以满足该组中不在序列范围内的条件。在该无序的第一个匹配区段中，先将[!UICONTROL 逻辑组]规则指定为页面 B 或页面 C 的页面查看，然后指定为页面 A 的所需查看。

**** 示例：访问页面B或页面C，然后访问页面A的访客。

**创建此区段**

在[!UICONTROL 逻辑组]容器中放入页面 B 和页面 C 维度并选择 [!UICONTROL OR] 运算符，然后[!UICONTROL 点击]容器将页面 A 的页面查看识别为该值。

![](assets/logic_group_1st_match.png)

## 逻辑组排除AND

Build segments using the [!UICONTROL Logic Group] where multiple page views are aggregated to define what pages were necessary to be hit while other pages were specifically missed. ****

**** 示例：访客访问了页面A，然后明确未访问页面B或C，但点击了页面D。

**创建此区段**

从左窗格中拖动维度、事件和预生成的区段以生成该区段。See [Building a Logic Group Segment](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_23CE0E6071E14E51B494CD21A9799112).

在[!UICONTROL 逻辑组]中嵌套这些值后，单击 **[!UICONTROL 逻辑组]容器中的“排除”**[!UICONTROL ]按钮。

![](assets/logic_exclude_and.png)

## 逻辑组排除OR

使用[!UICONTROL 逻辑组]生成区段，其中聚合多个页面查看以定义需要点击的页面，同时明确跳过其他页面。

**** 示例：访问页面A的访客，但未访问页面A之前的页面B或页面C。

**创建此区段**

在排除的[!UICONTROL 逻辑组]容器中指定初始页面 B 和 C，然后访客点击页面 A。

从左窗格中拖动维度、事件和预生成的区段以生成该区段。

在[!UICONTROL 逻辑组]中嵌套这些值后，单击 **[!UICONTROL 逻辑组]容器中的“排除”**[!UICONTROL ]按钮。

![](assets/logic_exclude_or.png)

## 构建内间段和后间段

可以使用每个容器标题中内置的 [!UICONTROL Within] 和 [!UICONTROL After] 运算符定义时间、事件和计数。

![](assets/then_within_operators.png)

您可以使用 [!UICONTROL Within] 和 [!UICONTROL After] 容器并指定粒度和计数，以将匹配限制为指定的持续时间。[!UICONTROL Within] 运算符用于指定两个检查点之间的时间长度的最大限制。[!UICONTROL After] 运算符用于指定两个检查点之间的时间长度的最小限制。

## After 和 Within 运算符 {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

持续时间是由表示粒度的单个大写字母以及后面表示粒度重复次数的数字指定的。

**[!UICONTROL Within]** 包括终结点（小于或等于）。

**[!UICONTROL After]** 不包括终结点（大于）。

| 运算符 | 描述 |
|--- |--- |
| AFTER | After 运算符用于指定两个检查点之间的时间长度的最小限制。在设置 After 值后，时间限制将从应用区段时算起。例如，如果在容器上设置了After运算符以标识访问页面A但返回页面B在一天后不返回的访客，则该天将在访客离开页面A时开始。要使访客包含在区段中，至少在离开页面A后，至少需要1440分钟(一天)才能查看页面B。 |
| WITHIN | Within 运算符用于指定两个检查点之间的时间长度的最大限制。例如，如果在容器上设置了“内部”运算符以标识访问页面A的访客，然后返回到一天内的页面B，则该天将在访客离开页面A时开始。要包含在区段中，访客在打开页面B前将拥有一天的最长时间。要使访客包含在区段中，访问页面B必须在离开页面A到查看页面B后最多在1440分钟(一天)内完成。 |
| AFTER/WITHIN | 在使用 After 和 Within 运算符时，一定要了解这两个运算符是并行开始和结束的，而不是按顺序开始和结束的。For example, if you build a segment with the container set to:<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>Then the conditions to identify visitors in the segment are met only between 1 and 2 weeks. 这两个条件是从第一次页面点击时开始执行的。 |

## 使用After运算符

* 通过使用 Time After，您可以按年、月、日、小时和分钟跟踪以匹配访问。
* Time After 只能应用于[!UICONTROL 点击]容器，因为它是定义这种细粒度的唯一级别。

**** 示例：访问页面A的访客只有在周后才访问页面B。*******

![](assets/time_between_after_operator.png)

**创建区段**：此区段是通过向两个点击容器添加 [!UICONTROL 一] 个访客容器 [!UICONTROL ] 来创建的。然后，您可以设置 [!UICONTROL THEN] 运算符，打开 [!UICONTROL AFTER] 运算符下拉列表并设置星期数。

![](assets/after_operator.png)

**匹配**

在指定“After 2 weeks”时，如果在 2019 年 6 月 1 日 00:01 点击了页面 A，只要随后在 2019 年 6 月 15 日 00:01（14 天后）之前点击页面 B，该点击就匹配。

| 点击 A | 点击 B | 匹配 |
|--- |--- |--- |
| **A** 点击：2019 年 6 月 1 日，00:01 | **B** 点击：2019 年 6 月 15 日，00:01 | **匹配：** 此时间限制匹配，因为它在2019年月日之后(两周)。 |
| **A** 点击：2019 年 6 月 1 日，00:01 | **B** 点击：20：01B点击：2019年月15日00：01 | **不匹配：** 页面B上的第一次点击不匹配，因为它与需要两周后的约束冲突。 |

## 使用内部运算符

* 通过使用 [!UICONTROL Within]，您可以按年、月、日、小时和分钟跟踪以匹配访问。
* [!UICONTROL Within] 只能应用于[!UICONTROL 点击]容器，因为它是定义这种细粒度的唯一级别。

>[!IMPORTANT]
>
>在“THEN”语句之间的“within”子句中，您可以添加“在 1 个搜索关键字实例之内”、“在 1 个 eVar 47 实例之内”。此条件可将区段限制在维度的一个实例之内。

**** 示例：访问了页面A的访客在分钟内访问了页面B。

![](assets/time_between_within_operator.png)

**创建区段**：此区段是通过添加一个 [!UICONTROL 访问者] 容器，然后使用两 [!UICONTROL 个点击] 容器拖动来创建的。随后您可以设置 [!UICONTROL THEN] 运算符，并打开 [!UICONTROL AFTER] 运算符下拉列表，然后设置间隔：点击、页面查看、访问、分钟、小时、天、周、月、季度或年。

![](assets/within_operator.png)

**匹配**

匹配项必须位于时间限制内。对于   表达式，如果访客在 00:01 点击页面 A，只要随后在 00:06（5 分钟后，含 5 分钟）或之前点击页面 B，该点击就匹配。整 5 分钟的点击也匹配。

## 内部和之后操作符

可以使用 [!UICONTROL Within] 和 [!UICONTROL After] 在区段两端提供最大和最小端点。

**** 示例：访问页面A的访客在周后访问页面B，但在个月内访问页面B。

![](assets/time_between_using_both_operators.png)

**创建区段**：通过在一个访客容器中排列两 [!UICONTROL 个点击] 容器 [!UICONTROL 来创建] 区段。然后设置 [!UICONTROL After] 和 [!UICONTROL Within] 运算符。

![](assets/within_after_together.png)

**匹配**

在 2019 年 6 月 1 日点击页面 A 并在 2019 年 6 月 15 日 00:01 之后但在 2019 年 7 月 1 日*之前*返回的任何访客将包含在该区段中。与[排除项之间的时间](../../../components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md#concept_C5CB0A391B7C4AC8A95B9724A14E28E8)进行比较。

可以将 [!UICONTROL After] 和 [!UICONTROL Within] 运算符一起使用以定义顺序区段。

![](assets/time_between_within_after.png)

该示例说明在两周后但在一个月内第二次访问以点击页面 B 的情况。
