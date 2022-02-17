---
title: 如何在 Advertising Analytics 中设置广告帐户
description: 让您创建新的广告帐户并将多个帐户映射到多个报表包。
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 91%

---

# 设置广告帐户

Adobe Analytics 管理员可以创建新的广告帐户，并将多个帐户映射到多个报表包（一对一、一对多、多对多）。

管理员还可以[为非管理员授予访问权限](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369)，以设置广告帐户。

![](assets/aa_accounts.png)

1. 在 Adobe Analytics 中，导航到&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 广告帐户]**。
1. （仅限首次使用）接受最终用户许可协议的条款。
1. 单击 **[!UICONTROL + 添加]**。
1. 显示[!UICONTROL 新搜索引擎帐户]对话框：

   ![](assets/aa_new_se_account.png)

1. 按照以下说明填写&#x200B;**[!UICONTROL 搜索引擎设置]**：

   | 设置 | 描述 |
   | --- | --- |
   | 类型 | 您有 2 个选项：Google AdWords 和 Microsoft Bing Ads。注意：Microsoft Bing 于 2019 年 3 月 31 日收购了 Yahoo Gemini。因此，现已不再提供 Yahoo Gemini 广告帐户选项。 |
   | 帐户名称 | 您可以选择将此帐户名称设置为适合您的任意名称。这是将显示在 UI 中的帐户的友好名称。 |
   | OAuth 令牌 | **注意：** OAuth 是一种针对访问权限委派的开放标准，通常用于授予网站或应用程序访问其他网站上的信息的权限，且无需提供密码。您会注意到您将被路由到一个第三方URL(efrontier.com)。 Adobe 使用 efrontier 为所有三个搜索引擎启用 OAuth 身份验证过程。如果您使用Internet Explorer 11（或更早版本），则无法为三个搜索引擎中的任何一个成功检索Oauth令牌。 请改用其他 Web 浏览器。<p>单击&#x200B;**[!UICONTROL 检索令牌]**&#x200B;可启动 OAuth2 身份验证过程。系统将要求您使用您的凭据登录到Google/Bing搜索帐户。 根据您选择的搜索引擎，过程会略有不同： <ul><li>Google Adwords:提供Google帐户ID</li><li>Microsoft Bing：提供 Bing 帐户 ID 和 Bing 客户 ID。</li></ul>请参考[查找帐户 ID](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) 以获取有关这些 ID 的信息。成功登录后， **[!UICONTROL OAuth令牌]** 字段显示 **[!UICONTROL 已检索]**. |

1. 在&#x200B;**[!UICONTROL 跟踪]**&#x200B;部分中，您提供的是有关您的 Adobe Analytics 实施如何对搜索引擎数据进行跟踪的信息。这是向 Adobe Analytics 数据适当增加搜索引擎数据的必要步骤。按照以下说明填写&#x200B;**[!UICONTROL 跟踪设置]**：

   | 设置 | 描述 |
   | --- | --- |
   | 类型 | <ul><li>**自动**：让 Advertising Cloud 引擎自行决定如何将跟踪参数附加到搜索引擎的跟踪模板/目标 URL。这种方法最简单，但可能不会生成最佳的集成数据集。<br>**重要信息：**&#x200B;要在“自动模式”中配置搜索引擎帐户，您需要负责执行以下操作：<br>将“s_kwcid”参数和值添加到要添加的帐户中的帐户跟踪模板或登陆页 URL。该参数和值将插入到 URL 的末尾。因此，如果您的 Web 服务器要求在 URL 末尾使用特定的键值对，或者需要更新以支持 URL 中的任何新键值对，则可能需要执行其他操作。**注意：**&#x200B;了解关于是否应将该参数添加到您的[内容安全策略](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html?lang=zh-Hans)的更多信息。<br>此外，还可以将关键字作为“s_kwcid”值的一部分插入到登陆 URL 中，所以，如果它们包含特殊字符或符号，请确认您的 Web 服务器可以支持这些字符（例如，常见特殊字符“+”，用于“修改广泛匹配”关键字）。</li><li>**手动**：让您管理如何将跟踪参数添加到搜索引擎的跟踪模板/目标 URL。[请参考每个搜索引擎的手动跟踪示例](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md)。</li></ul> |

1. 在&#x200B;**[!UICONTROL 映射]**&#x200B;部分，您可以选择链接到此搜索引擎帐户的报表包。您必须先提供至少一个报表包，然后才能保存广告帐户。您可以将多个帐户映射到多个报表包（一对一、一对多、多对多）。请注意，AMO 从搜索引擎提取的数据只是简单地复制到所有映射的报表包中，因此不会出现拆分数据的情况。

   >[!IMPORTANT]
   >
   >只有已映射到 Experience Cloud 组织的报表包才可供选择。如果在列出的报表包中未看到您的报表包，请参阅 [Advertising Analytics 疑难解答](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md)。

   对于&#x200B;**[!UICONTROL 映射设置]**，请遵循以下说明：

   | 设置 | 描述 |
   | --- | --- |
   | 报表包映射 | 报表包映射可确定链接到此搜索引擎帐户的报表包。换句话说，它可确定搜索引擎数据会发送到哪些报表包。 |


1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 保存之后，会显示免责声明列出一系列注意事项。您需要确认您已经阅读并理解这份协议。单击复选框，然后单击&#x200B;**[!UICONTROL 确定]**。

   现在，您会进入广告帐户[管理 UI](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)，您新创建的帐户应已列于此处。

>[!NOTE]
>
>您可能需要至少等待 24 小时，搜索引擎数据才会开始填充到您的 Analytics 报表中。
