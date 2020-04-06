---
title: “实施”模式窗口
description: 了解客户首次实施 Adobe Analytics 的体验。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# “实施”模式窗口

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

“欢迎使用 Adobe Analytics”模式窗口中提供了一个创建报表包的简化工作流。Adobe 建议当组织中需要更多报表包时使用此工作流。

![模式窗口屏幕截图](assets/implementation-modal.png)

## 先决条件

您的 Adobe ID 必须能够同时访问 Adobe Analytics 和 Adobe Experience Platform Launch。如果您无权访问 Launch，则可能会陷入身份验证循环，即系统不断要求您验证凭据。联系组织中的系统管理员以获取对 Launch 的访问权限。

## 访问模式窗口

访问此模式窗口以按以下步骤创建报表包。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 单击顶部的 9 宫格图标，然后单击 [!UICONTROL Adobe Analytics]。
3. 如果尚未创建报表包，则会自动显示此模式窗口。If a report suite exists for this login company, click the Help icon in the top right, then click [!UICONTROL Welcome to Adobe Analytics].

>[!NOTE] 仅 [!UICONTROL Welcome to Adobe Analytics] 当您通过Adobe Experience Cloud登录时，才会显示此选项。 如果通过旧域登录，则将不会显示此模式窗口。

## 创建报表包

Click the [!UICONTROL Start Setup] button to begin the report suite creation workflow.

![RS 向导](assets/analytics-implementation-rs-wizard.png)

### 属性类型

属性类型可帮助 Adobe 根据您计划实施 Analytics 的位置确定一些后端设置。

* **网站**：如果您计划仅为网站实施 Adobe Analytics。
* **本机移动设备应用程序**：如果您计划仅为移动设备应用程序实施 Adobe Analytics。
* **两者**：如果此报表包同时包含网站和移动设备应用程序的数据。

### 行业

指定您的主要商业模式。此设置可帮助 Adobe 根据您的主要商业模式预配置一些变量名称和设置。

### 数据层

[数据层](data-layer.md)是一种 JavaScript 对象，可将实施中使用的所有变量都整理到一个有用位置。有关更多信息，请参阅[数据层](data-layer.md)。

### 数据存储库

为您的报表包提供一个友好名称。您的报表包 ID (RSID) 会根据友好名称和登录公司自动生成。

### 时区

验证 Adobe 是否检测到报表包所处的正确时区。

### 估计每日页面查看次数

估计您的网站或应用程序每天的流量。Adobe 可根据此信息为您的报表包分配适量的处理资源。

### 基本货币

确定报表包存储货币值时所采用的币种。

>[!IMPORTANT] 确保声明正确的货币，特别是当具有与收入相关的报告要求时。数据收集开始后，很难更改基本货币。

## 实施资源

创建报表包后，您可以选择以下两个选项之一来继续实施：

* **转到 Adobe Experience Platform Launch**：将链接至 [launch.adobe.com](https://launch.adobe.com)，以配置实施和下载部署代码。请参阅[使用 Launch 实施](../launch/overview.md)。大多数情况下，Adobe 建议使用 Launch。
* **下载实施代码**：提供一个直接链接，通过该链接可下载手动实施 JavaScript 所需的 JavaScript 文件。请参阅 [AppMeasurement for JavaScript](../js/overview.md)。
