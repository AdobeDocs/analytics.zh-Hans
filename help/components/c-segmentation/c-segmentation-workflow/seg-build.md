---
description: 区段生成器提供了一个画布，用于根据容器层次结构逻辑、规则和运算符将度量维度、区段和事件拖放到区段访客中。 通过使用该集成开发工具，您可以生成和保存简单或复杂的区段，以确定跨访问和页面点击的访客属性和操作。
title: 生成区段
topic: Segments
uuid: c01393df-ccdd-431c-83a6-3c2700bd4999
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 区段生成器

The [!UICONTROL Segment Builder] provides a canvas to drag and drop Metrics, Dimensions, Segments, and Events to segment visitors based on container hierarchy logic, rules, and operators. 通过使用该集成开发工具，您可以生成和保存简单或复杂的区段，以确定跨访问和页面点击的访客属性和操作。

>[!IMPORTANT]
>
>我们在 2019 年 6 月版中引入了维度归因模型。请参阅以下“Web UI 功能”下的第 6 项。

访问区段生成器的方法有以下几种：

* **分析顶部导航**:单击 **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Segments]**。
* **[!UICONTROL Analysis Workspace]**:单击 **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**，打开一个项目，然后单击 **[!UICONTROL + New]** > **[!UICONTROL Create Segment]**。
* **[!UICONTROL Reports & Analytics]**:单击 **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**，打开现有报表，单击左侧导航中 ![](assets/segment_icon.png) 的区段图标，然后单击 **[!UICONTROL Add]**。
* **[!UICONTROL Ad Hoc Analysis]**:在 [临时分析中构建区段](/help/components/c-segmentation/c-segmentation-workflow/seg-build.md#build-segments)。
* **[!UICONTROL Report Builder]**:在 [Report Builder中添加或编辑区段](https://marketing.adobe.com/resources/help/zh_CN/arb/segmentation.html)。

## 区段生成器用户界面 {#concept_643F2DF74C544796B58F4656ABC5F726}

利用 [!UICONTROL Segment Builder] 该功能，您可以构建简单或复杂的细分，以确定跨访问和页面点击的访客属性和操作。 它提供了一个画布，用于拖放度量维度、事件或其他区段，以便根据层次结构逻辑、规则和运算符对访客进行细分。

## Web UI功能 {#section_F61C4268A5974C788629399ADE1E6E7C}

使用 [!UICONTROL Segment Builder] 可在Web UI(或在临时分析的 [Java UI中)中构建和编辑区段](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)。 您可以添加规则定义和容器来细化区段，堆叠区段，并嵌套它们以细化它们。 您还可以验证当前区段定义产生的页面视图、访问和唯一访客数。 然后保存区段以满足未来需求。

通过以下方式访问区段生成器：

* 显示一个现有报表，然后单击左侧导航中的“区段”图标 ![](assets/segment_icon.png)。In the segment rail that displays, click **[!UICONTROL Add]**.

* From within the Segment Manager, clicking **[!UICONTROL + Add]**.
* 在区段管理器中单击现有区段的标题以在区段生成器中编辑该区段。

![](assets/segment_builder_ui.png)

1. **[!UICONTROL Title]**:允许您命名或重命名区段。
1. **[!UICONTROL Description]**:提供区段的描述。 如果要共享区段，则必须提供描述。
1. **[!UICONTROL Tags]**:标 [记要创建的区段](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) ，方法是从现有标记的列表中选取或创建新标记。
1. **[!UICONTROL Definitions]**:您可以在此处构 [建和配置区段](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)、添加规则以及嵌套和序列容器。 允许您通过选择容器，并将维度、区段或量度拖放到定义中来为新区段提供描述。
1. **[!UICONTROL Show]**:(顶部容器选择器。)允许您选择顶级 [容器](/help/components/c-segmentation/seg-overview.md) ( [!UICONTROL Visitor]、 [!UICONTROL Visit]、 [!UICONTROL Hit])。 默认的顶级容器为“点击”容器。
1. **[!UICONTROL Options]**:（齿轮）图标

   * **[!UICONTROL + Add container]**:允许您将新容器(在顶级容器下)添加到区段定义。
   * **[!UICONTROL + Add container from selection]**:允许您根据在“定义”字段中选择（多个）的元素创建新容器。
   * **[!UICONTROL Exclude]**:允许您通过排除一个或多个维度、区段或指标来定义区段。

1. **[!UICONTROL Attribution Models]**:用于维度细分。 维度模型在连续分段中尤其有用，例如，在那些支持流量可视化图表的连续分段中。

   * **[!UICONTROL Repeating]** (（默认）):包括维的实例和保留的值。
   * **[!UICONTROL Instance]**: 包括维度的实例.
   * **[!UICONTROL Non-repeating instance]**: 包括维度的独特实例（非重复实例）.
   ![](assets/attribution-models.jpg)

1. **[!UICONTROL Dimensions]**:从维列表（橙色提要栏）中拖放维。
1. **[!UICONTROL Comparison]**:可以使用选定的运算符比较和约束值。
1. **[!UICONTROL Value]**:您为维度、区段或量度输入或选择的值。
1. **[!UICONTROL And/Or/Then]**:在容器 [!UICONTROL AND/OR/THEN] 或规则之间分配运算符。 通过使用 THEN 运算符，您可以[定义顺序区段](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md)。
1. **[!UICONTROL Metric]**:（绿色提要栏）从“度量”列表拖放的度量。
1. **[!UICONTROL Comparison]** 运算符：可以使用选定的运算符比较和约束值。
1. **[!UICONTROL Value]**:您为维度、区段或量度输入或选择的值。
1. **[!UICONTROL X]**：（删除）用于删除此部分区段定义。
1. **[!UICONTROL Save]** 或 **[!UICONTROL Cancel]**:保存或取消区段。 After clicking **[!UICONTROL Save]**, you are taken to the Segment Manager where you can manage the segment.
1. **[!UICONTROL Search]**:搜索维度、区段或指标的列表。
1. **[!UICONTROL Dimensions]**:(列表)单击标题可展开。
1. **[!UICONTROL Metrics]**:单击标题可展开。
1. **[!UICONTROL Segments]**:单击标题可展开。
1. **[!UICONTROL Report suite selector]**:允许您选择保存此区段的报表包。 您仍可以在所有报表包中使用该区段。
1. **[!UICONTROL Segment Preview]**:允许您预览关键指标，以查看您是否有有效的细分以及该细分的范围。 表示您是否应用此区段可望查看的数据集细分。 显示3个同心圆和一个列表，以显示针对数据集运行的区段的 [!UICONTROL Hits]、 [!UICONTROL Visits][!UICONTROL Visitors] 和匹配的数量和百分比。 在您创建或更改区段定义后，此图表会立即更新。
1. **[!UICONTROL Product Compatibility]**:提供与您创建的区段兼容的Adobe Analytics产品列表(分析工作区、临时分析、数据仓库)。 [!UICONTROL Reports & Analytics]大多数细分与所有产品兼容。 但是，并非所有运算符和维度都与所有Analytics产品（尤其是数据仓库） [兼容](/help/components/c-segmentation/seg-reference/seg-compatibility.md)。 在对区段定义做出更改之后，将立即更新此图表。

嵌入了日期范围的区段会继续以不同的方式在 Analysis Workspace 与 [!UICONTROL Reports & Analytics] 中运行：在“工作区”中，嵌入了日期范围的区段会覆盖面板日期范围。相反，[!UICONTROL Reports & Analytics] 会显示报表日期范围和区段嵌入日期范围的交集。

**[!UICONTROL Publish to Experience Cloud (for `<report suite name>`)]**:（未在屏幕上显示）仅当为Experience Cloud启用了您保存此区段的报表包时， [才显示此选项](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md)。 By publishing a segment to the Experience Cloud, you can use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], and [!DNL Audience Manager]. 区段标题和描述为必填字段。

>[!NOTE]在 Analytics 中，您可以编辑或删除已经发布的区段。如果区段正在使用，会在您编辑区段时给出一条警告消息。您无法删除一个已发布但 Adobe [!DNL Target] 正在使用的区段。

![](assets/segment_publish_to_mac_copy.png)

>[!IMPORTANT]
>
>您必须将从 Analytics 共享的受众数量限制为 20，以避免额外的处理延迟。从Analytics共享到Experience Cloud的受众不能超过2000万个唯一成员。 此外，由于缓存，在Analytics中删除的报表包需要12小时才能在Experience Cloud中显示删除。

>[!IMPORTANT]
>
>在访客有资格成为从 Analytics 共享的受众后，该信息需经过 24 - 48 小时的延迟，才能在 [!DNL Target]、[!DNL Advertising Cloud] 和 [!DNL Campaign] 中使用。

## 生成区段 {#build-segments}

1. 只需将维度、区段或度量事件从左侧窗格拖动到字段 [!UICONTROL Definitions] 中。

   ![](assets/drag_n_drop_dimension.png)

   将元素拖动到 [!UICONTROL Hit] 后，将显示默认的顶级容器 [!UICONTROL Definitions]。 You can change the container type to Visit or Visitor from the **[!UICONTROL Show]** drop-down menu.

1. 从下拉菜单中，设置[运算符](/help/components/c-segmentation/seg-reference/seg-operators.md)。
1. 输入或选择所选项目的值。
1. Add additional containers if needed, using **[!UICONTROL And]**, **[!UICONTROL Or]**, or **[!UICONTROL Then]** rules.
1. 放置容器并设置规则后，请在右上角的验证图表中查看区段的结果。 验证程序指示与您创建的区段匹配的页面视图、访问和唯一访客的百分比和绝对数。
1. Under **[!UICONTROL Tags]**, [tag](/help/components/c-segmentation/c-segmentation-workflow/seg-tag.md) the container by selecting an existing tag or creating a new one.
1. Click **[!UICONTROL Save]** to save the segment.

此时您将转到[区段管理器](/help/components/c-segmentation/c-segmentation-workflow/seg-manage.md)，在此处，可以通过多种方式标记、共享和管理区段。

## 生成和嵌套容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[生成容器框架](/help/components/c-segmentation/seg-overview.md)，然后在其中放置逻辑规则和运算符。

1. 单击 **[!UICONTROL Options > Add Container]**.

   ![](assets/add_container.png)

   将打开一 [!UICONTROL Hit] 个新容器，但 [!UICONTROL Hit] 未标识(页面视图)。

   ![](assets/new_container.png)

1. 根据需要更改容器类型。
1. 将维度、区段或事件从左侧窗格拖动到容器。
1. Continue to add new containers from the top-level **[!UICONTROL Options]** > **[!UICONTROL Add container]** button at the top of the definition, or add containers from within a container to nest logic.

   **或者**

   选择一个或多个规则，然后单击 **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**。 这会将您的选择转换为单独的容器。

## 在区段中使用日期范围 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以生成包含滚动日期范围的区段，以获取有关持续促销活动或事件问题的解答。

例如，您可以轻松生成一个区段，包含“过去 60 天中购买过产品的用户”。

您可以创建访问容器，并在其中添加时 [!UICONTROL Last 60 days] 间范围和度量， [!UICONTROL Orders is greater than or equal to 1]并使用AND运算符：

![](assets/date-ranges.png)

## 堆叠区段 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

堆叠区段的工作方式是使用“和”运算符组合每个区段中的条件，然后应用组合的条件。

例如，堆叠“移动电话用户”区段和“美国地区”区段将只返回美国的移动电话用户的数据。

将这些区段视为可包含在区段库中的构件块或模块，供用户视需要使用。 这样，您就可以显着减少所需的细分数量。 例如，假定您有40个区段：

* 20适用于不同国家／地区（US_mobile、Germany_mobile、France_mobile、Brazil_mobile等）的手机用户
* 20适用于不同国家／地区的平板电脑用户（US_tablet、Germany_tablet、France_tablet、Brazil_tablet等）

通过使用区段堆叠，您可以将区段数量减少到 22 个，然后根据需要进行堆叠。您需要创建以下区段：

* 移动用户的一个区段
* 一个针对平板电脑用户的细分
* 20个不同地区的细分

>[!NOTE] 堆叠两个区段时，默认使用 AND 语句联接。不能将其更改为OR语句。

1. 转到“区段生成器”。
1. 提供区段的标题和说明。

   步骤结果 1. Click **[!UICONTROL Show Segments]** to bring up the list of segments in the left navigation.

   步骤结果 1. 将要堆叠的区段拖放到区段定义画布上。下面是堆叠现有的“来自平板电脑的访问”和“美国地区”区段的区段示例：

   ![](assets/seg_stack2.png)

1. 保存区段。

   步骤结果

## 使用区段模板 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

模板表示预先配置的旧包区段。

In the Segment Manager, click **[!UICONTROL Add]**, which takes you to the Segment Builder. 现在，单击“区段”图标 ![](assets/segment_icon.png)

以调出区段边栏。区段模板显示在区段列表的底部。 模板名称左侧的文件夹图标可以区分它们：

![](assets/seg_template.png)

您可以将这些模板拖动到“定义”画布中，并在定义它们时使用它们，或者修改它们。

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 模板名称 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 放弃购物车 </td> 
   <td colname="col2">视图数据，用于向购物车中添加物品但未订购任何物品的访客。 在区段定义中，容器为访问。 此顺序区段的规则是 <p> 购物车加货不为空 </p> <p>然后 </p> <p>订单等于0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 第一次访问 </td> 
   <td colname="col2">视图最多访问一[1]次的访客的数据。 在区段定义中，容器为访问。 规则是 <p>访问次数等于1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非购买者 </td> 
   <td colname="col2">视图未参与订单事件的访客的数据。 在细分定义中，容器是访客。 此区段使用排除逻辑。 规则是 <p>订单不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非单页访问（非弹回） </td> 
   <td colname="col2">视图多次访问的访客的数据。 在细分定义中，容器是访客。 此区段使用排除逻辑。 规则是 <p>单次访问不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 付费搜索 </td> 
   <td colname="col2">视图来自付费搜索的访客的数据。 在区段定义中，容器为访问。 规则是 <p>付费搜索等于1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 购买者 </td> 
   <td colname="col2">视图已参与订单事件的访客的数据。 在细分定义中，容器是访客。 规则是 <p>订单不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 回访 </td> 
   <td colname="col2">视图来自至少访问过一次的访客的数据。 在区段定义中，容器为访问。 规则是 <p>访问次数大于1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 单页面访问量 </td> 
   <td colname="col2"> 视图来自其中显示单个页面值的访问的数据，即使您在该访问期间可提交多个页面视图。 具有退出链接事件的单页访问包含在区段中。 在区段定义中，容器为访问。 规则是 <p>单页访问量等于1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查看的产品未添加到购物车 </td> 
   <td colname="col2">视图数据，用于查看产品但没有购物车加货的访客。 在区段定义中，容器为访问。 此顺序区段的规则是 <p>产品视图不为空 </p> <p>然后 </p> <p> 购物车加货等于0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自活动的访问 </td> 
   <td colname="col2">视图活动所指访客的数据。 在区段定义中，容器为访问。 规则是 <p>跟踪代码不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自移动设备的访问量 </td> 
   <td colname="col2">视图来自使用移动设备的访客的数据。 在区段定义中，容器为访问。 规则是 <p>移动设备不为空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自免费搜索的访问量 </td> 
   <td colname="col2">视图来自非付费搜索的访客的数据。 在区段定义中，容器为访问。 规则是 <p>付费搜索等于0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自非移动设备的访问 </td> 
   <td colname="col2">视图来自未使用移动设备的访客的数据。 在区段定义中，容器为访问。 此区段使用排除逻辑。 规则是 <p>移动设备类型等于手机 </p> <p>或 </p> <p>移动设备类型等于平板电脑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 电话访问 </td> 
   <td colname="col2">视图来自使用电话的访客的数据。 在区段定义中，容器为访问。 规则是 <p>设备类型等于手机。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自搜索引擎的访问 </td> 
   <td colname="col2">视图来自搜索引擎引用的访客的数据。 在区段定义中，容器为访问。 规则是 <p>推荐人类型等于搜索引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 来自社交网站的访问 </td> 
   <td colname="col2">视图来自社交网站所指访客的数据。 在区段定义中，容器为访问。 规则是 <p>推荐人类型等于社交网络。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 从平板电脑访问 </td> 
   <td colname="col2">视图来自使用平板电脑的访客的数据。 在区段定义中，容器为访问。 规则是 <p>设备类型等于平板电脑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用访客 ID Cookie 的访问量 </td> 
   <td colname="col2">从访客到您的站点的视图数据，其中需要永久cookie。 在区段定义中，容器为访问。 规则是 <p>永久Cookie等于1。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例：促销活动访客区段 {#concept_61AC6115097B4EB3AEFE8CE98F38315D}

显示此常用区段的示例。

许多客户希望查看对特定活动做出响应的访客的指标。 创建活动访客区段是获取此数据的简单方法。

在“区段生成器”中构建此区段意味着从顶级访问容器拖入活动维，在此例中为活动名称：

![](assets/seg_campaign_visitor.png)

（可选）如果您希望轻松筛选所有与活动相关的区段，您还可以将活动标记应用到此区段。
