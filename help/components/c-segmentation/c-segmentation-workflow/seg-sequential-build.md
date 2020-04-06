---
description: 顺序区段是使用THEN运算符而不是AND或OR创建的。 THEN表示出现一个细分标准，然后是另一个。 默认情况下，顺序区段会识别所有匹配数据，并显示过滤器“包含每个人”。可以使用“仅在序列前”和“仅在序列后”选项将顺序区段进一步过滤为匹配点击的子集。
title: 生成顺序区段
topic: Segments
uuid: 7fb9f1c7-a738-416a-aaa2-d77e40fa7e61
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 生成顺序区段

顺序区段是使用THEN运算符而不是AND或OR创建的。 THEN表示出现一个细分标准，然后是另一个。 默认情况下，顺序区段会识别所有匹配数据，并显示过滤器“包含每个人”。可以使用“仅在序列前”和“仅在序列后”选项将顺序区段进一步过滤为匹配点击的子集。

![](assets/before-after-sequence.png)

此外，您还可以使用 [After 和 Within 运算符](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)，将顺序区段限制为检查点之间的特定时间段、粒度和计数。

## 包含每个人 {#section_75ADDD5D41F04800A09E592BB2940B35}

在创建一个设置了“包含每个人”的区段时，该区段能够识别匹配整个给定模式的路径。这是一个基本序列区段的示例，该区段查找同一访客所访问的一次点击（页面A）后跟另一次点击（页面B）。 该区段设置为“包括所有人”。

![](assets/sequence-filter.png)

| 如果结果为... | 序列 |
|--- |--- |
| 匹配 | A -> B<br>A ->（在不同的访问中）B<br>A -> D -> B |
| 不匹配 | B -> A |

## 仅序列前和序列后 {#section_736E255C8CFF43C2A2CAAA6D312ED574}

这些选 **[!UICONTROL Only Before Sequence]** 项并 **[!UICONTROL Only After Sequence]** 将区段过滤为指定序列之前或之后的数据子集。

* **仅在序列前**：包含序列之前的所有点击 + 该序列自身的第一次点击（见示例 1、3）。如果序列在路径中出现多次，则“仅在序列前”包括该序列最后一个实例的第一次点击和之前的所有点击（见示例 2）。
* **仅在序列后**：包含序列之后的所有点击 + 该序列自身的最后一次点击（见示例 1、3）。如果序列在路径中出现多次，则“仅在序列后”包括该序列首个实例的最后一次点击和之后的所有点击（见示例 2）。

例如，考虑B -> D。这三个过滤器将按以下方式识别点击：

**示例1:B然后D显示一次**

| 示例 | A | B | C | D | E | 五 |
|---|---|---|---|---|---|---|
| 包含每个人 | A | B | C | D | E | 五 |
| 仅在序列前 | A | B |  |  |  |  |
| 仅在序列后 |  |  |  | D | E | 五 |

**示例2:B然后D多次出现**

| 示例 | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| 包含每个人 | A | B | C | D | B | C | D | E |
| 仅在序列前 | A | B | C | D | B |  |  |  |
| 仅在序列后 |  |  |  | D | B | C | D | E |

我们还可以使用“点击深度”维度来描述这个概念。

**示例 3：点击深度 3 -> 5**

![](assets/hit-depth.png)

## 维度约束 {#section_EAFD755F8E674F32BCE9B642F7F909DB}

在 THEN 语句之间的“within”子句中，您可以添加“在 1 个搜索关键词实例之内”、“在 1 个 eVar 47 实例之内”。此条件可将区段限制在维度的一个实例之内。

在规则之间设置“在维度之内”子句，能够使区段将数据限制为满足此子句的序列。请参见以下示例，其中约束条件被设置为“在 1 个页面之内”：

![](assets/sequence-filter4.png)

| 如果结果为... | 序列 |
|--- |--- |
| 匹配 | A -> B |
| 不匹配 | A -> C -> B（因为 B 不在 A 的 1 个页面之内）<br>**注意：**如果取消维度限制，则“A -> B”和“A -> C -> B”都将匹配。 |

## 简单页面查看序列

识别查看某个页面然后查看其他页面的访客。 点击级别数据将过滤此序列，而不考虑以前、过去或过渡的访问会话，也不考虑之间发生的页面视图的时间或数量。

