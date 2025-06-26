---
description: 了解
title: 量度类型和归因
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 07590d00341f9016ee0728970483e77cb8d38a9d
workflow-type: ht
source-wordcount: '603'
ht-degree: 100%

---

# 量度类型和归因 {#metric-type-attribution}

您可以为计算量度定义中的量度配置量度类型和[归因模型](#attribution-models)。

1. 选择量度组件中的![设置](/help/assets/icons/Setting.svg)。
1. 在弹出的对话框中：

   ![指标类型和归因](assets/cm-type-alloc.png)

   * 指定&#x200B;**[!UICONTROL 量度类型]**：

     | 量度类型 | 定义 |
     |---|---|
     | **[!UICONTROL 标准]** | 如果一个公式包含一个单一的标准量度，它会显示与其相对的非计算量度的相同数据。标准量度可用于创建特定于每个单独行项目的计算量度。 <p>例如，![事件](/help/assets/icons/Event.svg) **[!UICONTROL 订单]** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 访问次数]**&#x200B;会获取该特定行项目的订单数，并将其除以该特定行项目的访问次数。 |
     | **[!UICONTROL 全部总计]** | 使用每个行项目中报告时段的&#x200B;**[!UICONTROL 全部总计]**。如果一个公式是由单个全部总计量度组成的，则计算量度会在每个行项目上显示相同的“全部总计”数字。全部总计量度可用于创建与总计数据相比较的计算量度。 <p>例如，![事件](/help/assets/icons/Event.svg) **[!UICONTROL 订单]** ![划分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 总访问次数]** 显示订单占所有访问次数的比例，而不仅仅是特定行项目的访问次数。在此示例中，您指定计算量度中![事件](/help/assets/icons/Event.svg)**[!UICONTROL 访问次数]**&#x200B;量度的&#x200B;**[!UICONTROL 全部总计]**，这将自动将其转换为![事件](/help/assets/icons/Event.svg)**[!UICONTROL 总访问次数]**。 |

   * 指定&#x200B;**[!UICONTROL 归因]**。

      1. 您可以：

         * 禁用&#x200B;**[!UICONTROL 使用非默认归因模型]**&#x200B;来使用默认的列归因模型，即“上次接触”，其回溯期为 30 天。
         * 启用&#x200B;**[!UICONTROL 使用非默认的归因模型]**。在&#x200B;**[!UICONTROL 列归因模型]**&#x200B;对话框中，

            * 从[归因模型](#attribution-models)中选择一个&#x200B;**[!UICONTROL 模型]**。
            * 从[容器](#container)选项中选择一个&#x200B;**[!UICONTROL 容器]**。
            * 从[回溯时间范围](#lookback-window)选项中选择&#x200B;**[!UICONTROL 回溯时间范围]**。如果您选择&#x200B;**[!UICONTROL 自定义时间]**，则可定义时段，单位为&#x200B;**[!UICONTROL 分钟]**&#x200B;至&#x200B;**[!UICONTROL 季度]**。

      1. 选择&#x200B;**[!UICONTROL 应用]**&#x200B;来应用非默认归因模型。选择“取消”即可取消。

     如果您已定义非默认归因模型，请选择&#x200B;**[!UICONTROL 编辑]**&#x200B;来修改选择。

请参阅[示例](#example)，了解如何使用归因模型、容器和回溯时间范围。


## 归因模型 {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="使用非默认的属性模型"
>abstract="为所选量度启用非默认归因模型。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="模型"
>abstract="选择量度的归因模型。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="最后接触"
>abstract="100% 的点数归于访客看到的最后一个维度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="首次接触"
>abstract="100% 的点数归于访客看到的第一个维度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="线性"
>abstract="点数均匀分布于所有维度值上。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="参与率"
>abstract="100% 的点数归于访客所见的每个维度值。<br/>列总数被夸大了。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同一接触"
>abstract="仅对与转化发生在同一事件上的维度值给予点数。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="同一接触"
>abstract="仅对与转化发生在同一事件上的维度值给予点数。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 型"
>abstract="第一个维度值占 40%，最后一个维度值占 40%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J 曲线"
>abstract="最后一个维度值占 60%，第一个维度值占 20%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J 曲线"
>abstract="最后一个维度值占 60%，第一个维度值占 20%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="反向 J"
>abstract="第一个维度值占 60%，最后一个维度值占 20%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="反向 J"
>abstract="第一个维度值占 60%，最后一个维度值占 20%，中间维度值占 20%。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="时间衰减"
>abstract="距离转化时间最近的维度值将获得最多的点数。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="自定义"
>abstract="根据归因权重，自行定义您的位置。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="自定义"
>abstract="根据归因权重，自行定义您的位置。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="算法"
>abstract="点数是根据统计算法动态确定的。"

{{attribution-models-details}}


## 容器 {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="容器"
>abstract="选择一个容器来设置所需的归因范围。"

{{attribution-container}}


## 回溯时间范围 {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="回溯时间范围"
>abstract="此设置可以确定将要对每次转化应用的数据归因时间范围。"

{{attribution-lookback-window}}

## 示例

{{attribution-example}}


<!--
When [building a calculated metric](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), you can specify the metric type and the attribution model.

## Metric type

To specify the metric type when building a calculated metric:

1. Select the gear icon next to the metric whose type you want to select.

   ![](assets/cm-type-alloc.png) 

1. Choose from the following options:

   |  Metric Type  | Definition  |
   |---|---|
   |  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item.  |
   |  Grand total  | Use Grand total for the reporting period in every line item. If a formula consisted of a single Grand total metric, it displays the same total number on every line item. Grand total metrics are useful for creating calculated metrics that compare against site total data. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item.  |

## How linear allocation works

[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) is how allocation models in calculated metrics are evaluated.

For a full list of non-default attribution models and lookback windows supported, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).

The following example illustrates how calculated metrics with linear allocations work in reporting: 

| | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
|Data Sent In|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|
|Last Touch eVar|PROMO A|PROMO A|PROMO A|PROMO B|PROMO B|PROMO C|$10|
|First Touch eVar|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|$10|
|Example prop|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|

In this example, the values A, B, and C were sent into a variable on hits 1, 3, 4, and 6 before a $10 purchase was made on hit 7. In the second row, those values persist across hits on a last touch visit basis. The third row illustrates a first-touch visit persistence. Finally, the last row illustrates how data would be recorded for a prop which does not have persistence.

-->