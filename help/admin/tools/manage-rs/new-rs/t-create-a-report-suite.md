---
description: 创建用于在 Adobe Analytics 中收集数据的基本容器
title: 创建报表包
feature: Report Suite Settings
exl-id: 255ae051-d993-41a5-8cf3-819a54c17e34
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 98%

---

# 创建报表包

报表包是一种数据存储库，Adobe Analytics 使用报表包提取单个报表。一个组织可以有多个报表包，每个报表包中包含不同的数据集。过去，有必要设置多个独立报表包，但现在单个报表包的优势变得日益凸显。通过引入[虚拟报表包](/help/components/vrs/vrs-about.md#virtual-report-suites)和报表时间处理，管理员可创建您自己的数据子集，使得可灵活地获取全局数据和站点专属数据。

本文旨在帮助系统级别管理员或 Adobe Analytics 管理员为数据收集做好准备。

## 先决条件

[Adobe Analytics 首位管理员指南](/help/admin/admin-console/first-admin-guide.md)：确保有一位系统级别管理员已通过 Experience Cloud Admin Console 准许您访问 Adobe Analytics。

## 创建报表包 {#create-report-suite}

1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 单击&#x200B;**[!UICONTROL 添加报表包]**。
1. 选择要用作[模板](/help/admin/tools/manage-rs/rs-templates/report-suite-templates.md)的预定义模板或现有报表包。

   >[!NOTE]
   >
   >只能复制设置，而不能复制数据。如果客户关怀团队复制设置，您将需要对客户关怀团队提供的与所涉及的风险相关的免责声明进行书面确认。请参阅[不会从源报表包复制的设置](/help/admin/tools/manage-rs/new-rs/settings-not-copied-from-rs.md)，以了解更多信息。

1. 填写[新的报表包](/help/admin/tools/manage-rs/new-rs/new-report-suite.md)中描述的字段。
1. 单击“**[!UICONTROL 创建报表包]**”。

报表包 ID 最长为 40 字节。报表包易记名称最长为 255 字节。

## 故障诊断

**登录到 Experience Cloud 后，Analytics 图标显示为灰色。**

这意味着您的帐户尚未获得所需的 Analytics 访问权限。与组织中的系统级别管理员合作，确保您所属的轮廓具有足够权限访问 Adobe Analytics。

## 后续步骤

[创建 Adobe Analytics 标记属性](/help/implement/launch/create-analytics-property.md)：创建一个区域以管理您的 Analytics 实施。
