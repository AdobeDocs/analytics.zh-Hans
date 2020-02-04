---
title: 实施模式
description: 了解客户首次实施 Adobe Analytics 的体验。
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 实施模式

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

“欢迎使用Adobe Analytics”模式窗口提供了一个简化的创建报表包的工作流程。 Adobe建议在组织中需要更多报表包时使用此工作流。

![Modal屏幕截图](assets/implementation-modal.png)

## 先决条件

您的Adobe ID必须有权访问Adobe Analytics和Adobe Experience Platform Launch。 如果您无权访问Launch，则可以放入一个身份验证循环，该循环会要求您无限期地验证凭据。 与组织中的系统管理员交谈以获取对Launch的访问权限。

## 访问模态

访问该模式，可使用以下步骤创建报表包。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. Click the 9-grid icon at the top, then click [!UICONTROL Adobe Analytics].
3. 如果尚未创建报表包，则会自动显示该模式。 如果此登录公司存在报表包，请单击右上方的“帮助”图标，然后单击“欢 [!UICONTROL 迎使用Adobe Analytics]”。

> [!NOTE] 仅 [!UICONTROL 当您通过Adobe Experience cloud登录时] ，才会显示欢迎使用Adobe Analytics选项。 如果通过旧域登录，则模态不可用。

## 创建报表包

单击“开 [!UICONTROL 始设置] ”按钮以开始报表包创建工作流。

![RS向导](assets/analytics-implementation-rs-wizard.png)

### 属性类型

属性类型可帮助Adobe根据您计划实施Analytics的位置确定一些后端设置。

* **网站**:如果您打算仅为网站实施Adobe Analytics。
* **本机移动应用程序**:如果您打算仅为移动应用程序实施Adobe Analytics。
* **两者**:如果此报表包包含网站和移动应用程序的数据。

### 行业

指定您的主要业务模式。 此设置可帮助Adobe根据您的主要业务模式预配置某些变量名称和设置。

### 数据层

数 [据层是JavaScript对象](data-layer.md) ，它将实现中使用的所有变量组织到一个有用的位置。 有关更 [多信息](data-layer.md) ，请参阅数据层。

### 数据存储库

为您的报表包提供一个友好的名称。 您的报表包ID(RSID)会根据友好名称和登录公司自动生成。

### 时区

验证Adobe是否检测到报表包的正确时区。

### 估计的每日页面查看次数

估计您的网站或应用程序每天的流量。 此信息允许Adobe为您的报表包分配正确的处理资源量。

### 基本货币

确定报表包存储货币值的币种。

> [!IMPORTANT] 确保您声明了正确的货币，特别是如果您有收入相关的报告要求。 数据收集开始后，很难更改基本货币。

## 实施资源

创建报表包后，您有以下两个选项之一来继续实施：

* **转到Adobe Experience Platform Launch**:将您链接到 [launch.adobe.com](https://launch.adobe.com) ，以配置实施和下载部署代码。 请参阅[使用 Launch 实施](../launch/overview.md)。Adobe建议在大多数情况下使用Launch。
* **下载实施代码**:提供用于手动JavaScript实现的下载JavaScript文件的直接链接。 请参阅 [AppMeasurement for JavaScript](../js/overview.md)。
