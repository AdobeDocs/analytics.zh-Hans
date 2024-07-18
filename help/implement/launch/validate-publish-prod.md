---
title: 验证开发实施并发布到生产环境
description: 了解如何使用 Adobe Experience Platform 标记将 Adobe Analytics 部署到生产环境。
feature: Tags
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
role: Admin, Developer
source-git-commit: e35210582e94037cf286b98e7e0a6b06040a8c6f
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 89%

---

# 验证开发实施并发布到生产环境

将标记库推送到生产环境后，您的组织可以开始使用 Adobe Analytics 提取基本报表。

## 先决条件

[将 Analytics 实施部署到开发环境](deploy-dev.md)：必须将 Analytics 实施发布到您的开发环境，才能遵循本页进行操作。

## 使用 Experience Cloud Debugger 验证您的开发实施

Experience Cloud Debugger 是一个可显示页面上存在的所有 Experience Cloud 标记的扩展。

1. 安装[Chrome](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob)或Firefox的扩展。
2. 导航到已实施标记的开发网站。
3. 单击浏览器中的 Adobe Experience Cloud Debugger 图标。
4. 如果一切都已正确实施，则应会看到 Adobe Analytics、标记和 Adobe Experience Cloud 访客 ID 服务中的内容。

## 将开发实施部署到测试/生产环境

一旦确认看到数据，则可在网站实时版本推出实施。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
1. 单击要在网站上实施的标记属性。
1. 单击&#x200B;**[!UICONTROL 发布]**&#x200B;选项卡，并在开发列中找到您的库。
1. 单击库上的下拉列表，然后选择&#x200B;**[!UICONTROL 提交以供审批]**。 在模态窗口中单击&#x200B;**[!UICONTROL 提交]**。
1. 再次单击库的下拉列表（现在位于“已提交”列中），然后选择&#x200B;**[!UICONTROL Build for Staging]**。
1. 片刻后，库上的黄色指示灯变为绿色，表示已成功构建。
1. 再次单击库的下拉列表，然后选择&#x200B;**[!UICONTROL 批准以供发布]**。
1. 再次单击库的下拉列表（现在位于[!UICONTROL Approved]列中），然后选择&#x200B;**[!UICONTROL Build and Publish to Production]**。
1. 转到“环境”选项卡，单击&#x200B;**[!UICONTROL 生产环境]**。
1. 复制生产安装代码块并将其提供给网站所有者。请求他们在网站的生产环境中实施此代码。

## 验证您的生产实施

确认您会在网站的在线版本上看到数据，然后开始正式收集 Adobe Analytics 的数据。

1. 向网站所有者确认他们已将标记代码推送到生产环境后，请在 Chrome 中导航到您网站的主页并打开 [!UICONTROL Adobe Experience Cloud Debugger]。
2. 如果一切运行正常，您应会在开发环境中看到与测试类似的数据。此时，您将可收集网站上的数据，并且可以立即开始使用 Adobe Analytics 进行报告。

## 故障诊断

**调试器中不显示任何数据。**

在您的网站上，打开浏览器的开发人员控制台（通常按 F12）。查看页面的源代码，确保符合以下情况：

* 控制台中没有 JavaScript 错误。与贵组织的网站所有者合作，确保解决了所有 JS 错误。
* 正确实施了页眉代码：确保页眉代码位于 `<head>` 标记内部，并且文件存在。
* AppMeasurement 库存在：直接导航到 JS 源，以确保 JS 文件包含代码。如果不包含，请确保创建了每个环境，并且库已发布到各自对应的环境。
* 干扰扩展：一些扩展，如广告拦截器，可以阻止触发图像请求。禁用任何可能阻止数据发送到 Adobe 的扩展。

## 后续步骤

现在，基本实施已设置，您在组织中的角色会影响您所要了解详情的路径：

* [创建解决方案设计文档](../prepare/solution-design.md)：制定有关如何使用自定义变量的计划，然后将其包含在实施中
* [开始使用 Analysis Workspace](/help/analyze/analysis-workspace/home.md)：通过使用该工具的主要功能，深入研究 Adobe Analytics。
