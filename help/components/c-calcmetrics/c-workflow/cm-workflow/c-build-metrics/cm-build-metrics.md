---
description: 计算指标生成器提供了一个画布，用于拖放维度、指标、区段和函数，以基于容器层次结构逻辑、规则和运算符创建自定义指标。通过这个集成的开发工具，可生成并保存简单的计算指标或复杂的高级计算指标。
title: 生成量度
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: 75d8705170169a0ef9f1ee59b12e4bb2c3afac7a
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 43%

---

# 生成量度 {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="产品兼容性"
>abstract="表示此计算量度可用于 Customer Journey Analytics，例如 Analysis Workspace、Report Builder 等。某些计算量度无法与试验相结合。"
>additional-url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="在实验中使用计算量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="外部 ID"
>abstract="更改外部 ID 可能会影响计算量度在外部源（例如商业智能工具）中的显示方式"

<!-- markdownlint-enable MD034 -->

Adobe Analytics提供了一个画布以将维度、量度、区段和函数拖放到其中，从而根据容器层次结构逻辑、规则和运算符创建自定义量度。 通过这种集成式开发工具，您可以生成并保存简单或复杂的计算量度。

## 开始构建计算量度

您可以使用计算指标生成器创建计算指标。 通过这种方式创建时，计算量度在组件列表中可用，然后可在整个组织的项目中使用。 或者，还可创建快速计算量度，如[量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md)中的[为单个项目](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)创建计算量度中所述。

访问计算量度生成器，以开始创建组件列表中可用的计算量度。

1. 通过以下任意方式访问计算指标生成器：

   * 在Analysis Workspace中，打开一个项目，然后选择&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 创建指标]**。
   * 在Analysis Workspace中，打开一个项目，然后选择左边栏中&#x200B;[!UICONTROL **量度**]&#x200B;部分旁边的&#x200B;**加号**&#x200B;图标。
   * 在[!DNL Customer Journey Analytics]中，转到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 计算量度]**，然后选择计算量度页面顶部的&#x200B;**[!UICONTROL +添加]**。

1. 继续计算指标生成器](#areas-of-the-calculated-metrics-builder)的[区域。

## 计算指标生成器的区域

下图及随附的表介绍了计算量度生成器的某些主要区域和功能。

![](assets/cm_builder_ui.png)

| 图像中的位置 | 名称和功能 |
|---|---|
| 1 | **标题：**&#x200B;必须为量度命名。 如果没有命名，则无法保存指标。 |
| 2 | **描述：**&#x200B;为它提供用户友好的描述，以显示它的用途并区分它与类似的描述。 <p>该描述还会显示在报表内。最好不要在描述中放入公式，而是描述此指标应当用于哪些方面，不应当用于哪些方面。（公式会在您创建指标时生成，它位于“摘要”标题的下面。因此，无需将公式添加到描述中。） </p> |
| 3 | **格式：**&#x200B;选项包括“小数”、“时间”、“百分比”和“货币”。 |
| 4 | **小数位：**&#x200B;显示报告中将显示的小数位数。 您可以指定的最大小数位数为 10。 |
| 5 | **将上升趋势显示为：**&#x200B;此指标极性设置显示Analytics应当将指标中的上升趋势视为有利（绿色）还是不利（红色）。 最终，报表中的图表将在上升时显示为绿色或红色。 |
| 6 | **标记：**&#x200B;标记是组织量度的好方法。 所有用户均可创建标记，并将一个或多个标记应用于指标。但是，您只能查看您所拥有的或与您共享的那些区段的标记。应创建哪种类型的标记？以下是对实用标记的一些建议：<ul><li>**团队名称**，如社交营销、移动营销。</li><li>**项目** （分析标记），如登录页分析。</li><li>**类别**，如女性；地理位置。</li><li>**工作流**，如“待批准”；策划（为特定的业务部门）</li></ul> |
| 7 | **摘要：** <p>无论您何时对量度定义进行更改，概要公式都会随之发生更新。 当您将光标悬停在量度上并单击 <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />图标。 </p> |
| 8 | **定义：**&#x200B;您可以在此处拖入量度/计算量度、区段和/或函数来生成计算量度。 <ul><li>如果拖入一个计算指标，则它将自动展开其指标定义。 </li> <li>您可以通过容器嵌套定义。但是，与区段容器不同的是，这些容器的作用类似于数学表达式，它们决定着运算的顺序。 </li> </ul> |
| 9 | **运算符：**&#x200B;除以( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> )是默认运算符，另外还有+、 — 和x运算符。 |
| 10 | **预览：**&#x200B;提供对任何可能错误的快速读取。 预览涵盖过去 90 天的范围。这种方式可用于初步评估您是否为指标选择了正确的组件。出现意外结果表示您需要重新检查指标定义。 |
| 11 | **产品兼容性：**&#x200B;产品兼容性显示量度是与<a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=zh-Hans"  >当前数据</a>、完全处理数据兼容，还是只与营销渠道报表（首次联系分配）兼容。 <p>注意：“当前数据”并不支持所有指标。包含区段或函数的指标与“当前数据”不兼容。<a href="/help/components/c-calcmetrics/cm-compatibility.md"  > 更多... </a> </p> </p> |
| 12 | **添加：**&#x200B;对于所有类型的计算量度，可以将容器和静态数字添加到定义。 对于高级计算指标，您还可以添加区段和函数。 <ul><li>容器的作用类似于数学表达式，它们决定着运算的顺序。因此，容器中的任何内容都将在下次运算前得到处理。</li><li>将区段拖到容器上，会将该容器中的所有内容分段。（仅限高级计算指标）</li><li>您可以在一个容器中堆叠多个区段。</li></ul> |
| 13 | **齿轮图标（量度类型、归因）：**&#x200B;选择量度旁边的齿轮图标允许您指定<a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  >量度类型和归因模型</a>。 |
| 14 | **新：**&#x200B;允许您创建新组件，例如新区段（这会将您转到<a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  >区段生成器</a>）。 |
| 15 | **搜索组件：**&#x200B;通过此搜索栏，可搜索维度、量度、区段（仅限高级计算量度）和函数（仅限高级计算量度）。 |
| 16 | **Dimension列表：**&#x200B;要在区段生成器中生成一个简单的区段（例如“页面=主页”），您无需离开计算指标生成器，而是可以在“页面”中拖动并从计算指标生成器中直接选择“主页”。<p>这可以极大地简化用于创建分段计算指标的工作流程。</p> |
| 17 | **量度列表：**&#x200B;量度有3个类别： <ul> <li>标准量度(<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>计算量度( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">量度模板( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) — 位于列表底部。 </li> </ul> <p>当您将光标悬停在指标上方时，可以在其右侧看到“信息”图标： <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />。单击此图标会显示以下信息： </p><ul> <li>有关如何计算指标的公式。 </li><li>指标的预览趋势。 </li><li>编辑（铅笔）图标 位于右上角的<img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" />将带您进入计算量度生成器，您可以在其中编辑此计算量度。 </li></ul> |
| 18 | **区段列表：**（仅限高级计算指标）作为管理员，此列表显示在您的登录公司中创建的所有区段。 如果您不是管理员，此列表会显示您拥有的区段以及与您共享的区段。<a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=zh-Hans"  > 更多... </a> |
| 19 | **函数列表：** （仅限高级计算量度）函数分为两个列表：<a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  >基本</a> （最常用）和<a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  >高级</a>。 |
| 20 | **报表包选择器：**&#x200B;允许您切换到其他报表包。 |

{style="table-layout:auto"}
