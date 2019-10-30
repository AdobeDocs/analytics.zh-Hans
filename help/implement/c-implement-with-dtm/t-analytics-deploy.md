---
description: 创建 Adobe Analytics 工具以便使用 Dynamic Tag Management 进行部署。此过程描述手动（旧版）实施方法。
keywords: Dynamic Tag Management
seo-description: 创建 Adobe Analytics 工具以便使用 Dynamic Tag Management 进行部署。此过程描述手动（旧版）实施方法。
seo-title: 手动实施 Adobe Analytics（旧版）
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 手动实施 Adobe Analytics（旧版）
uuid: d3ad2035-393d-4a77-81f6-e749ee717c09
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 手动实施 Adobe Analytics（旧版）

创建 Adobe Analytics 工具以便使用 [!UICONTROL Dynamic Tag Management] 进行部署。此过程描述手动（旧版）实施方法。

有关自动实施管理的信息，请参阅 [添加 Adobe Analytics 工具](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

如果您要将手动配置更改为自动配置，请编辑工具并单击&#x200B;**[!UICONTROL 启用自动配置]**。

1. 下载 Analytics 测量代码：
   1. 在 Analytics 中，单击&#x200B;**[!UICONTROL 管理员]** &gt; **[!UICONTROL 代码管理器]**。
   1. 单击 **[!UICONTROL JavaScript（新）]**&#x200B;以通过本地方式下载代码。
1. 在 [!UICONTROL Dynamic Tag Management] 中，[创建 Web 属性](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)。

   ![](assets/dtm-property.png)

   在创建 Web 属性之后，便可以在“[!UICONTROL 功能板]”的“[!UICONTROL Web 属性]”选项卡中对其进行编辑。不需要激活 Web 属性。.

1. 将 Analytics 工具添加到该属性：
   1. 在 **[!UICONTROL Web 属性]**&#x200B;选项卡中，单击该属性。
   1. 在&#x200B;**[!UICONTROL 概述]**&#x200B;选项卡中，单击&#x200B;**[!UICONTROL 添加工具]**。
   1. 从&#x200B;**[!UICONTROL 工具类型]**&#x200B;菜单中，选择 **[!UICONTROL Adobe Analytics]**。

      ![](assets/dtm-add-analytics-tool.png)

   1. 配置以下字段：

      | 元素 | 描述 |
      |---|---|
      | 工具类型 | Experience Cloud 解决方案，例如 Analytics、Target、Social 等。 |
      | 工具名称 | 此工具的名称。此名称显示在“[!UICONTROL 概述]”选项卡中的“[!UICONTROL 已安装工具]”下方。 |
      | 生产帐户 ID | 用于数据收集的生产帐户号码。动态标签管理会在生产和暂存环境中自动安装正确的帐户。 |
      | 暂存帐户 ID | 在开发或测试环境中使用的帐户号码。暂存帐户可将您的测试数据与生产数据分隔开。 |

1. 单击&#x200B;**[!UICONTROL 创建工具]**。

   已安装的工具显示在“[!UICONTROL 概述]”选项卡中。

1. 要配置代码，请单击&#x200B;**[!UICONTROL 设置]**![](assets/settings_gear.png)。

   至少应单击 **[!UICONTROL Cookie]并配置您的跟踪服务器和 SSL 跟踪服务器。**

1. 单击&#x200B;**[!UICONTROL 常规]**，然后[插入核心 AppMeasurement 代码](../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658)。
1. 定义[页面加载规则](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB)以收集 [!DNL Analytics] 数据。

   您当前已准备好定义规则来收集分析数据。您可能需要首先定义几个数据元素。数据元素允许您从可用于配置规则的页面中提取数据。若要开始，您可以定义一个没有任何条件的页面加载规则，以收集每个页面中的 [!DNL Analytics] 数据。
1. [在“嵌入”选项卡中添加页眉和页脚代码](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5)。

   为进行暂存，您可以保留默认的 Amazon 托管选项。您可以在生产转出之前根据需要更改它。
1. （可选）单击“选项”选项卡中的&#x200B;**[!UICONTROL 设置]**![](assets/settings_gear.png)，然后配置 Adobe Analytics 代码。

   >[!NOTE]
   >
   >[!UICONTROL Adobe Analytics] 页面中的设置（“常规”、“Cookie”等）会覆盖 `s_code` 中的设置。如果这些设置存在于您的 `s_code` 中，则无需在此重复设置它们。

