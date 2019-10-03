---
description: 'null'
seo-description: 'null'
seo-title: 部署集成
solution: Analytics
title: 部署集成
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: f326b29bb73fd6e8630957c43dfd89f47b711986

---


# 部署集成{#deploying-the-integration}

部署此集成过程很简单，包括完成Adobe集成向导、部署插件代码(javascript)和验证集成。

## 完成Adobe集成向导{#complete-the-adobe-integration-wizard}

要激活集成，必须在数据连接器界面中完成配置向导。

1. 登录到 Adobe Experience Cloud.
1. 导航到 **[!UICONTROL 数据连接器]** （以前称为Genesis）。
1. Launch the Kampyle integration wizard.
1. Select the desired report suite and provide a name for the integration.
1. 配置以下项目：
   1. **[!UICONTROL Email address]** - the primary contact's email address.
   1. **[!UICONTROL Description - (optional) description for this integration setup.]**
   1. **[!UICONTROL Kampyle Key - Find this key in the Kampyle application under Feedback Form &gt; Feedback Form Customization.]**********
   1. **[!UICONTROL Tracking Server - the tracking server (domain) setting that you use to track Adobe Analytics data.]**
   1. **[!UICONTROL 跟踪服务器安全]** -如果跟踪服务器与安全/https通信不同，请在此处提供该设置。
1. Configure the following Variable Mappings items:****
   1. **[!UICONTROL Kampyle反馈ID]** —— 从报表包中选择一个可用的eVar变量
   1. **[!UICONTROL 反馈级别]** -从您的报告套件中选择可用的成功事件（键入“计数器”）。
   1. **[!UICONTROL 反馈项]** -从报告包中选择可用的成功事件（键入“计数器”）。
   1. **[!UICONTROL 评级反馈]** -从报表包中选择一个可用的成功事件（键入“计数器”）。
1. 选中该框，自动为您创建Kampyle集成控制面板（建议）。
1. 查看所有配置项，然后单击“ **[!UICONTROL 立即激活]**”。

## 部署集成配置对象{#deploy-the-integration-configuration-object}

完成集成向导后，必须将集成配置对象部署到Web属性。

在很多情况下，部署集成配置对象的最简单方法是将其包含在Adobe Analytics部署代码中。

> [!NOTE] 如果您使用Adobe TagManager或动态标签管理来部署Adobe Analytics，则可以通过该工具轻松添加集成配置对象。

1. 导航到集 **[!UICONTROL 成的]** Resources &gt; **[!UICONTROL Support]** （资源&gt;支持）选项卡。
1. 下载并保存 **[!UICONTROL Kampyle集成代码(JS)资源]** 。 代码类似于：

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. 使用下列方法之一部署代码：
|您 **可以使用Adobe TagManager或动态标签管理。** |使用标签管理界面添加代码。 |
|---|---|
| In all other cases | Deliver the code to the organizational resource that is responsible for updating your Adobe Analytics deployment code.  |****

## Verify the Integration{#verify-the-integration}

Validate that the integration is successfully transferring data by completing a couple of checks.

### 集成活动日志 {#section-0472df9180db4f218db5f6040cab07af}

View your Kampyle integration setup within the Adobe Experience Cloud by navigating to Support &gt; Integration Activity Log. ******** Under the Data In tab, you should see entries stating that classification data was successfully imported.****

> [!NOTE] Log entries should appear within 24 hours of successful deployment.

![](assets/integration_activity_log.png)

### Adobe报告数据 {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

View your Kampyle feedback reports with Adobe Analytics by navigating to the Kampyle reporting within the appropriate menu structure.

> [!NOTE] Reporting data should appear within 24-48 hours of successful deployment, assuming that the integrated feedback form(s) is actively receiving submissions.

![](assets/adobe_reporting_data.png)

