---
description: 使用线条可视化描述趋势（基于时间）数据集
title: 折线图
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
translation-type: tm+mt
source-git-commit: 78ed02b7bb7a4dc042c837817d36fc8ce30dce79
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 17%

---


# 折线图

此可视化使用线条来表示量度，以显示一段时间内值的变化情况。仅当使用时间作为维度时，才可以使用折线图。

## “可视化图表”设置 

>[!IMPORTANT]
>
> 某些线条可视化设置（如“添加趋势线”）当前处于有限测试中。 [了解更多](https://docs.adobe.com/content/help/zh-Hans/analytics/landing/an-releases.html).

单击线可视化右上角的齿轮图标可访问可 [**视化设**](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html#section_D3BB5042A92245D8BF6BCF072C66624B) 置。 设置分为：

* 常规——在各种可视化类型中通用的设置
* 轴——影响线可视化的x轴或y轴的设置
* 叠加——用于向显示在线条可视化中的系列添加其他上下文的选项。

### 更改粒度

通过[可视化设置](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#section_D3BB5042A92245D8BF6BCF072C66624B)中的粒度下拉列表，可以将趋势可视化（例如折线图、条形图）从每日更改为每周、每月等。

### 添加趋势线叠加

在“ **可视化设置”>“叠加”>“添加趋势线**”下，您可以选择向行系列添加回归趋势线。 趋势线有助于在数据中描绘更清晰的图案。

所有模型都采用普通最小二乘拟合：

| 模型 | 描述 |
|---|---|
| 线性 | 为简单的线性数据集创建最适合的直线，当数据以稳定速率增加或减少时，该直线很有用。 等式：y = a + b * x |
| 对数 | 创建最适合的曲线，当数据更改率快速增加或减少，然后平铺时，该曲线很有用。 对数趋势线可使用负值和正值。 等式：y = a + b * log(x) |
| 指数 | 创建一条曲线，当数据以不断增加的速度上升或下降时，它非常有用。 如果数据包含零值或负值，则不应使用此选项。 等式：y = a +<sup>eb * x |
| 电源 | 创建一条曲线，对于比较以特定速率增加的测量值的数据集非常有用。 如果数据包含零值或负值，则不应使用此选项。 等式：y = a *<sup>xb |
| 二次型 | 找到最适合抛物线（上下凹）形状的数据集。 等式：y = a + b * x + c * x<sup>2 |
| 多项式 | 当数据集波动时（如分析大数据集上的增益和损失）非常有用。 等式：y = a + b * x + ... + k *<sup>xorder |