**示例**：访客查看了页面 A，然后在同一次访问或其他访问中查看了页面 B。

**用例**

以下是如何使用区段的示例。

1. 访客到体育网站视图足球登陆页，然后按顺序视图篮球登陆页，但不一定在同一次访问中。 这促使活动在足球赛季期间向足球观众推送篮球内容。
1. 汽车零售商确定了在客户忠诚度页面上登录，然后在访问或其他访问期间随时转到视频页面的用户之间的关系。

**创建此区段**

You nest two page rules within a top-level [!UICONTROL Visitor] container and sequence the page hits using the [!UICONTROL THEN] operator.

![](assets/segment_sequential_1.png)

## 跨访问的访客序列

确定退出促销活动但随后在另一个会话中返回页面查看序列的访客。

**示例**：访客在一次访问中查看了页面 A，然后在另一次访问中查看了页面 B。

**用例**

以下是如何使用此类型区段的示例：

* 访客进入新闻网站的“体育”页面，然后在另一个会话中重新访问“体育”页面。
* 服装零售商在一个会话中看到在登陆页上着陆的访客之间的关系，然后在另一个会话中直接转到结帐页面。

**创建此区段**

This example nests two **[!UICONTROL Visit]** containers within the top-level **[!UICONTROL Visitor]** container and sequences the segment using the [!UICONTROL THEN] operator.

![](assets/visitor_seq_across_visits.png)

## 混合级别序列

识别在次数不定的访问中查看两个页面，然后在单独的访问中查看第三个页面的访客。

**示例**：访客在一次或多次访问中访问页面 A，然后访问页面 B，随后在单独的访问中访问页面 C。

**用例**

以下是如何使用此类型区段的示例：

* 访客首先访问新闻网站，然后在同一次访问中视图体育页面。 另一次访问访客访问天气页面。
* 零售商定义进入主页，然后转到“我的帐户”页面的访客。 在另一次访问中，他们访问视图车页面。

**创建此区段**

1. 将左窗格中的两个页面维度拖放到顶级 [!UICONTROL Visitor] 容器中。
1. 在它们之间添加THEN运算符。
1. 单击 **[!UICONTROL Options]** > **[!UICONTROL Add container]** 并在级别下添加一个 [!UICONTROL Visit] 容器，并使用运 [!UICONTROL Visitor] 算符进行排序 [!UICONTROL THEN] 。

![](assets/mixed_level_checkpoints.png)

## 汇总容器

在容器中 [!UICONTROL Hit][!UICONTROL Visitor][!UICONTROL Hit] 添加多个容器允许您在同一类型的容器之间使用相应的运算符，并使用规则和维（如页面和访问编号）来定义页面视图并在容器中提供序列维。 通过在点击级别应用逻辑，您可以限制和合并容器中相同级别的点击匹配项，以构建 [!UICONTROL Visitor] 各种区段类型。

**示例**:访客在页面视图顺序中第一次点击后访问了页面A（示例中的页面D），然后访问了页面B或页面C，而不考虑访问次数。

**用例**

以下是如何使用此类型区段的示例：

* 确定一次访问中前往主登陆页的访客，然后在另一次访问中视图“男士”服装页面，然后在另一次访问中视图“妇女”或“儿童”登陆页。
* 电子杂志捕获一次访问中前往主页的访客、另一次访问中的“体育”页面和另一次访问中的“观点”页面。

**创建此区段**

1. 选择 [!UICONTROL Visitor] 容器作为顶级容器。
1. 添加两 [!UICONTROL Hit]个级容器-一个尺寸，该尺寸具有由和运算符在同一级连接 [!UICONTROL Hit] 的相应数值 [!UICONTROL AND] 尺寸 [!UICONTROL OR] 。
1. 在容器 [!UICONTROL Visit] 中，添加另一个容器，并嵌套两个与或运 [!UICONTROL Hit] 算符连接的其 [!UICONTROL Hit] 他容器 [!UICONTROL OR][!UICONTROL AND] 。

   用运算符对这 [!UICONTROL Hit] 些嵌套容器进 [!UICONTROL THEN] 行排序。

![](assets/aggregate_checkpoints2.png)

## 在顺序区段中“嵌套”

By placing checkpoints at both the [!UICONTROL Visit] and [!UICONTROL Hit] level, you can constrain the segment to meet requirements within a specific visit as well as a specific hit.

