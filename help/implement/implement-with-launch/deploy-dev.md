---
title: 将 Adobe Analytics 部署到开发环境
seo-title: 将 Adobe Analytics 部署到开发环境
description: 了解如何使用 Adobe Experience Platform Launch 将 Adobe Analytics 部署到开发环境。
seo-description: 了解如何使用 Adobe Experience Platform Launch 将 Adobe Analytics 部署到开发环境。
translation-type: ht
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 将 Analytics 实施部署到开发环境

在 Launch 中创建并配置属性后，即可在您的网站上部署库并实施代码。

## 先决条件

[在 Launch 中为 Adobe Analytics 创建和配置属性](create-analytics-property.md)：访问该工具并为 Analytics 实施创建空间。

## 创建适配器和环境

Launch 在部署代码方面提供了许多组织工作流程。请按照以下步骤为 Analytics 实施创建所需的最少组件。作为 Launch 管理员，您可以在组织内部建立用于部署 Adobe 解决方案的合适工作流程。

1. 转到 [Adobe Experience Platform Launch](https://launch.adobe.com)，并在出现提示时登录。
2. 单击要在网站上实施的 Launch 属性。
3. 单击“适配器”选项卡，然后单击“添加适配器”。
4. 将其命名为“Akamai”，然后在类型下拉列表中选择“Akamai”。单击“保存”。
5. 转到“环境”选项卡，然后单击“创建新环境”。
6. 选择“开发”，将其命名为“开发环境”，然后从下拉菜单中选择“Akamai”适配器。单击“创建”，然后单击“关闭”。
7. 单击“添加环境”，选择“测试”，将其命名为“测试环境”，然后选择“Akamai”适配器。单击“创建”，然后单击“关闭”。
8. 再次单击“添加环境”，选择“生产”，将其命名为“生产环境”，然后选择“Akamai”适配器。单击“创建”，然后单击“关闭”。

## 构建开发库

尽管到目前为止您已进行所有更改和配置，但实际上尚未发布任何代码。创建一个库（大致意思为更改集合）以在您的网站上用于发布代码。

1. 转到 [Adobe Experience Platform Launch](https://launch.adobe.com)，并在出现提示时登录。
2. 单击要在网站上实施的 Launch 属性。
3. 单击“发布”选项卡，然后单击“添加新库”。
4. 将该库命名为“初始更改”，然后选择开发环境。
5. 单击“添加所有更改的资源”，此时将自动列出 Adobe Analytics、Identity Service 和核心。
6. 单击“保存”。
7. 返回发布工作流程屏幕，单击新库旁边的下拉菜单，然后单击“为开发构建”。几秒钟后，如果库上的黄点变为绿色，则表示已成功生成该内部版本。
8. 转到“环境”选项卡，然后单击开发环境。
9. 在“安装 Launch”下，复制代码块并将其提供给贵组织的网站所有者。

## 在网站的开发环境中安装 Launch

如果您控制网站的代码，请在网站每个页面上的相应位置（在 `<head>` 标记内和靠近 `</body>` 标记的正上方）实施这两个代码块。此代码通常放置在网站的主要模板中。仅包含实施代码的空白页面如下所示：

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

失败的一个常见原因是其他要推送到测试或生产的库中已存在这些元素。最初创建库时，请确保仅将已更改的资源添加到库。

## 文档和其他资源

- [Launch 快速入门](https://docs.adobelaunch.com/getting-started)：了解 Launch 的基本工作流程
- [Launch 管理](https://docs.adobelaunch.com/administration)：了解有关适配器和环境的更多信息

## 后续步骤

[验证 Analytics 实施并发布到生产环境](validate-publish-prod.md)：开始从 Adobe Analytics 中获取值。
