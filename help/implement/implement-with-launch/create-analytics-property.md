---
title: 在Launch中创建Analytics属性
seo-title: 在Adobe Experience Platform Launch中创建Adobe Analytics属性
description: 使用Adobe Experience Platform Launch创建一个空间，以自定义数据的收集方式。
seo-description: 使用Adobe Experience Platform Launch创建一个空间，以自定义在Adobe Analytics中收集数据的方式。
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 在Adobe Experience Platform Launch中创建Analytics属性

Adobe Experience Platform Launch是可用于在您的网站(包括Analytics)中集成Experience Cloud解决方案的工具。本页明确介绍了Launch管理员如何正确配置基础Adobe Analytics实施。

## 先决条件

[创建报表包](../../admin/admin-console/create-report-suite.md)：创建用于收集Analytics数据的孤岛

## 创建一个属性并安装重要扩展

属性是指用于管理标记的覆盖容器。扩展允许您安装特定于产品的标记并配置它们。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. 单击“New Property”。
1. 为您的属性提供名称(如网站标题)，然后输入您希望在上实施Analytics的域。单击“保存”。
1. 单击新创建的属性以输入其设置。
1. 单击“扩展”选项卡，然后单击“目录”。
1. 找到标识服务，然后单击安装。
1. 所有设置(包括Experience Cloud组织ID)都应已填写。单击“保存”。
1. 返回到扩展目录，找到Adobe Analytics，然后单击安装。

## 为Adobe Analytics创建数据元素

数据元素是对网站特定部分的引用以收集变量值。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
2. 单击要在站点上实施的启动项属性。
3. 单击“数据元素”选项卡，然后单击“创建新数据元素”。
4. 为数据元素提供以下设置：
   * 名称：页面名称
   * 扩展：核心
   * 数据元素类型：JavaScript变量
   * Path to variable: `window.document.title`
      > [!NOTE] 注意：这是一个可帮助入门的示例值。如果您的组织为页面名称定义了更高的值(如数据图层值)，则可以在此处输入该值。
   * 选中了清除文本
   * 持续时间：页面查看
5. 单击“保存”。

## 创建Adobe Analytics规则

规则将数据元素映射到Analytics变量值，并确定这些值何时发送到Adobe服务器。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. 单击要在站点上实施的启动项属性。
1. Click Create New Rule and name it `Global Rule`.
1. 单击活动旁边的“添加”，然后输入以下设置：
   * 扩展：核心
   * 事件类型：加载的库(页面顶部)
   * 名称：核心-加载的库(页面顶部)
   * 订单：50
1. 单击保留更改。
1. 在“操作”下，单击“添加”，然后输入以下设置：
   * 扩展：Adobe Analytics
   * 操作类型：设置变量
   * Page Name: click the container icon, and select the `Page Name` data element.
   * Campaign: Query parameter with a value of `cid`
1. 单击保留更改。
1. 单击操作旁边的加号以添加其他操作，然后输入以下设置：
   * 扩展：Adobe Analytics
   * 操作类型：发送信标
   * 名称：Adobe Analytics-发送信标
   * 跟踪：s. t()
1. 单击保留更改。
1. 确认您有活动和两个操作集，然后单击“保存”。

## 文档和其他资源

* [Adobe Analytics扩展文档](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension)：Adobe Experience Platform Launch中特定于Adobe Analytics扩展的完整文档。
* [Launch](https://docs.adobelaunch.com/getting-started)入门：有关Launch的完整文档，包括更深入的入门指南
* [Adobe Experience Platform Launch YouTube频道](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd)：了解如何通过视频使用Launch

## 后续步骤

[将Analytics实施部署到开发环境](deploy-dev.md)：获取在测试环境中工作的Analytics代码。
