---
title: 将Adobe Analytics部署到开发环境
seo-title: 将Adobe Analytics部署到开发环境
description: 了解如何使用Adobe Experience Platform Launch将Adobe Analytics部署到开发环境。
seo-description: 了解如何使用Adobe Experience Platform Launch将Adobe Analytics部署到开发环境。
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 将Analytics实施部署到开发环境

在Launch中创建并配置了某个属性后，即可部署库并在您的站点上实现代码。

## 先决条件

[在Launch](create-analytics-property.md)中创建并配置Adobe Analytics的属性：访问工具并为Analytics实施创建空间。

## 创建适配器和环境

Launch在部署代码中支持许多组织工作流程。按照这些步骤，为Analytics实施创建最低必要的组件。作为Launch管理员，您可以在组织内工作，为部署Adobe解决方案建立正确的工作流程。

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. 单击要在站点上实施的启动项属性。
3. 单击适配器选项卡，然后单击添加适配器。
4. 将其命名为“Akamai”，然后在类型下拉列表中选择Akamai。单击“保存”。
5. 转到“环境”选项卡，然后单击“创建新环境”。
6. 选择“开发”，将其命名为“Dev Environment”，然后从下拉菜单中选择Akamai适配器。单击创建，然后单击关闭。
7. 单击“添加环境”，选择“暂存环境”，将其命名为“暂存环境”，然后选择Akamai适配器。单击创建，然后单击关闭。
8. 再次单击添加环境，选择“生产”，将其命名为“生产环境”，然后选择Akamai适配器。单击创建，然后单击关闭。

## 构建开发库

尽管目前已进行所有更改和配置，但实际上没有任何代码实际上已发布。创建库(粗略翻译为一系列更改)允许在站点上使用代码发布。

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. 单击要在站点上实施的启动项属性。
3. 单击发布选项卡，然后单击添加新库。
4. 将库“初始更改”命名为“初始更改”，然后选择开发环境。
5. 单击“添加所有更改的资源”，它会自动列出Adobe Analytics、Identity Service和核心。
6. 单击“保存”。
7. 返回发布工作流屏幕，单击新库旁边的下拉菜单，然后单击“构建为开发所用格式”。几秒钟后，库上的黄色圆点变为绿色，表示构建成功。
8. 转到“环境”选项卡，然后单击开发环境。
9. 在“安装启动项”下，复制代码块并将其提供给单位的网站所有者。

## 在网站开发环境上安装Launch

If you control your website's code, implement the two blocks of code in their respective locations (in the `<head>` tag and just above the closing `</body>` tag) on every page of your site. 此代码通常放置在站点的覆盖模板中。只有包含实施代码的空白页面才会如下所示：

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## 故障诊断

**尝试构建失败。**

一个常见原因是，其他库中已存在到暂存或生产的其他库中。最初创建库时，请确保只将更改的资源添加到库中。

## 文档和其他资源

- [Launch](https://docs.adobelaunch.com/getting-started)入门：了解Launch的基本工作流程
- [启动管理](https://docs.adobelaunch.com/administration)：进一步了解适配器和环境

## 后续步骤

[验证Analytics实施并发布到生产](validate-publish-prod.md)：从Adobe Analytics开始获得价值。
