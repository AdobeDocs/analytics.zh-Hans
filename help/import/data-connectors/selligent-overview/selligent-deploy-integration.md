---
description: 部署此集成的流程非常简单，只需 3 步。
title: 部署集成
uuid: c578bf26-34c2-44ea-8e60-2990273f8659
translation-type: ht
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# 部署集成{#deploying-the-integration}

部署此集成的流程非常简单，只需 3 步。

## 完成集成向导{#completing-the-integration-wizard}

要激活集成，必须在 Data Connectors 界面中完成 Selligent 集成向导。

1. 导航到 Adobe Experience Cloud 中的“Data Connectors”区域。

   ![](assets/selligent-data_connectors.png)

1. 在&#x200B;**[!UICONTROL 添加集成]**&#x200B;下，将 Selligent 插件拖放到 Adobe Experience Cloud 中。

   ![](assets/selligent-add_integration.png)

   此时将打开 Selligent Data Connector 集成。

1. **集成设置**：选择所需的报表包，并在&#x200B;**[!UICONTROL 集成设置]**&#x200B;下提供集成的名称。

1. 在&#x200B;**[!UICONTROL 自定义值]**&#x200B;下，填写所有与您的 Selligent 帐户相关的信息。

   ![](assets/selligent-general_settings.png)

1. **变量映射**：从下拉菜单中选择相应的保留 eVar 和事件：

   ![](assets/selligent-variables.png)

1. **数据设置**：除了 3 个自动提供的&#x200B;**[!UICONTROL 合作伙伴]**&#x200B;区段外，您还可以在&#x200B;**[!UICONTROL 您的区段]**&#x200B;下选择自己的区段。

1. 此集成可能需要将几个数据点下载到您的 Selligent 帐户。您可以在&#x200B;**[!UICONTROL 访问请求]**&#x200B;下选择授予此访问权限。
1. 在&#x200B;**[!UICONTROL 数据收集]**&#x200B;下，选择自动或手动解决方案（JavaScript 插件），以从登陆页面 URL 中收集查询字符串参数。如果选择自动解决方案，请为消息 ID 和收件人 ID 输入查询字符串参数（分别为 MID 和 RID）。有关 JavaScript 插件，请联系您的 Adobe 顾问。
1. **报表设置**：在&#x200B;**[!UICONTROL 功能板生成]**&#x200B;下，选中自动为您生成 Selligent 功能板的框。

   ![](assets/selligent-report_settings.png)

1. 查看集成摘要并单击&#x200B;**[!UICONTROL 激活]**。

## Selligent 中的配置{#configuration-within-selligent}

在 Adobe Analytics 中启用该集成后，Selligent 端便会启用自动配置。

系统已创建跟踪器，以跟踪每封电子邮件。如果您希望将其限制到特定域，请更新跟踪器配置。

我们强烈建议您将 URL 中 Adobe Analytics 的跟踪参数移到前面。这样可确保 Adobe 处理规则从登陆页面 URL 中提取参数。通过选中下面所示的复选框启用跟踪。

![](assets/selligent-tracker.png)

## 验证集成{#verifying-the-integration}

完成所有部署步骤后，您可以验证集成是否可成功传输数据。

需要几天时间才能开始交换数据。请确保在激活集成后联系 Selligent。

### 集成活动日志 {#section-927e270495db479fba9578915d9ae9c9}

导航到 Data Connectors 中的 Selligent 集成。在&#x200B;**[!UICONTROL 支持]**&#x200B;选项卡下，您应会看到诸如已成功导入量度数据和/或已成功导入分类数据等事件：

![](assets/selligent-verifying.png)

### 报表数据 {#section-ebd481a162324e66bd6dc8cb4b8d2424}

查看包含相应量度的 Selligent 消息报表。

1. 转到 Adobe Experience Cloud 下的 Report &amp; Analytics。
1. 选择适当的报表包。
1. 在&#x200B;**[!UICONTROL 自定义转化]**&#x200B;下，选择&#x200B;**[!UICONTROL 消息 ID 报表]**，然后选择&#x200B;**[!UICONTROL 消息 ID/消息名称]**。
