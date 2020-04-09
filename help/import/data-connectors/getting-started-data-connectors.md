---
description: 将跟踪数据从第三方应用程序导入到 Analytics 中。
title: Analytics Data Connectors 快速入门
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Data Connectors 概述

Adobe为组织提供与其数字战略和营销计划相关的可操作实时智能。 数据连接器允许您将跟踪数据从第三方应用程序导入Analytics，以便从一个中心位置收集和使用数据。 如果您使用合作伙伴产品之一，则可以创建将应用程序数据导入市场营销报告的集成。 集成后，您可以生成包含应用程序数据的报告。

例如，电子邮件集成可能希望使用电子邮件合作伙伴分发电子邮件活动。 当访客访问您的网站时，您希望了解哪些是响应您的电子邮件活动而来的。 数据连接器将来自电子邮件合作伙伴的数据集成到市场营销报告中，以便您确定此信息以评估电子邮件活动的有效性。

**系统要求**

数据连接器应与最流行的浏览器正确集成。 但是，报告在满足以下建议的系统上的显示效果和功能最好：

* 浏览器：Microsoft Internet Explorer版本6及更高版本
* Cookie:必需
* JavaScript:已启用
* 操作系统：基于Windows
* Macromedia Flash Player:版本6或更高版本
* 显示器分辨率：1024x768（800x600工作）
* 颜色深度：16位或更高

此外，用户的 Web 浏览器启用 JavaScript 时，还会改善数据收集。

**先决条件**

在为产品配置数据连接器集成之前，请执行以下操作：

* 拥有合作伙伴产品帐户的必要访问凭据，有权访问要与市场营销报告集成的所有数据。 您可能要为报告分发者创建一个特殊的电子邮件帐户，并为有关集成操作的通知创建该帐户。
* 识别包含您的活动信息的自定义变量。 这通常称为活动跟踪代码，但您的组织可能使用一些其他术语。
* 确定要接收印象和点击数据的事件。 您可能希望相应地重命名事件。
* 将相应代码放置在您的登陆页面上，这样 Analytics 就可以使用来自合作伙伴产品的数据进行相应的建模。可在“Data Connectors 展示区”的“资源”选项卡上找到每个合作伙伴产品的特定说明。

## 添加集成

您必须拥有有效帐户才能访问 [!UICONTROL Data Connectors] 登陆页面（控制台）。另外，建议您熟悉 Adobe Analytics。

1. 登录 Adobe Experience Cloud。
1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.
1. 单击 **[!UICONTROL Add New]**.
1. 遍历界 **[!UICONTROL Add Integration]** 面。

   根据各个产品集成，您可能需要在集成过程中提供特定的配置信息。

   集成完成后，合作伙伴产品图标会显示在“Data Connectors 网络”页面上，并且在菜单中可用。

## Data Connectors 控制台

激活集成后，该集成会显示在“[!UICONTROL Data Connectors]”页面上。您可以在控制台上查看详细信息并进行配置更改。您可以视图公司中所有报表包中的活动集成和集成。 您还可以视图活动日志、将集成设置为仪表板、配置集成和查找帮助。

![Data Connectors 控制台](assets/data-connectors-console.png)

## Data Connectors 中的再营销区段

再营销区段是基于 Data Connectors 集成所用变量创建的数据文件。

Adobe Analytics 会通过 Data Warehouse 将这些文件作为单独的每日文件发送至 Adobe 为第三方创建的 FTP。然后，第三方将这些文件分发到客户端。 公司通常使用这些工具将产品重新营销至那些可能访问过网站并查看过产品但未购买的产品。 （例如，您联系的客户对他们查看过但最终并未购买的产品提供折扣）。

**区段**

* [!UICONTROL 放弃购买]：将产品添加到购物车但没有完成购买的访客百分比。从技术上说，这是一种计算量度，由订购数除以购物车加货次数得到。
* [!UICONTROL 购买]：根据特定产品中的消息 ID 进行购买的收件人 ID 数（或访客 ID 数）。
* [!UICONTROL 产品查看]：与“[!UICONTROL 放弃购买]”类似，也是一种计算量度。它会报告[!UICONTROL 产品查看次数]除以订单数的结果，因为客户查看产品即反映出对该产品有一些兴趣。

**实施示例**

要成功实施再营销细分，必须满足以下条件：

* 数据连接器合同已经签订，贵组织已与Adobe顾问完成实施阶段。
* 相应的事件在products变量的同时触发：
   * 放弃购买：`scAdd` 事件
   * 购买：`purchase` 事件
   * 产品查看：`prodView` 事件

>[!NOTE] 如果定义的产品没有关联事件，则会自动触发 prodView 事件。如果不满足以上要求，那么相应的再营销区段将无法正常报告。

[!UICONTROL 放弃购买]：用户将产品添加到购物车后触发：

```
s.products=";cat";
s.events="scAdd";
```

[!UICONTROL 购买]：在购买确认页面触发：

```
s.products=";
cat;1;50";
s.events="purchase";
//Note: Though optional, adding the purchaseID variable increases accuracy by preventing duplicate purchases
```

**常见问题**

| 问题 | 描述 |
| -----------| ---------- |  
| 再营销区段文件中未显示产品ID信息。 | 当触发了正确的事件，但同一图像请求中不存在产品变量时，会发生这种情况。为了纠正这一错误，请确保products变量和相应的事件在同一页面上触发，如上述实施示例所示。 |
| 未收到再营销区段文件。 | 如果您未收到文件，请让贵组织的某个受支持用户与ClientCare联系以调查未成功接收报告的原因。 |


>[!IMPORTANT] 除了标准的 Data Connectors 集成再营销区段文件外，顾问通常还会设置 Data Warehouse 请求作为每日计划报表。此数据仓库请求将包括数据连接器变量和非数据连接器变量，并且该请求只能根据单位的特定请求来计划。 要防止在疑难排解时出现混淆，请指定相关文件是实际的再营销段文件还是包含非Genesis变量的数据仓库请求。
