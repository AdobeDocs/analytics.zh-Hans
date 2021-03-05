---
description: 在Adobe Analytics中部署Kampyle数据连接器。
title: 部署集成
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 46%

---


# 部署集成{#deploying-the-integration}

部署此集成过程很简单，包括完成Adobe集成向导、部署插件代码(JavaScript)和验证集成。

## 完成 Adobe 集成向导{#complete-the-adobe-integration-wizard}

要激活集成，请在数据连接器界面中完成配置向导。

1. 登录 Adobe Experience Cloud。
1. 导航到&#x200B;**[!UICONTROL 数据连接器]**。
1. 启动 Kampyle 集成向导。
1. 选择所需的报表包并提供集成的名称。
1. 配置以下项目：
   1. **[!UICONTROL 电子邮件地址]**:主要联系人的电子邮件地址。
   1. **[!UICONTROL 说明]** （可选）：此集成设置的说明。
   1. **[!UICONTROL 坎皮尔]**:在Kampyle应用程序中的反馈表单> **[!UICONTROL 反馈表单自]** 定 **[!UICONTROL 义下找到此键]**。
   1. **[!UICONTROL 跟踪服务器]**:用于跟踪Adobe Analytics数据的跟踪服务器值。
   1. **[!UICONTROL 跟踪服务器安全]**:如果您的跟踪服务器在安全/https通信方面不同，请在此处提供该设置。
1. 配置以下&#x200B;**[!UICONTROL 变量映射]**&#x200B;项目：
   1. **[!UICONTROL 坎皮尔反馈ID]**:从报表包中选择一个可用的eVar变量
   1. **[!UICONTROL 反馈级别]**:从报表包中选择可用的成功事件（键入“计数器”）。
   1. **[!UICONTROL 反馈项]**:从报表包中选择可用的成功事件（键入“计数器”）。
   1. **[!UICONTROL 评级反馈]**:从报表包中选择可用的成功事件（键入“计数器”）。
1. 选中自动为您创建 Kampyle 集成功能板的框（推荐）。
1. 查看所有配置项目并单击&#x200B;**[!UICONTROL 立即激活]**。

## 部署集成配置对象{#deploy-the-integration-configuration-object}

完成集成向导后，将集成配置对象部署到您的Web属性。 在很多情况下，部署集成配置对象最简单的方法是，将其包含在 Adobe Analytics 部署代码中。

>[!NOTE]
>
>如果您使用Adobe Experience Platform Launch，则可以通过该工具轻松添加集成配置对象。

1. 导航到集成的&#x200B;**[!UICONTROL 资源]** > **[!UICONTROL 支持]**&#x200B;选项卡。
1. 下载并保存 **[!UICONTROL Kampyle 集成代码 (JS)]** 资源。该代码与以下内容类似：

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. 使用下列方法之一部署代码：

   * 使用Adobe Experience Platform Launch。
   * 将代码交付到维护Adobe Analytics部署的组织资源。

## 验证集成{#verify-the-integration}

通过完成两次检查验证集成是否成功传输数据。

### 集成活动日志 {#section-0472df9180db4f218db5f6040cab07af}

通过导航到&#x200B;**[!UICONTROL 支持]** > **[!UICONTROL 集成活动日志]**，查看 Adobe Experience Cloud 中的 Kampyle 集成设置。在&#x200B;**[!UICONTROL 数据输入]**&#x200B;选项卡下，您应该会看到表明分类数据已成功导入的条目。

>[!NOTE]
>
>日志条目通常在成功部署后的24小时内显示。

![集成活动日志](assets/integration_activity_log.png)

### Adobe 报表数据 {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

通过在 Adobe Analytics 的相应菜单结构中导航到 Kampyle 报表，查看 Kampyle 反馈报表。

>[!NOTE]
>
> 如果集成反馈表单主动接收提交，则报表数据应会在成功部署后的 24-48 小时内显示。

![Adobe报告数据](assets/adobe_reporting_data.png)