**示例**：访客访问了页面 A，然后在同一访问中访问了页面 B。接下来，访客在新的访问中访问页面 C。

**创建此区段**

1. Underneath a top-level [!UICONTROL Visit] container, drag in two page dimensions.
1. 多选两个规则，单击 **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]** 并将其更改为一个 [!UICONTROL Visit] 容器。
1. 使用操作员将其 [!UICONTROL THEN] 连接。
1. 创建点击容器作为对等容器, [!UICONTROL Visit] 并在页面维度中拖动。
1. 使用其他运算符将容器中 [!UICONTROL Visit] 的嵌套序列与 [!UICONTROL Hit] 容器连接 [!UICONTROL THEN] 起来。

![](assets/nesting_sequential_seg.png)

## 排除点击

细分规则包括所有数据，除非您特别 [!UICONTROL Visitor]使用 [!UICONTROL Visit]该规 [!UICONTROL Hit] 则排除、或 [!UICONTROL Exclude] 数据。 它允许您取消常见数据，并创建更具针对性的细分。 或者，您也可以创建区段（不包括已找到的组）以标识其余的数据集，例如创建一个规则，该规则包括下单的成功访客，然后排除他们以标识“非购买者”。 但是，在大多数情况下，最好创建排除广泛值的规则，而不是尝试使用该规则来 [!UICONTROL Exclude] 目标特定的包含值。

例如：

* **排除页面**。 使用区段规则从报表中删除特定页面(如 *`Home Page`*)，创建页面等于“主页”的点击规则，然后将其排除。 此规则自动包括除主页之外的所有值。
* **排除引用域**。 使用仅包括Google.com中引用域且排除所有其他域的规则。
* **识别非购买者**。 确定订单大于零的时间，然后排除 [!UICONTROL Visitor]。

运 [!UICONTROL Exclude] 算符可用于标识访客不执行特定访问或点击的序列。 [!UICONTROL Exclude Checkpoints] 也可以包含在逻辑 [组中](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)。

### 检查点之间排除

执行逻辑以细分符合以下条件的访客：某个检查点没有明确出现在两个其他检查点之间。

**示例**：访客访问了页面 A，然后访问页面 C，但未访问页面 B。

**用例**

以下是如何使用此类型区段的示例：

* 访客到“生活方式”页面，然后转到“剧院”部分，而不转到“艺术”页面。
* 汽车零售商会看到访问主登陆页，然后直接转到“无兴趣”活动而不转到“车辆”页面的用户之间的关系。

**创建此区段**

像创建简单的混合级别顺序区段或嵌套顺序区段一样创建一个区段，然后为容器元素设置 [!UICONTROL EXCLUDE] 运算符。The example below is an aggregate segment where the three [!UICONTROL Hit] containers are dragged to the canvas, the [!UICONTROL THEN] operator assigned to join the container logic, then exclude the middle page view container to include only visitors that went from page A to Page C in the sequence.

![](assets/exclude_between_checkpoints.png)

### 序列开头排除

如果排除检查点位于顺序区段开头，则它确保排除的页面查看不会位于第一个非排除的点击前面。

**示例**：访客访问了页面 A，但没有访问页面 B。

**用例**

以下是如何使用这种类型区段的用例示例：

* 访问页面A且未访问页面B的访客。
* 餐馆希望看到那些避开主登陆页并直接转到“下单”页面的投资者。

**创建此区段**

在顶级容器容器中创建两个单独的点击访客。 然后为第 [!UICONTROL EXCLUDE] 一个容器设置运算符。

![](assets/exclude_beginning_sequence.png)

### 序列末尾排除

如果排除检查点位于序列末尾，则它确保在上一非排除的检查点和访客序列结束之间不会出现检查点。

**示例**：访客访问了页面 A，然后在当前或随后的访问中没有访问页面 B。

**用例**

以下是如何使用此类型区段的示例：

* 访问页面A且未访问页面B的访客。
* 餐馆希望看到那些避开主登陆页并直接转到“下单”页面的投资者。

**创建此区段**

Build a simple sequence segment by dragging two [!UICONTROL Hit] containers to the canvas and connecting them using the [!UICONTROL THEN] operator. Then assign the [!UICONTROL EXCLUDE] operator to the second [!UICONTROL Hit] container in the sequence.

