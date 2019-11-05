---
title: 在 Launch 中创建 Analytics 属性
seo-title: 在 Adobe Experience Platform Launch 中创建 Adobe Analytics 属性
description: 使用 Adobe Experience Platform Launch 创建一个空间以自定义收集数据的方式。
seo-description: 使用 Adobe Experience Platform Launch 创建一个空间以自定义在 Adobe Analytics 中收集数据的方式。
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# 在 Adobe Experience Platform Launch 中创建 Analytics 属性

Adobe Experience Platform Launch 是一个可用于在您的网站（包括 Analytics）上集成 Experience Cloud 解决方案的工具。此页面专门概述了 Launch 管理员如何正确配置基本的 Adobe Analytics 实施。

## 先决条件

[创建报表包](/help/admin/admin-console/create-report-suite.md)：为要收集的 Analytics 数据创建一个容器

## 创建属性并安装重要扩展

属性是用于管理标记的主要容器。通过扩展，您可以安装和配置特定于产品的标记。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. 单击“新建属性”。
1. 为您的属性指定名称（如网站的标题），然后输入要在其中实施 Analytics 的域。单击“保存”。
1. 单击新创建的属性以输入其设置。
1. 单击“扩展”选项卡，然后单击“目录”。
1. 找到 Identity Service，然后单击“安装”。
1. 所有设置（包括 Experience Cloud 组织 ID）均应已填充。单击“保存”。
1. 返回扩展目录，找到 Adobe Analytics 并单击“安装”。

## 为 Adobe Analytics 创建数据元素

数据元素是对网站特定部分的引用，以便收集变量值。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
2. 单击要在网站上实施的 Launch 属性。
3. 单击“数据元素”选项卡，然后单击“创建新数据元素”。
4. 为数据元素指定以下设置：
   * 名称：页面名称
   * 扩展：核心
   * 数据元素类型：JavaScript 变量
   * 变量路径：`window.document.title`
      > [!NOTE] 注意：这是一个帮助您入门的示例值。如果您的组织为页面名称定义了更好的值（例如数据层值），则可以在此处输入该值。
   * 清理选中的文本
   * 持续时间：页面查看
5. 单击“保存”。

## 为 Adobe Analytics 创建规则

规则会将数据元素映射到 Analytics 变量值，并确定何时将这些值发送到 Adobe 的服务器。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. 单击要在网站上实施的 Launch 属性。
1. 单击“创建新规则”并将其命名为 `Global Rule`。
1. 单击事件旁边的“添加”，然后输入以下设置：
   * 扩展：核心
   * 事件类型：已加载的库（页面顶部）
   * 名称：核心 - 已加载的库（页面顶部）
   * 订购：50
1. 单击“保留更改”。
1. 在“操作”下，单击“添加”，然后输入以下设置：
   * 扩展：Adobe Analytics
   * 操作类型：设置变量
   * 页面名称：单击容器图标，然后选择 `Page Name` 数据元素。
   * 促销活动：值为 `cid` 的查询参数
1. 单击“保留更改”。
1. 单击操作旁边的加号以添加其他操作，然后输入以下设置：
   * 扩展：Adobe Analytics
   * 操作类型：发送信标
   * 名称：Adobe Analytics - 发送信标
   * 跟踪：s.t()
1. 单击“保留更改”。
1. 验证是否已设置事件和两个操作，然后单击“保存”。

## 文档和其他资源

* [Adobe Analytics扩展文档](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension):Adobe Experience Platform Launch中特定于Adobe Analytics扩展的完整文档。
* [Launch 快速入门](https://docs.adobelaunch.com/getting-started)：有关 Launch 的完整文档，包括更详细的入门指南
* [Adobe Experience Platform Launch youTube频道](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd):了解如何通过视频使用Launch

## 后续步骤

[将 Analytics 实施部署到开发环境](deploy-dev.md)：获取可在测试环境中运作的 Analytics 代码。
