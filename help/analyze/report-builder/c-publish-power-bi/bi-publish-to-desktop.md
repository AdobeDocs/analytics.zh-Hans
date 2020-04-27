---
description: 介绍如何将 Report Builder 发布的资产提取到 Power BI Desktop
title: 将已发布的资产提取到 Power BI Desktop
uuid: ef47d5c7-31e0-44fc-a792-bc9d12bb089e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 将已发布的资产提取到 Power BI Desktop

介绍如何将 Report Builder 发布的资产提取到 Power BI Desktop

## 先决条件 {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* 您需要安装最新的 Power BI Desktop 版本（2017 年 4 月版）
* 此过程假定您已将 Report Builder 格式的表或请求发布到 Power BI 服务。

## 过程 {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

在 Power BI Desktop 的 2017 年 4 月更新中，Microsoft 发布了可连接到 Power BI 服务中数据集的功能。此功能允许您根据已发布到云的现有数据集创建新报表。您可以利用此功能加强团队间的协作并减少重复劳动。

1. 在Power BI Desktop中，转到 **[!UICONTROL File]** > **[!UICONTROL Options and settings]** > **[!UICONTROL Options]** > **[!UICONTROL Preview features.]**
1. 启用 **[!UICONTROL Power BI Service Live Connection]** 并单击 **[!UICONTROL OK]**。 ![](assets/bi-preview-features.png)

1. 重新启动 Power BI Desktop。
1. 重新启动桌面后，转到 **[!UICONTROL Home]** > **[!UICONTROL Get Data]** > **[!UICONTROL More...]**。
1. 搜索并选择 **[!UICONTROL Power BI service]**。
1. 在 **[!UICONTROL Microsoft Power BI service]** > **[!UICONTROL My Workspace]**&#x200B;下，选择您之前从Report Builder发布的数据集。

有关更多信息，请参阅此 [Microsoft 博客文章](https://powerbi.microsoft.com/zh-cn/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/)。