![](assets/exclude_end_sequence.png)

## 逻辑组容器

将条件分组到一个顺序区段检查点时，需要使用逻辑组容器。特殊逻辑组容器仅在顺序区段中可用，以确保其条件在任何先前顺序检查点之后和任何后续顺序检查点之前都得到满足。可以按任意顺序满足逻辑组检查点自身内的条件。相反，非顺序容器（点击、访问、访客）不要求在整个序列中满足其条件，因此，如果与 THEN 运算符一起使用，则会产生不直观的结果。The [!UICONTROL Logic Group] container was designed to treat *several checkpoints as a group*, *without any ordering* among the grouped checkpoints. 换句话说，我们不关心该组内检查点的顺序。For example, you can&#39;t nest a [!UICONTROL Visitor] container within a [!UICONTROL Visitor] container. But instead, you can nest a [!UICONTROL Logic Group] container within a [!UICONTROL Visitor] container with specific [!UICONTROL Visit]-level and [!UICONTROL Hit]-level checkpoints.

>[!NOTE] 只能 [!UICONTROL Logic Group] 在顺序段中定义运算符，这表示该运 [!UICONTROL THEN] 算符在表达式中使用。

| 容器层次结构 | 插图 | 定义 |
|---|---|---|
| 标准容器层次结构 | ![](assets/nesting_container.png) | 在容器 [!UICONTROL Visitor] 中，和 [!UICONTROL Visit][!UICONTROL Hit] 容器按顺序嵌套，以根据点击量、访问次数和访客提取区段。 |
| 逻辑容器层次结构 | ![](assets/logic_group_hierarchy.png) | 标准容器层次结构在容器之外也是必需的。 [!UICONTROL Logic Group] 但在容器内 [!UICONTROL Logic Group] 部，检查点不需要固定的顺序或层次结构，这些检查点只需访客按任意顺序满足。 |

逻辑组可能看起来令人望而却步，以下是一些关于如何使用逻辑组的最佳实践：

**逻辑组容器，还是点击/访问容器？**
如果要对顺序检查点进行分组，则“容器”为逻辑组容器。但是，如果这些顺序检查点必须出现在单个点击或访问范围内，则需要使用“点击”或“访问”容器。（当然，当一次点击可能只计入一个检查点时，“点击”对于一组顺序检查点没有意义）。

**逻辑组是否可以简化顺序区段的生成过程？**
是的，可以。假设您正在尝试回答以下问题：**访客是否在访问页面 A 后访问了页面 B、页面 C 或页面 D？**

您可以不使用逻辑组容器生成此区段，但是这样既费时又费力：
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

逻辑组容器可以大大简化生成此区段的过程，如下所示：

![](assets/logic-grp-example.png)


### 生成逻辑组区段 {#section_A5DDC96E72194668AA91BBD89E575D2E}

与其他容器一样， [!UICONTROL Logic Group] 容器可以在中以多种方式构建 [!UICONTROL Segment Builder]。 以下是嵌套容器的首选方法： [!UICONTROL Logic Group]

1. 从左窗格中拖动维、事件或区段。
1. 将顶部容器更改为 [!UICONTROL Visitor] 容器。
1. 将默认 [!UICONTROL AND] 插入 [!UICONTROL OR] 的或运算符更改为THEN运算符。
1. 选择 [!UICONTROL Hit] 容器(维、事件或项目)，然后单击 **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**。
1. Click the container icon and select **[!UICONTROL Logic Group]**.  ![](assets/logic_group_checkpoints.png)
1. You can now set the [!UICONTROL Hit] within the [!UICONTROL Logic Group] container without regard to hierarchy.

### 采用任意顺序的逻辑组检查点

Using the [!UICONTROL Logic Group] lets you meet conditions within that group that reside outside of the sequence. This allows you to build segments where a [!UICONTROL Visit] or [!UICONTROL Hit] container happens irrespective of the normal hierarchy.

**示例**：访客访问了页面 A，然后按任意顺序访问了页面 B 和页面 C。

**创建此区段**

Page B and C are nested in a [!UICONTROL Logic Group] container within the outer [!UICONTROL Visitor] container. The [!UICONTROL Hit] container for A is then followed by the [!UICONTROL Logic Group] container with B and C identified using the [!UICONTROL AND] operator. Because it is in the [!UICONTROL Logic Group], the sequence is not defined and hitting both page B and C in any order makes the argument true.

