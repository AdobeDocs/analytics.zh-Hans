---
title: 移动记分卡注释
description: 了解如何在移动记分卡中显示注释。
role: User, Admin
solution: Analytics
feature: Components
exl-id: d8212ab1-d639-41b5-b28e-da580a3628b0
source-git-commit: 0e7a9aa92c8c5b61fffae96d42bd1b258920e99d
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 2%

---


# 在移动记分卡中共享注释

您可以在移动记分卡中显示在工作区中创建的注释。 这允许您直接在移动记分卡项目中共享与您的组织和促销活动有关的上下文数据细微差别和分析，这些项目可在Analytics功能板移动应用程序中查看。

## 移动记分卡中的表面批注

要在移动记分卡中显示注释，请先从工作区项目或组件菜单中创建注释。

有关创建注释的信息，请参阅 [创建注释](create-annotations.md). 默认情况下，移动记分卡中会关闭注释，并且必须为要在移动记分卡中显示的每个记分卡启用注释。

1. 打开注释。 要打开注释，请参阅 [打开或关闭注释](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=en#turn-annotations-on-or-off).

1. 创建注释，并确保已将其共享给所有项目。 要在工作区中创建注释，请参阅 [创建注释](create-annotations.md).

1. 选择 **显示注释** ，以在移动记分卡中显示注释。

<img src="assets/show-annotations.png"  width="75%">

1. 确认已选择显示批注，请转到 **项目** > **项目信息和设置**.

<img src="assets/project-info-settings.png" width="40%">

## 在移动记分卡中查看注释

启用注释后，注释图标会在记分卡生成器中显示。 注释仅在详细视图的图表和表格上显示。 注释在记分卡的主图块视图中不可见。

<img src="assets/view-annotations.png"  width="75%">

当注释图标可见时，无法在生成器画布中完全查看注释或与注释进行交互。 使用预览模式可查看应用程序中显示的批注并与之交互。 ![](assets/preview-icon.png)

在工作区中创建注释时，将选择注释颜色。 灰色批注表示存在多个批注。 ![](assets/gray-annotations1.png) ![](assets/gray-annotations2.png)

## 查看图表批注

| 日期 | 外观 |
| --- | --- |
| **一天** | <img src="assets/single-day-mobile-annotations.png"  width="30%"><br></br> |
| **日期范围** | <img src="assets/date-range.png"  width="30%"> |
| **重叠注释** | <img src="assets/overlapping-annotations.png"  width="30%"><br></br>要在Analytics功能板应用程序中查看注释详细信息，请点按注释图标。 <br></br>在图表中查看注释时，您可以向左和向右轻扫以导航图表中存在的所有注释。 在表中查看注释时，向左和向右轻扫可导航与表中该行项目关联的所有注释。 <br></br><img src="assets/swipe-multiple-annotations.png"  width="30%"> <br></br>在没有基于时间的图表中 *x轴*&#x200B;例如，点按右下角的图标，可查看应用于图表的注释，如圆环图或水平条形图。<br></br> <img src="assets/charts-without-timebase.png"  width="30%"> |