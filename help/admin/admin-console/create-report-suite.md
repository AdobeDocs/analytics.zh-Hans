---
title: 创建报表包
description: 在 Adobe Analytics 中创建用于数据收集的基本容器。
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# 创建报表包

报表包是一种数据存储库，Adobe Analytics 使用报表包提取单个报表。一个组织可以有多个报表包，每个报表包中包含不同的数据集。过去，有必要设置多个独立报表包，但现在单个报表包的优势变得日益凸显。引入虚拟报表包和报表时间处理后，用户可以自行创建子数据集，因而能够根据需要灵活地获取全局性数据和特定于网站的数据。

本文旨在帮助系统级别管理员或 Analytics 管理员做好数据收集前的准备工作。

## 先决条件

[Adobe Analytics 每一个管理员入门指南](first-admin-guide.md)：确保系统级别管理员已通过 Experience Cloud Admin Console 向您授予 Adobe Analytics 的访问权限

## 创建报表包

> [!NOTE] 在 Adobe Analytics 中，还可以使用旧版管理界面创建报表包。Adobe 建议使用此处介绍的报表包设置向导。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 单击右上角的 9 个正方形图标，然后单击彩色的 Analytics 徽标。
1. 此时，您应该会看到一个自动弹出的“欢迎使用 Adobe Analytics”模式窗口。如果没有看到该窗口，请单击右上方的帮助图标，然后选择“欢迎使用 Adobe Analytics”。
1. 在该模式窗口中，单击“开始设置”。
1. 按照每个提示操作，提示中会提供属性类型、行业和时区等基本信息。单击“下一步”。
1. 将立即创建报表包。Adobe 还建议您创建一个开发报表包，以免测试破坏客户数据。为此，请单击右上方的帮助图标，然后再次选择“欢迎使用 Adobe Analytics”。
1. 在弹出的模式窗口中，单击“开始设置”。
使用相同的名称命名此报表包，但要在后面附加“- DEV”。由于此报表包将仅接收内部流量，因此预估的大小可以为最小值。
1. 单击“下一步”，即可完成创建开发报表包。

有关此模态窗口中的步骤的详细信息，请参阅“实 [施用户指南](/help/implement/prepare/implementation-modal.md) ”中的实施模态。

## 故障诊断

**登录到 Experience Cloud 后，Analytics 图标显示为灰色。**

这意味着您的帐户尚未获得所需的 Analytics 访问权限。与组织中的系统级别管理员合作，确保您所属的配置文件具有足够权限访问 Adobe Analytics。

**登录到 Adobe Analytics 后，看不到“欢迎使用 Adobe Analytics”弹出窗口和下拉列表。**

确保您是通过 Experience Cloud 而不是 my.omniture.com 登录的。如果用户通过 my.omniture.com 登录，将不会显示报表包设置向导。

## 后续步骤

[在 Launch 中创建并配置 Adobe Analytics 资产](/help/implement/launch/create-analytics-property.md)：创建一个用于管理 Analytics 实施的区域