![](assets/logic_group_any_order2.png)

**另一个示例**：访客访问了页面 B 或页面 C，然后访问了页面 A：

![](assets/logic_group_any_order3.png)

区段必须匹配逻辑组的至少一个检查点（B 或 C）。此外，可在同一点击中或在多次点击中满足逻辑组条件。

### 逻辑组第一个匹配

Using the [!UICONTROL Logic Group] lets you meet conditions within that group that reside outside of the sequence. 在此无序的第一个匹配区段中，规 [!UICONTROL Logic Group] 则首先被标识为页面B的页面视图或页面C，然后是页面A的所需视图。

**示例**：访客访问了页面 B 或页面 C，然后访问了页面 A。

**创建此区段**

Page B and page C dimensions are grouped within a [!UICONTROL Logic Group] container with the [!UICONTROL OR] operator selected, then the [!UICONTROL Hit]container identifying a page view of page A as the value.

![](assets/logic_group_1st_match.png)

### 逻辑组排除 AND

Build segments using the [!UICONTROL Logic Group] where multiple page views are aggregated to define what pages were necessary to be hit while other pages were specifically missed. ****

**示例**：访客访问了页面 A，然后明确不访问页面 B 或 C，但点击页面 D。

**创建此区段**

从左窗格中拖动维度、事件和预生成的区段以生成该区段。请参阅[生成逻辑组区段](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)。

在中嵌入值后， [!UICONTROL Logic Group]单击容器 **[!UICONTROL Exclude]** 中的按钮 [!UICONTROL Logic Group] 。

![](assets/logic_exclude_and.png)

### 逻辑组排除 OR

Build segments using the [!UICONTROL Logic Group] where multiple page views are aggregated to define what pages were necessary to be hit while other pages were specifically missed.

**示例**：访客访问了页面 A，但在页面 A 之前没有访问页面 B 或页面 C。

**创建此区段**

The initial B and C pages are identified in a [!UICONTROL Logic Group] container that is excluded, and then followed by a hit to page A by the visitor.

从左窗格中拖动维度、事件和预生成的区段以生成该区段。

在中嵌入值后， [!UICONTROL Logic Group]单击容器 **[!UICONTROL Exclude]** 中的按钮 [!UICONTROL Logic Group] 。

![](assets/logic_exclude_or.png)

## 生成 Time-Within 和 Time-After 区段

使用 [!UICONTROL Within] 每个容器 [!UICONTROL After] 标题中内置的和运算符来定义时间、事件和计数。

![](assets/then_within_operators.png)

您可以通过使用和容器并指定粒度和计数，将匹配限 [!UICONTROL Within] 制为 [!UICONTROL After] 指定的时长。 The [!UICONTROL Within] operator is used to specify a max limit on the amount of time between two checkpoints. The [!UICONTROL After] operator is used to specify a minimum limit on the amount of time between two checkpoints.

### After and Within Operators {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

持续时间是由表示粒度的单个大写字母以及后面表示粒度重复次数的数字指定的。

**[!UICONTROL Within]** 包括终结点（小于或等于）。

**[!UICONTROL After]** 不包括终结点（大于）。

| 运营商 | 描述 |
|--- |--- |
| AFTER | After 运算符用于指定两个检查点之间的时间长度的最小限制。在设置 After 值后，时间限制将从应用区段时算起。例如，如果在容器上设置 After 运算符以识别访问页面 A，但直到一天后才返回访问页面 B 的访客，那么该时间将从访客离开页面 A 时开始。对于要包含在此区段中的访客，从离开页面 A 后至查看页面 B，必须至少经过 1440 分钟（一天）。 |
| WITHIN | Within 运算符用于指定两个检查点之间的时间长度的最大限制。例如，如果在容器上设置 Within 运算符以识别访问页面 A，然后在一天内返回访问页面 B 的访客，那么该时间将从访客离开页面 A 时开始。要包含在此区段中，访客需要在一天之内打开页面 B。对于要包含在此区段中的访客，在离开页面 A 后至查看页面 B，所经过的时间不能超过 1440 分钟（一天）。 |
| AFTER/WITHIN | 在使用 After 和 Within 运算符时，一定要了解这两个运算符是并行开始和结束的，而不是按顺序开始和结束的。例如，如果生成一个区段并将容器设置为：<br>`After = 1 Week(s) and Within = 2 Week(s)`<br>则确定区段中的访客的条件仅在 1 周后但在 2 周内满足要求。这两个条件是从第一次页面点击时开始执行的。 |

