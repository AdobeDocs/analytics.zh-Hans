---
title: 捕获内部搜索词
description: 使用自定义变量来捕获内部搜索词。
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---


# 捕获内部搜索词

内部搜索报表是许多组织不可或缺的一部分，不是 Adobe Analytics 的开箱即用维度。但是，只需极少的实施工作，即可轻松捕获内部搜索词报表。

## 先决条件

[验证开发实施并发布到生产环境](../launch/validate-publish-prod.md)：此页面假设您有一个基本的工作实施，并在 Adobe Debugger 中看到 Adobe Analytics 图像请求。

## 创建一个 eVar 以适应内部搜索

按照[转化变量管理员](/help/admin/admin/conversion-var-admin/conversion-var-admin.md)的指示，创建一个专用于内部搜索的新 eVar。为 eVar 取一个易于识别的名称（如“内部搜索词”），并将新 eVar 记录在您组织的[解决方案设计文档](../prepare/solution-design.md)中。

## 确定内部搜索关键词

大多数内部搜索使用查询字符串在页面之间传递关键词数据。使用您网站的内部搜索，并记下搜索结果页面上的 URL：

`https://example.com/search.html?q=kittens`

如果您网站的内部搜索不使用该 URL，请在其他位置查找搜索词，如数据层或 Cookie。如果您不确定在哪里可以找到内部搜索词，请咨询您的网站开发团队。

## 将查询字符串参数分配给数据元素

请遵循[将数据层对象映射到数据元素](../launch/layer-to-elements.md)。当选择&#x200B;**[!UICONTROL 数据元素类型]**&#x200B;时，请选择&#x200B;**[!UICONTROL 查询字符串参数]**&#x200B;而不是 **[!UICONTROL JavaScript 变量]**。将所需的查询字符串参数（通常为 `q`）放入文本字段。

## 将数据元素映射到 eVar

请遵循[将数据元素映射到 Analytics 变量](../launch/elements-to-variable.md)。确保您选择的 eVar 与您在报表包设置中创建的 eVar 相同。

## 开始部署标记

请遵循[将 Analytics 实施部署到开发环境](../launch/deploy-dev.md)。一旦确认它在您的开发环境中工作，就可以[验证开发实施并发布到生产环境](../launch/validate-publish-prod.md)。

## 在 Workspace 中报告

等待您的实施收集数据，然后您就可以开始使用 Analysis Workspace 中的维度。

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
2. 如果您没有自动登录 Adobe Analytics，则单击右上角的 9 宫格图标，然后选择 **[!UICONTROL Analytics]**。
3. 单击 **[!UICONTROL Workspace]** 选项卡，然后创建一个新项目。
4. 在“维度”下找到您创建的 eVar 的名称，然后将其拖到工作区画布上。
