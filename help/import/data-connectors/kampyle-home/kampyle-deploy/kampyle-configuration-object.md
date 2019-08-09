---
description: 完成集成向导后，您必须将集成配置对象部署到Web属性。
seo-description: 完成集成向导后，您必须将集成配置对象部署到Web属性。
seo-title: 部署集成配置对象
solution: Analytics
title: 部署集成配置对象
uuid: e951c864-2914-4324-9f03-5069d4f75d99
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 部署集成配置对象{#deploy-the-integration-configuration-object}

完成集成向导后，您必须将集成配置对象部署到Web属性。

在许多情况下，部署集成配置对象最简单的方法是将它包含在您的Adobe Analytics部署代码中。

>[!NOTE]
>
>如果使用Adobe TagManager或Dynamic Tag Management部署Adobe Analytics，则可以通过该工具轻松添加集成配置对象。

1. 导航到集成的 **[!UICONTROL “资源]** ”&gt; **[!UICONTROL “支持]** ”选项卡。
1. 下载并保存 **[!UICONTROL Kampyle Integration Code(JS)]** 资源。代码类似于：

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. 使用以下方法之一部署代码：

       ||**您可以使用Adobe TagManager或动态标签管理。****||使用标签管理界面添加代码。||
    ||—||—||
    ||**在所有其他情况**||将代码交付到负责更新Adobe Analytics部署代码的组织资源。||
   
