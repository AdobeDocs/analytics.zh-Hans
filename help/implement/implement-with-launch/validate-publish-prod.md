---
title: 将 Adobe Analytics 部署到开发环境
seo-title: 将 Adobe Analytics 部署到开发环境
description: 了解如何使用 Adobe Experience Platform Launch 将 Adobe Analytics 部署到开发环境。
seo-description: 了解如何使用 Adobe Experience Platform Launch 将 Adobe Analytics 部署到开发环境。
translation-type: ht
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 验证开发实施并发布到生产环境

将 Adobe Experience Platform Launch 库推送到生产环境后，您的组织可以开始使用 Adobe Analytics 提取基本报表。

## 先决条件

[将 Analytics 实施部署到开发环境](deploy-dev.md)：必须将 Analytics 实施发布到您的开发环境，才能遵循本页进行操作。

## 使用 Experience Cloud 调试器验证您的开发实施

Experience cloud 调试器是一个 Chrome 插件，可显示页面上存在的所有 Experience Cloud 标记。

1. 打开 [Chrome Web 浏览器](https://www.google.com/chrome/)，然后转到 Chrome Web Store 上的 [Adobe Experience Cloud 调试器](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj)以安装该扩展。
2. 导航到已实施 Launch 的开发网站。
3. 单击 Chrome 右上角的 Adobe Experience Cloud 调试器图标
4. 如果一切都已正确实施，则应会在 Adobe Analytics、Adobe Experience Platform Launch 和 Adobe Experience Cloud 访客 ID 服务中看到以下内容：

![调试器][assets/debugger.png]

## 将开发实施部署到测试/生产环境

验证数据后，即可将实施推送到网站的在线版本。

1. 转到 [Adobe Experience Platform Launch](https://launch.adobe.com)，并在出现提示时登录。
2. 单击要在网站上实施的 Launch 属性。
3. 单击“发布”选项卡，并在开发列中找到您的库。
4. 单击库上的下拉列表，然后选择“提交以供审批”。在模态窗口中单击“提交”。
5. 再次单击库的下拉菜单（现在位于“已提交”列中），然后选择“为开发构建”。
6. 片刻后，库上的黄色指示灯变为绿色，表示已成功构建。
7. 再次单击库的下拉列表，然后选择“批准以供发布”。
8. 再次单击库的下拉列表（现在位于“已批准”列中），然后选择“构建并发布到生产环境”。
9. 转到“环境”选项卡，单击“生产环境”。
10. 复制生产页眉和页脚代码，并将其提供给您的网站所有者。请求他们在网站的生产环境中实施此代码。

## 验证您的生产实施

确认您会在网站的在线版本上看到数据，然后开始正式收集 Adobe Analytics 的数据。

1. 向网站所有者确认他们已将 Launch 代码推送到生产环境后，请在 Chrome 中导航到您网站的主页并打开 Adobe Experience Cloud 调试器。
2. 如果一切运行正常，您应会在开发环境中看到与测试类似的数据。此时，您将可收集网站上的数据，并且可以立即开始使用 Adobe Analytics 进行报告。

## 故障诊断

**调试器中不显示任何数据。**

在您的网站上，打开浏览器的开发人员控制台（通常按 F12）。查看页面的源代码，确保符合以下情况：

* 控制台中没有 JavaScript 错误。与贵组织的网站所有者合作，确保解决了所有 JS 错误。
* 正确实施了页眉代码：确保页眉代码位于 `<head>` 标记内部，并且文件存在。
* AppMeasurement 库存在：直接导航到 JS 源，以确保 JS 文件包含代码。如果不包含，请确保创建了每个环境，并且库已发布到各自对应的环境。
* 干扰插件：某些 Chrome 插件可阻止触发图像请求。禁用任何可能阻止将数据发送到 Adobe 服务器的插件。

## 后续步骤

现在，基本实施已经设置完毕，至于您想通过什么途径了解有关以下内容的更多信息，取决于您在贵组织中的角色：

* [创建解决方案设计文档](../prepare/solution-design.md)：制定有关如何使用自定义变量的计划，然后将其包含在实施中
* [开始使用 Analysis Workspace](../../analyze/analysis-workspace/home.md)：通过使用该工具的主要功能，深入研究 Adobe Analytics。
