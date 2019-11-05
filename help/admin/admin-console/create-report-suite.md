---
title: 创建报表包
seo-title: 在Adobe Analytics中创建报表包
description: 在Adobe Analytics中为数据收集创建基本容器。
seo-description: 在Adobe Analytics中为数据收集创建基本容器。
translation-type: tm+mt
source-git-commit: 4e3e164f5c28290ac280343d95cf5cb1186e09cd

---


# 创建报表包

报表包是Adobe Analytics用来拉取报表的数据库。 组织可以有许多报表包，每个报表包都包含不同的数据集。 虽然单独的报表包过去很重要，但拥有单个报表包已变得更有利。 虚拟报告套件的引入和报告时间处理允许用户创建自己的数据子集，从而允许灵活地获取全局数据和站点特定数据。

本文面向系统级管理员或分析管理员，旨在为数据收集做好准备。

## 先决条件

[Adobe Analytics第一管理指南](first-admin-guide.md):确保系统级管理员已授予您通过Experience Cloud Admin Console访问Adobe Analytics的权限

## 创建报表包

> [!NOTE]注意：还有一种方法可使用旧版管理员在Adobe Analytics中创建报表包。 Adobe建议使用此处概述的报表包设置向导。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
1. 您应该会自动弹出“欢迎使用Adobe Analytics”模式窗口。 如果不这样做，请单击右上角的帮助图标，然后选择“欢迎使用Adobe Analytics”。
1. 在模态窗口中，单击“开始设置”(Start Setup)。
1. 按照每个提示操作，概述基本信息，如财产类型、行业和时区。 单击下一步。
1. 报表包现已创建。 Adobe还建议您拥有一个开发报告套件，因此测试不会污染客户数据。 单击右上角的帮助图标，然后再次选择“欢迎使用Adobe Analytics”。
1. 在模态窗口中，单击“开始设置”(Start Setup)。
将此报告套件命名为相同名称，但在结尾处附加“- DEV”。 由于此报表包将仅接收内部流量，因此估计的大小可以是最小的。
1. 单击“下一步”以完成开发报告套件的创建。

## 故障诊断

**登录到Experience cloud后，Analytics图标将灰显。**

这意味着您的帐户尚未获得对Analytics的正确权限。 与组织中的系统级管理员合作，确保您属于具有访问Adobe Analytics足够权限的配置文件。

**登录Adobe Analytics后，“欢迎使用Adobe Analytics”弹出窗口和下拉框丢失。**

确保您已通过Experience cloud登录，而非通过my.omniture.com登录。 通过my.omniture.com登录的用户没有可用的报表包设置向导。

## 后续步骤

[在Launch中为Adobe Analytics创建和配置属性](/help/implement/implement-with-launch/create-analytics-property.md):创建管理Analytics实施的区域