### 使用 After 运算符

* Time After允许您按年、月、日、小时和分钟跟踪以匹配访问。
* Time After只能应用于容器，因 [!UICONTROL Hit] 为它是定义此类精细粒度的唯一级别。

**示例**：访客访问了页面 A，然后仅在 2 周后访问了页面 B。****

![](assets/time_between_after_operator.png)

**创建区段**:此区段是通过添加具有两个 [!UICONTROL Visitor] 容器的容器来创建 [!UICONTROL Hit] 的。 然后，您可以设置 [!UICONTROL THEN] 运算符，打开 [!UICONTROL AFTER] 运算符下拉列表并设置星期数。

![](assets/after_operator.png)

**匹配**

在指定“After 2 weeks”时，如果在 2019 年 6 月 1 日 00:01 点击了页面 A，只要随后在 2019 年 6 月 15 日 00:01（14 天后）之前点击页面 B，该点击就匹配。

| 点击A | Hit B | 匹配 |
|--- |--- |--- |
| **A** 点击：2019 年 6 月 1 日，00:01 | **B** 点击：2019 年 6 月 15 日，00:01 | **匹配**：该时间约束了匹配情况，因为该时间是在 2019 年 6 月 1 日之后（两周）。 |
| **A** 点击：2019 年 6 月 1 日，00:01 | **B** 点击：2019 年 6 月 8 日，00:01 B 点击：2019 年 6 月 15 日，00:01 | **不匹配**：页面 B 的第一次点击不匹配，因为它与约束条件（要求在两周后点击）冲突。 |

### 使用 Within 运算符

* [!UICONTROL Within] 允许您按年、月、日、小时和分钟跟踪以匹配访问。
* [!UICONTROL Within] 只能应用于容器, [!UICONTROL Hit] 因为它是定义这种精细粒度的唯一级别。

>[!IMPORTANT]
>
>在 THEN 语句之间的“within”子句中，您可以添加“在 1 个搜索关键词实例之内”、“在 1 个 eVar 47 实例之内”。此条件可将区段限制在维度的一个实例之内。

**示例**：访客访问了页面 A，然后在 5 分钟内访问了页面 B。

![](assets/time_between_within_operator.png)

**创建区段**:此区段是通过添加容器，然 [!UICONTROL Visitor] 后用两个容器拖动来创建 [!UICONTROL Hit] 的。 随后您可以设置 [!UICONTROL THEN] 运算符，并打开 [!UICONTROL AFTER] 运算符下拉列表，然后设置间隔：点击、页面查看、访问、分钟、小时、天、周、月、季度或年。

![](assets/within_operator.png)

**匹配**

匹配项必须位于时间限制内。对于   表达式，如果访客在 00:01 点击页面 A，只要随后在 00:06（5 分钟后，含 5 分钟）或之前点击页面 B，该点击就匹配。整 5 分钟的点击也匹配。

### Within 和 After 运算符

可以使用 [!UICONTROL Within] 和 [!UICONTROL After] 在区段两端提供最大和最小端点。

**示例**：访客访问了页面 A，然后在两周后但在一个月内访问了页面 B。

![](assets/time_between_using_both_operators.png)

**创建区段**:通过在一个容器中排列两个 [!UICONTROL Hit] 容器来创建 [!UICONTROL Visitor] 区段。 Then set the [!UICONTROL After] and [!UICONTROL Within] operators.

![](assets/within_after_together.png)

**匹配**

在 2019 年 6 月 1 日点击页面 A 并在 2019 年 6 月 15 日 00:01 之后但在 2019 年 7 月 1 日&#x200B;*之前*&#x200B;返回的任何访客将包含在该区段中。与排除 [时间进行比较](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)。

运 [!UICONTROL After] 算符 [!UICONTROL Within] 和运算符可一起用于定义顺序段。

![](assets/time_between_within_after.png)

此示例描述了两周后但一个月内对页面B的第二次访问。
