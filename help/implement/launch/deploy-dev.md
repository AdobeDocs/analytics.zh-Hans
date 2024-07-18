---
title: 将 Adobe Analytics 部署到开发环境
description: 了解如何使用标记将 Adobe Analytics 部署到开发环境。
feature: Tags
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 92%

---

# 将 Analytics 实施部署到开发环境

创建并配置标记属性后，便可在网站上部署库并实施代码。

## 先决条件

[为 Adobe Analytics 创建和配置标记属性](create-analytics-property.md)：访问该工具并为 Analytics 实施创建空间。

## 创建适配器和环境

标记在部署代码方面提供了许多组织工作流程。请按照以下步骤为 Analytics 实施创建所需的最少组件。作为标记管理员，您可以在组织内部建立用于部署 Adobe 解决方案的合适工作流程。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击要在网站上实施的标记属性。
3. 单击 **[!UICONTROL 主机]**，然后单击 **[!UICONTROL 添加主机]**。
4. 将其命名为`"Adobe managed"`，并在类型下拉列表中选择&#x200B;**[!UICONTROL 由Adobe管理]**。 单击“保存”。
5. 导航至&#x200B;**[!UICONTROL 环境]**，然后单击&#x200B;**[!UICONTROL 添加环境]**。
6. 选择&#x200B;**[!UICONTROL 开发]**，将其命名为`"Dev Environment"`，然后从下拉列表中选择Adobe托管主机。 单击&#x200B;**[!UICONTROL 保存]**。
7. 此时会出现一个模式窗口，显示 Web 安装说明。稍后我们将返回此窗口；现在，请单击&#x200B;**[!UICONTROL 关闭]**。
8. 单击&#x200B;**[!UICONTROL 添加环境]**，选择&#x200B;**[!UICONTROL 暂存]**，将其命名为`"Staging Environment"`，然后选择由 Adobe 管理的主机。单击&#x200B;**[!UICONTROL 创建]**，然后关闭安装说明模式窗口。
9. 再次单击&#x200B;**[!UICONTROL 添加环境]**，选择&#x200B;**[!UICONTROL 生产]**，将其命名为`"Production Environment"`，然后选择由 Adobe 管理的主机。单击&#x200B;**[!UICONTROL 创建]**，然后关闭安装说明模式窗口。

## 构建开发库

尽管到目前为止您已进行所有更改和配置，但实际上尚未发布任何代码。创建一个库（大致意思为更改集合）以在您的网站上用于发布代码。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击要在网站上实施的标记属性。
3. 单击 **[!UICONTROL 发布流]** 选项卡，然后单击 **[!UICONTROL 添加库]**。有关此页面的更多信息，请参阅标记文档中的[发布概述](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html)。
4. 为此库命名`'Initial changes'`，并选择您的开发环境。
5. 单击&#x200B;**[!UICONTROL 添加所有更改的资源]**，自动列出 Adobe Analytics、标识服务和核心。
6. 单击&#x200B;**[!UICONTROL 保存]**。
7. 返回发布工作流程屏幕，单击新库旁边的下拉列表，然后单击&#x200B;**[!UICONTROL 为开发构建]**。 几秒钟后，库上的黄点变为绿色，表示构建成功。
8. 导航到&#x200B;**[!UICONTROL 环境]**，然后单击开发环境右侧的安装图标。此操作将再次打开“Web 安装说明”模式窗口。
9. 复制代码块并将其提供给贵组织的网站所有者。

## 在网站的开发环境中安装标记

如果是您控制网站的代码，请在各自位置执行每个代码块：

* 主标记属于`<head>`网站上的标记。
* 如果选择同步加载标记，您还必须在网站上的结束`</body>`标记下方添加第二个代码块。通过在 Web 安装说明中切换&#x200B;**[!UICONTROL 异步加载库]**&#x200B;选项，您可以选择同步加载库标记。

标记代码通常放置在网站的主要模板中。仅包含实施代码的空白页面如下所示：

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
