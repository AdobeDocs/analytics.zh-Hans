---
title: 创建报表包
seo-title: 在Adobe Analytics中创建报告套件
description: 在Adobe Analytics中为数据收集创建一个基本容器。
seo-description: 在Adobe Analytics中为数据收集创建一个基本容器。
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 创建报表包

报表包是Adobe Analytics用来提取报表的数据孤岛。组织可以有许多报表包，每个包都包含不同的数据集。虽然单独的报表套件在过去很重要，但拥有单个报表包变得更加有利。虚拟报告套件的简介和报告时间处理允许用户创建自己的子集，从而能够灵活获取全局和站点特定数据。

本文专为系统级管理员或分析管理员设计，用于准备数据收集。

## 先决条件

[Adobe Analytics第一批管理员指南](first-admin-guide.md)：确保系统级管理员授予您通过Experience Cloud Admin Console访问Adobe Analytics的权限

## 创建报表包

> [!NOTE]注意：还有一种方法可以使用传统管理员在Adobe Analytics中创建报表包。Adobe建议使用此处概述的报告套件设置向导。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. 单击右上角的方形图标，然后单击彩色的Analytics徽标。
1. 您应当看到“欢迎使用Adobe Analytics”模态窗口自动弹出。如果不是，请单击右上角的帮助图标，然后选择“欢迎使用Adobe Analytics”。
1. 在模态窗口中，单击“开始设置”。
1. 按照每个提示进行操作，这些提示列出了属性类型、行业和时区等基础知识。单击下一步。
1. 报表包现已创建。Adobe建议开发报告套件，因此测试不会影响客户数据。单击右上角的帮助图标，然后再次选择“欢迎使用Adobe Analytics”。
1. 在模态窗口中，单击“开始设置”。
将此报告套件命名为相同，但最终“-DEV”结束。由于此报表包只接收内部流量，估计的大小可以是最小的。
1. 单击“下一步”以完成开发报表包。

## 故障诊断

**登录Experience Cloud后，Analytics图标将灰显。**

这意味着您的帐户未被授予Analytics的正确权限。与组织中的系统级管理员合作，确保您属于具有访问Adobe Analytics的适当权限的配置文件。

**登录Adobe Analytics后，“欢迎使用Adobe Analytics”弹出和下拉菜单丢失。**

请确保您已通过Experience Cloud登录，而不是通过我的. omniture. com登录。通过my.omniture.com登录的用户没有可用的报告套件设置向导。

## 后续步骤

[在Launch](../../implement/implement-with-launch/create-analytics-property.md)中创建并配置Adobe Analytics的属性：创建一个用于管理Analytics实施的区域
