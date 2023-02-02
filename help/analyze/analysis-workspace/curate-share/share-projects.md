---
description: Workspace 中的项目共享和项目角色
keywords: Analysis Workspace 共享
title: 共享项目
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 58abc4a8410441a3c76c6737ace8e2c5ab5c1374
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 共享项目

您可以与组织中的现有Adobe Analytics用户或组共享项目。 当您按照本节所述共享项目时，您与共享的用户必须已经拥有Adobe Analytics帐户。

您可以与用户或组共享特定角色，也可以共享链接。

* [共享特定项目角色](#share-a-specific-project-role)

* [共享指向项目的链接](#share-a-link-to-a-project)

## 共享特定项目角色

在与组织中的用户和组共享特定项目角色时，请考虑以下事项：

* 项目角色(**[!UICONTROL 可以编辑]**, **[!UICONTROL 可以复制]**&#x200B;和 **[!UICONTROL 可以查看]**)与用户和特定项目ID关联。 项目角色与 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中管理的用户权限无关。

* 在 Adobe Analytics 中，组由 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中的产品配置文件定义。管理员可以共享到任何组，包括“全部”组。 除“全部”组外，非管理员可以共享到其所属的任何组。

* 处于多个角色的用户始终可以获得最高的体验。 如果将用户同时添加为个人和组的一部分，则可能会发生这种情况。 例如，如果为用户提供 **[!UICONTROL 可以编辑]** 个人角色和 **[!UICONTROL 可以查看]** 角色作为组的成员，他们将收到 **[!UICONTROL 可以编辑]** 项目体验。

* 置于 **[!UICONTROL 可以复制]** 或 **[!UICONTROL 可以查看]** 角色在打开项目时会获得这些有限的体验。 如有需要，管理员可以随时通过&#x200B;**[!UICONTROL 组件] > [!UICONTROL 项目]**&#x200B;将其角色提升为&#x200B;**[!UICONTROL 可以编辑]**。

要与组织中的用户或组共享特定项目角色，请执行以下操作：

1. 转到要共享的项目，然后单击 **[!UICONTROL 共享]** > **[!UICONTROL 共享项目]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
如果存在未保存的更改，系统会提示您先保存项目。

   ![](assets/share-proj-modal.png)

   有关如何同时共享多个项目的信息，请参阅 [在项目管理器中共享项目](#share-projects-in-the-project-manager).

1. 在提供的角色字段中添加收件人或收件人组：

   **可以编辑：** 收件人可以 **[!UICONTROL 保存]** 对项目的更改，并可以行使共有人的职能。 如果您希望与其他同事共同管理项目，则此角色很有用；这包括编辑、删除和修改共享项目的收件人列表。<br>注意：Analysis Workspace 当前不支持实时协作，因此建议在给定时间只让一个用户编辑项目。如果同时保存多个项目，则将保留最后一个版本。

   **可以复制：** 收件人可以 **[!UICONTROL 另存为]** 并有权访问左边栏。 在此角色中，项目交互不受限。如果您希望将项目共享给了解您组织数据以及如何使用Analysis Workspace的用户，但您不希望更改项目，则此角色非常有用。

   **可以查看：** 收件人不能 **[!UICONTROL 保存]** 或 **[!UICONTROL 另存为]** 和无权访问左边栏。 项目交互受到限制。如果您希望将项目共享给不太熟悉您组织的数据结构(通常是Analysis Workspace或Adobe Analytics)的用户，则此角色非常有用。 但是，您可能仍然希望这些用户在一个安全的环境中使用数据和信息分析。详细了解[“可以查看”角色提供的项目体验](/help/analyze/analysis-workspace/curate-share/view-only-projects.md)。

1. 选择在共享项目时是否启用以下选项：

   * **共享嵌入的项目组件：** 与所有收件人共享区段、计算量度和日期范围。 共享后，这些组件将显示在接收人工作区的“组件”下拉菜单中。此设置不持续 — 在共享时只执行一次性操作。

   * **设置为收件人的登陆页面：** 将此页面设置为收件人的登陆页面。 此设置不持续 — 在共享时只执行一次性操作。

1. 单击&#x200B;**[!UICONTROL 共享]**。您还可以单击&#x200B;**[!UICONTROL 策划和共享]**&#x200B;以自动应用项目策划。如果某个项目已共享，则将显示&#x200B;**[!UICONTROL 更新]**&#x200B;和&#x200B;**[!UICONTROL 策划和更新]**&#x200B;按钮。了解有关[项目策划](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hans)的更多信息。

## 共享指向项目的链接

在共享本节所述的链接时，请考虑以下事项：

* 使用链接的收件人需要先登录Adobe Analytics，然后才能访问项目。

* 如果收件人未分配角色，并收到 [链接](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=zh-Hans) 项目(**[!UICONTROL 共享] > [!UICONTROL 获取项目链接]**)，则默认情况下会为其分配角色。 管理员将获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;角色，非管理员将获得&#x200B;**[!UICONTROL 可以复制]**&#x200B;角色。

要与组织中的用户共享项目链接，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 共享]** > **[!UICONTROL 共享项目]**。
<!-- recommned changing "Share project" to "Share project internally" or something like that -->
如果存在未保存的更改，系统会提示您先保存项目。

   ![](assets/share-proj-modal.png)

1. 单击 **[!UICONTROL 复制链接]** 旁边 **[!UICONTROL 共享URL字段]**.

1. 与组织中的用户共享该链接。 例如，您可以将其粘贴到电子邮件中，粘贴到内部网站上，等等。

## 在项目管理器中共享项目 {#Manager}

还可以通过&#x200B;**[!UICONTROL 组件] > [!UICONTROL 项目]**&#x200B;来共享项目。可以按照上述相同步骤共享单个项目。如果选择共享多个项目，则会将收件人添加到每个项目的现有收件人列表中。

例如：

* 项目 A 共享给收件人 1、2、3
* 项目 B 共享给收件人 4、5、6

选择项目 A 和 B 后，将收件人 4 和 7 添加到共享列表。现在，每个项目的新共享列表为：

* 项目 A：1、2、3、4、7
* 项目 B：4、5、6、7

![](assets/mult-proj-sharing.png)

## 共享嵌入的组件

以下是一段关于该主题的视频：

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## 常见问题解答 {#FAQs}

| 问题 | 回答 |
| --- | --- |
| 如果两位编辑者同时保存一个项目，会发生什么情况？ | 将不会合并更改，并将保留最后保存的项目版本。Analysis Workspace 当前不支持实时协作。 |
| 作为管理员，我将获得什么样的项目体验？ | 具有&#x200B;**[!UICONTROL 可以复制]**&#x200B;或&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色的管理员在打开项目时将获得有限的项目体验。如有需要，管理员可以随时通过&#x200B;**[!UICONTROL 组件] > [!UICONTROL 项目]**&#x200B;将其角色提升为&#x200B;**[!UICONTROL 可以编辑]**。 |
| 如果一位收件人作为个人和作为小组成员分别有不同的角色，会发生什么情况？ | 如果收件人同时具有多个角色，他们将始终获得权限最高的角色体验。例如，如果作为个人收件人获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;角色，而作为小组成员获得&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色，则收件人将获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;项目体验。 |
| 如果收件人打开项目链接，他们会获得什么体验？ | 收件人将获得您在共享模式中为其分配的角色。如果收件人未分配到角色，并收到指向项目的链接（**[!UICONTROL 共享] > [!UICONTROL 获取项目链接]**），则他们会获得默认角色。管理员将获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;角色，非管理员将获得&#x200B;**[!UICONTROL 可以复制]**&#x200B;角色。 |
