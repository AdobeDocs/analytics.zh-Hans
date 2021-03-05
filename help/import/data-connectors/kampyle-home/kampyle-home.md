---
description: 将Kampyle数据连接器与Adobe Analytics结合使用。
title: 适用于 Adobe Analytics 的 Kampyle Data Connector
uuid: f7733c81-93f5-4c50-b83a-721a6fbd4e8e
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 93%

---


# 适用于 Adobe Analytics 的 Kampyle Data Connector{#kampyle-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>我们将于2021年8月1日终止Adobe Data Connector技术。 [了解更多...](/help/import/data-connectors/data-connectors-eol.md)

适用于 Adobe Analytics 的 Kampyle Data Connector 将 Kampyle 的集成式反馈系统与 Adobe Analytics® 的行为报表整合在一起，为贵组织提供强大的分析和优化契机。

在线营销人员日益认识到客户反馈与品牌建立和提升业务成果的相关性。适用于 Adobe Analytics® 的 Kampyle Data Connector 将访客反馈量度和维度添加到了 Adobe Analytics 中。它让您能够根据访客的态度和意见来分析访客行为。这有助于您根据反馈进行优化并提高转化率。

## 集成先决条件{#integration-prerequisites}

激活 Data Connector 之前需要考虑的先决条件。

### Adobe 客户先决条件：{#section-d9c2e266931249e596de5f4406b5b6f0}

* 您必须是 Adobe Analytics 的当前客户。
* 您必须是管理员用户。
* 您的报表包中必须具有 1 个已启用的可用 eVar 变量。
* 您的报表包中必须具有 3 个已启用的可用自定义事件（类型：计数器）。

### Kampyle 客户先决条件：{#section-4bbbca50e74d4f218414ae0cc535b8e9}

* 您必须是 Kampyle 网站的当前客户。
* 您必须是 Adobe Experience Cloud 管理员用户，且有权启用 Data Connectors。
* 您必须能够从 Kampyle 反馈表单管理 UI 中检索 Kampyle 私钥。

## 检索 Kampyle 私钥{#retrieve-the-kampyle-private-key}

在 Kampyle 界面中检索密钥的步骤。

1. 登录您的 Kampyle 帐户，网址为 [https://www.kampyle.com/login](https://www.kampyle.com/login)。
1. 在左侧导航中，转到&#x200B;**[!UICONTROL 反馈表单]** > **[!UICONTROL 反馈表单自定义]**。

   ![](assets/retrieve_key1.png)

1. 在主内容窗格的下面部分找到所列的私钥。

   ![](assets/retrieve_key2.png)
