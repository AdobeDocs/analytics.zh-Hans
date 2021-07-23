---
title: 捕获内部搜索词
description: 使用自定义变量捕获内部搜索词。
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---


# 捕获内部搜索词

内部搜索报表是许多组织必不可少的组成部分，对于Adobe Analytics来说，它不是一个现成的维度。 但是，只要执行少量工作，就可以轻松捕获内部搜索词报表。

## 先决条件

[验证开发实施并发布到生产环境](../launch/validate-publish-prod.md):本页假定您具有基本的正常实施，并在Debugger中查看Adobe Analytics图像请求。

## 创建eVar以适应内部搜索

按照[转化变量管理员](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)创建专用于内部搜索的新eVar。 为eVar提供一个易于识别的名称（如“内部搜索词”），并在贵组织的[解决方案设计文档](../prepare/solution-design.md)中记录新eVar。

## 确定内部搜索关键词

大多数内部搜索使用查询字符串来在页面之间传递关键词数据。 使用网站的内部搜索，并在搜索结果页面上记下URL:

`https://example.com/search.html?q=kittens`

如果您网站的内部搜索未使用URL，请在其他位置（如数据层或Cookie）查找搜索词。 如果您不确定在何处查找内部搜索词，请与网站开发团队合作。

## 将查询字符串参数分配给数据元素

按照[将数据层对象映射到数据元素](../launch/layer-to-elements.md)。 选择&#x200B;**[!UICONTROL 数据元素类型]**&#x200B;时，请选择&#x200B;**[!UICONTROL 查询字符串参数]**，而不是&#x200B;**[!UICONTROL JavaScript变量]**。 将所需的查询字符串参数（通常为`q`）放在文本字段中。

## 将数据元素映射到eVar

请按照[将数据元素映射到Analytics变量](../launch/elements-to-variable.md)。 确保选择与在报表包设置中创建的eVar相同的数据。

## 开始部署标记

请按照[将Analytics实施部署到开发环境](../launch/deploy-dev.md)。 确认开发环境中运行正常后，您可以[验证开发实施并发布到生产环境](../launch/validate-publish-prod.md)。

## 工作区中的报表

为您的实施留出一些时间来收集数据，然后您便可以开始在Analysis Workspace中使用维度。

1. 使用您的 AdobeID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 如果您没有自动登录Adobe Analytics，请单击右上方的9宫格图标，然后选择&#x200B;**[!UICONTROL Analytics]**。
3. 单击&#x200B;**[!UICONTROL 工作区]**&#x200B;选项卡，然后创建新项目。
4. 找到在“eVar”下创建的Dimension的名称，并将其拖动到工作区画布。
