---
description: 在Adobe Analytics中部署Kampyle数据连接器。
title: 部署集成
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
exl-id: ac8e1f30-cefe-448a-bec6-cda58ee51025
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 47%

---

# 部署集成{#deploying-the-integration}

部署此集成的流程非常简单，包括完成Adobe集成向导、部署插件代码(JavaScript)和验证集成。

## 完成 Adobe 集成向导{#complete-the-adobe-integration-wizard}

要激活集成，请在Data Connectors界面中完成配置向导。

1. 登录 [!DNL Adobe Experience Cloud].
1. 单击 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 数据连接器]**。
1. 启动 Kampyle 集成向导。
1. 选择所需的报表包并提供集成的名称。
1. 配置以下项目：
   1. **[!UICONTROL 电子邮件地址]**:主要联系人的电子邮件地址。
   1. **[!UICONTROL 描述]** （可选）：此集成设置的描述。
   1. **[!UICONTROL Kampyle密钥]**:在Kampyle应用程序的反馈表单 ****  >反馈表单自定 **[!UICONTROL 义]**&#x200B;下找到此键。
   1. **[!UICONTROL 跟踪服务器]**:用于跟踪Adobe Analytics数据的跟踪服务器值。
   1. **[!UICONTROL 安全跟踪服务器]**:如果安全/https流量的跟踪服务器不同，请在此处提供该设置。
1. 配置以下&#x200B;**[!UICONTROL 变量映射]**&#x200B;项目：
   1. **[!UICONTROL Kampyle反馈ID]**:从报表包中选择一个可用的eVar变量
   1. **[!UICONTROL 反馈等级]**:从报表包中选择一个可用的成功事件（类型“计数器”）。
   1. **[!UICONTROL 反馈项目]**:从报表包中选择一个可用的成功事件（类型“计数器”）。
   1. **[!UICONTROL 带等级的反馈]**:从报表包中选择一个可用的成功事件（类型“计数器”）。
1. 选中自动为您创建 Kampyle 集成功能板的框（推荐）。
1. 查看所有配置项目并单击&#x200B;**[!UICONTROL 立即激活]**。

## 部署集成配置对象{#deploy-the-integration-configuration-object}

完成集成向导后，将集成配置对象部署到您的Web资产。 在很多情况下，部署集成配置对象最简单的方法是，将其包含在 Adobe Analytics 部署代码中。

>[!NOTE]
>
>如果在Adobe Experience Platform中使用标记，则可以通过该工具轻松添加集成配置对象。

1. 导航到集成的&#x200B;**[!UICONTROL 资源]** > **[!UICONTROL 支持]**&#x200B;选项卡。
2. 下载并保存 **[!UICONTROL Kampyle 集成代码 (JS)]** 资源。该代码与以下内容类似：

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

3. 使用下列方法之一部署代码：

   * 在Adobe Experience Platform中使用标记。
   * 将代码交付到维护Adobe Analytics部署的组织资源。

## 验证集成{#verify-the-integration}

通过完成几项检查，验证集成是否成功传输数据。

### 集成活动日志 {#section-0472df9180db4f218db5f6040cab07af}

通过导航到&#x200B;**[!UICONTROL 支持]** > **[!UICONTROL 集成活动日志]**，查看 Adobe Experience Cloud 中的 Kampyle 集成设置。在&#x200B;**[!UICONTROL 数据输入]**&#x200B;选项卡下，您应该会看到表明分类数据已成功导入的条目。

>[!NOTE]
>
>日志条目通常会在成功部署后的24小时内显示。

![集成活动日志](assets/integration_activity_log.png)

### Adobe 报表数据 {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

通过在 Adobe Analytics 的相应菜单结构中导航到 Kampyle 报表，查看 Kampyle 反馈报表。

>[!NOTE]
>
> 如果集成反馈表单主动接收提交，则报表数据应会在成功部署后的 24-48 小时内显示。

![Adobe报表数据](assets/adobe_reporting_data.png)
