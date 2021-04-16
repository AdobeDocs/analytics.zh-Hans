---
description: 在Adobe Analytics中为数据收集创建基本容器
title: 创建报表包
feature: 管理工具
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 75%

---

# 创建报表包

报表包是一种数据存储库，Adobe Analytics 使用报表包提取单个报表。一个组织可以有多个报表包，每个报表包中包含不同的数据集。过去，有必要设置多个独立报表包，但现在单个报表包的优势变得日益凸显。[虚拟报表包](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en#virtual-report-suites)和报表时间处理的引入使管理员能够创建您自己的数据子集，从而灵活地获取全局数据和站点特定数据。

本文旨在帮助系统级别管理员或 Analytics 管理员做好数据收集前的准备工作。

## 先决条件

[Adobe Analytics第一份管理指南](/help/admin/admin-console/first-admin-guide.md):确保系统级管理员已授予您通过Experience CloudAdmin Console访问Adobe Analytics的权限。

## 创建报表包 {#create-report-suite}

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 单击&#x200B;**[!UICONTROL “新建”]**>**[!UICONTROL “报表包”]**。
1. 要复制报表包的设置，请在模板列表中，选择预定义的模板，或选择现有的报表包以用作[模板](/help/admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)。

   >[!NOTE]
   >
   >只能复制设置，而不能复制数据。如果客户关怀团队复制设置，您将需要对客户关怀团队提供的与所涉及的风险相关的免责声明进行书面确认。请参阅[不会从源报表包复制的设置](/help/admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)，以了解更多信息。

1. 填写[新的报表包](/help/admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)中描述的字段。
1. 单击&#x200B;**[!UICONTROL 创建报表包]**。

报表包ID的最大长度为40字节。 报表包友好名称的最大长度为255字节。

## 故障诊断

**登录到 Experience Cloud 后，Analytics 图标显示为灰色。**

这意味着您的帐户尚未获得所需的 Analytics 访问权限。与组织中的系统级别管理员合作，确保您所属的配置文件具有足够权限访问 Adobe Analytics。

**登录到 Adobe Analytics 后，看不到“欢迎使用 Adobe Analytics”弹出窗口和下拉列表。**

确保您是通过 Experience Cloud 而不是 my.omniture.com 登录的。如果用户通过 my.omniture.com 登录，将不会显示报表包设置向导。

## 后续步骤

[在 Launch 中创建并配置 Adobe Analytics 资产](/help/implement/launch/create-analytics-property.md)：创建一个用于管理 Analytics 实施的区域
