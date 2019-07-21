---
title: 将Adobe Analytics部署到开发环境
seo-title: 将Adobe Analytics部署到开发环境
description: 了解如何使用Adobe Experience Platform Launch将Adobe Analytics部署到开发环境。
seo-description: 了解如何使用Adobe Experience Platform Launch将Adobe Analytics部署到开发环境。
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 验证开发实施并发布到生产

将Adobe Experience Platform Launch库推向生产之后，您的组织可以开始使用Adobe Analytics提取基本报表。

## 先决条件

[将Analytics实施部署到开发环境](deploy-dev.md)：要遵循本页，必须将Analytics实施发布到开发环境。

## 使用Experience Cloud调试器验证开发实施

Experience Cloud调试器是一个Chrome插件，它显示页面上显示的所有Experience Cloud标签。

1. Open [Chrome Web Browser](https://www.google.com/chrome/) and go to [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) on the Chrome Web Store to install the extension.
2. 导航到已实施启动项的开发网站。
3. 单击Chrome右上角的Adobe Experience Cloud调试器图标
4. 如果所有内容得到正确实施，您应在Adobe Analytics、Adobe Experience Platform Launch和Adobe Experience Cloud访问者ID服务中看到内容：

![调试器][assets/debugger.png]

## 将开发实施部署到stage/prod

验证数据后，您可以将实施推送到站点的Live版本。

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. 单击要在站点上实施的启动项属性。
3. 单击“发布”选项卡并在开发列中找到库。
4. 单击库中的下拉菜单，然后选择提交以进行批准。单击模态窗口上的“提交”。
5. 再次单击库的下拉菜单(现在“已提交”列中)，然后选择“为暂存构建”。
6. 几分钟后，库上的黄色浅色变为绿色，表示构建成功。
7. 再次单击库的下拉菜单，然后选择“批准发布”。
8. 再次单击库的下拉菜单(现在“已批准”列中)，然后选择“构建和发布到生产”。
9. 转到“环境”选项卡，单击“制作环境”。
10. 复制生产页眉+页脚代码，并将其提供给网站所有者。请求他们在站点的生产环境中实施此代码。

## 验证您的制作实施

确认您正在查看站点的实时版本数据，并开始为Adobe Analytics开始官方数据收集。

1. 从网站所有者确认已将启动代码推送到生产后，导航到Chrome中的网站主页，然后打开Adobe Experience Cloud调试器。
2. 如果一切正常，您应在开发环境中将类似数据看到测试。此时，您在您的网站上收集数据，现在可以开始使用Adobe Analytics报告。

## 故障诊断

**调试器中不显示数据。**

在站点上，打开浏览器的开发人员控制台(通常为F12)。查看页面的源代码并确保满足以下各项：

* 控制台中没有JavaScript错误。与贵组织的网站所有者合作，确保解决了所有JS错误。
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* AppMeasurement库存在：直接导航到JS源，以确保JS文件包含代码。如果没有，请确保创建每个环境，并将库发布到其各自的环境。
* 干扰插件：某些Chrome插件可阻止触发图像请求。禁用任何可能阻止数据发送到Adobe服务器的插件。

## 后续步骤

既然已经设置了基本实施，您在组织内的角色就会影响您想了解更多关于哪些路径：

* [创建解决方案设计文档](../prepare/solution-design.md)：计划如何使用自定义变量，然后将其包含在实施中
* [开始使用Analysis Workspace](../../analyze/analysis-workspace/home.md)：使用该工具的旗舰功能直接进入Adobe Analytics。
