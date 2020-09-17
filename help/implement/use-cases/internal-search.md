---
title: 捕获内部搜索词
description: 使用自定义变量捕获内部搜索词。
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---


# 捕获内部搜索词

内部搜索报告是许多组织不可或缺的一部分，与Adobe Analytics不是现成的维度。 但是，只要执行工作很少，内部搜索词报告就很容易捕获。

## 先决条件

[验证开发实施并发布到生产](../launch/validate-publish-prod.md):本页假定您有一个基本的工作实现，并在Adobe调试器中查看Adobe Analytics图像请求。

## 创建eVar以适应内部搜索

按照 [转化变量管理](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) ，创建专用于内部搜索的新eVar。 为eVar提供一个易于识别的名称（如“内部搜索词”），并将新eVar记录在您组织的“解决方案” [设计文档中](../prepare/solution-design.md)。

## 确定内部搜索关键字

大多数内部搜索使用查询字符串在页面之间传递关键字数据。 使用网站的内部搜索，并在搜索结果页面上记下URL:

`https://example.com/search.html?q=kittens`

如果网站的内部搜索未使用该URL，请在其他位置（如数据层或cookie）查找搜索词。 如果您不确定在何处查找内部搜索词，请与站点开发团队合作。

## 将查询字符串参数指定给数据元素

Follow [Map data layer objects to data elements](../launch/layer-to-elements.md). 选择“数据 **[!UICONTROL 元素类型]**”时， **[!UICONTROL 选择查询字符串参]** 数，而 **[!UICONTROL 不是JavaScript变量]**。 将所需的查询字符串参数(通 `q`常)放在文本字段中。

## 将数据元素映射到eVar

Follow [Map Launch data elements to Analytics variables](../launch/elements-to-variable.md). 确保选择在“报表包”设置中创建的eVar。

## 开始启动部署过程

Follow [Deploy an Analytics implementation to a development environment](../launch/deploy-dev.md). 一旦您确认它正在开发环境中工作，您就可以验 [证开发实施并发布到生产](../launch/validate-publish-prod.md)。

## 工作区中的报告

给您的实施一些时间来收集数据，然后您可以使用Analysis Workspace的维度进行开始。

1. 使用您的 AdobeID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 如果您没有自动登录Adobe Analytics，请单击右上角的9网格图标，然后选择 **[!UICONTROL Analytics]**。
3. 单击“工 **[!UICONTROL 作区]** ”选项卡，然后创建新项目。
4. 找到您在Dimension下创建的eVar的名称，并将其拖动到工作区画布。
