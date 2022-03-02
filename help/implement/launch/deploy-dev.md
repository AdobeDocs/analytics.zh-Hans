---
title: 将 Adobe Analytics 部署到开发环境
description: 了解如何使用标记将 Adobe Analytics 部署到开发环境。
feature: Launch Implementation
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 47%

---

# 将 Analytics 实施部署到开发环境

创建并配置标记属性后，便可在网站上部署库并实施代码。

## 先决条件

[为 Adobe Analytics 创建和配置标记属性](create-analytics-property.md)：访问该工具并为 Analytics 实施创建空间。

## 创建适配器和环境

标记在部署代码方面提供了许多组织工作流程。请按照以下步骤为 Analytics 实施创建所需的最少组件。作为标记管理员，您可以在组织内部建立用于部署 Adobe 解决方案的合适工作流程。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
2. 单击要在网站上实施的标记属性。
3. 单击 **[!UICONTROL 主机]**，然后单击 **[!UICONTROL 添加主机]**.
4. 将其命名为 `"Adobe managed"`，然后选择 **[!UICONTROL 由Adobe]** 在类型下拉列表中。 单击“保存”。
5. 导航到 **[!UICONTROL 环境]**，然后单击 **[!UICONTROL 添加环境]**.
6. 选择 **[!UICONTROL 开发]**，命名 `"Dev Environment"`，然后从下拉菜单中选择Adobe托管主机。 单击&#x200B;**[!UICONTROL 保存]**。
7. 出现一个显示Web安装说明的模式窗口。 我们稍后会返回此窗口；单击 **[!UICONTROL 关闭]** 现在。
8. 单击 **[!UICONTROL 添加环境]**，选择 **[!UICONTROL 暂存]**，命名 `"Staging Environment"`，然后选择Adobe管理的主机。 单击 **[!UICONTROL 创建]**，然后关闭安装说明模式窗口。
9. 单击 **[!UICONTROL 添加环境]** 再次选择 **[!UICONTROL 生产]**，命名 `"Production Environment"`，然后选择Adobe管理的主机。 单击 **[!UICONTROL 创建]**，然后关闭安装说明模式窗口。

## 构建开发库

尽管到目前为止您已进行所有更改和配置，但实际上尚未发布任何代码。创建一个库（大致意思为更改集合）以在您的网站上用于发布代码。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
2. 单击要在网站上实施的标记属性。
3. 单击 **[!UICONTROL 发布流程]** ，然后单击 **[!UICONTROL 添加库]**. 请参阅 [发布概述](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) 有关此页面的更多信息，请参阅标记文档。
4. 将库命名为 `'Initial changes'`，然后选择开发环境。
5. 单击 **[!UICONTROL Add All Changed Resources]**，它会自动列出Adobe Analytics、Identity Service和核心。
6. 单击&#x200B;**[!UICONTROL 保存]**。
7. 返回发布工作流程屏幕，单击新库旁边的下拉菜单，然后单击 **[!UICONTROL 构建用于开发]**. 几秒钟后，库上的黄色圆点变为绿色，表示已成功生成。
8. 导航到 **[!UICONTROL 环境]**，然后单击开发环境右侧的安装图标。 此操作将再次显示Web安装说明模式窗口。
9. 复制代码块，并将其提供给贵组织的网站所有者。

## 在网站的开发环境中安装标记

如果您控制网站的代码，请在其各自的位置实施每个代码块：

* 主标记属于 `<head>` 标记。
* 如果选择同步加载标记，则还必须在紧靠结束 `</body>` 标记。 您可以选择通过切换 **[!UICONTROL 异步加载库]** 选项。

标记代码通常放置在网站的总模板中。 仅包含实施代码的空白页面如下所示：

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
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## 故障诊断

**尝试构建失败。**

失败的一个常见原因是其他要推送到测试或生产的库中已存在这些元素。最初创建库时，请确保仅将已更改的资源添加到库。

## 后续步骤

[验证 Analytics 实施并发布到生产环境](validate-publish-prod.md)：开始从 Adobe Analytics 中获取值。
