---
description: Workspace 中的项目共享和项目角色
keywords: Analysis Workspace 共享
title: 共享项目
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: e3447bc278cfcf5553e46ceb298d9f4743f73328
workflow-type: tm+mt
source-wordcount: '1752'
ht-degree: 55%

---

# 共享项目

您可以与以下类型的人员共享Analysis Workspace项目：

* 您组织中有权访问Adobe Analytics的用户和组

   您可以共享“编辑”、“复制”或“查看”访问权限

* 您组织中无权访问Adobe Analytics的用户和组

   收件人具有只读访问权限

* 组织外的人员

   收件人具有只读访问权限

任意 [策划](curate.md) 在收件人打开项目时，会反映在共享之前应用的内容。

下面是项目共享的视频概述：

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## 与组织中的Analysis Workspace用户和组共享 {#Add}

您可以与组织中的现有Analysis Workspace用户或组共享项目。 在您按照本节所述共享项目时，您与共享的用户必须已经具有访问Adobe Analytics的权限。

您可以与用户或组共享特定角色，也可以共享链接。

* [共享特定的项目角色](#share-a-specific-project-role)

* [共享项目链接](#share-a-link-to-a-project)

## 共享特定的项目角色

与组织中的用户和组共享特定项目角色时，请考虑以下事项：

* 项目角色（**[!UICONTROL 可以编辑]**，**[!UICONTROL 可以复制]**，**[!UICONTROL 可以查看]**）与用户和特定项目 ID 相关联。 项目角色与 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中管理的用户权限无关。

* 在 Adobe Analytics 中，组由 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中的产品配置文件定义。管理员可以共享到任何组，包括“全部”组。 除“全部”组外，非管理员可以共享到其所属的任何组。

* 如果用户分配到了多个角色，将始终获得权限最高的角色体验。 如果同时将用户添加为个人和组成员，则可能发生这种情况。 例如，如果作为个人用户获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;角色，而作为小组成员获得&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色，则用户将获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;项目体验。

* 具有&#x200B;**[!UICONTROL 可以复制]**&#x200B;或&#x200B;**[!UICONTROL 可以查看]**&#x200B;角色的管理员在打开项目时会获得有限的项目体验。 如有需要，管理员可以随时通过“**[!UICONTROL 组件]”>“[!UICONTROL 项目]**”将其角色提升为&#x200B;**[!UICONTROL 可以编辑]**。

与组织中的用户或组共享特定项目角色：

1. 转到要共享的项目，然后单击 **[!UICONTROL 共享]** > **[!UICONTROL 与工作区用户共享]**.

如果存在未保存的更改，系统将提示您先保存项目。

   ![](assets/share-proj-modal.png)

   有关如何同时共享多个项目的信息，请参阅[在“项目”管理器中共享项目](#share-projects-in-the-project-manager)。

1. 在提供的角色字段之一中添加收件人或收件人组：

   **可以编辑：**&#x200B;收件人可以&#x200B;**[!UICONTROL 保存]**&#x200B;对项目的变更，并且可以行使共有人的权力。 如果您希望与其他同事共同管理项目，则此角色很有用；这包括编辑、删除和修改共享项目的收件人列表。<br>注意：Analysis Workspace 当前不支持实时协作，因此建议在给定时间只让一个用户编辑项目。如果同时保存多个项目，则将保留最后一个版本。

   **可以复制：**&#x200B;收件人可以执行&#x200B;**[!UICONTROL 另存为]**&#x200B;操作，并有权访问左边栏。 在此角色中，项目交互不受限。如果您希望将项目共享给了解您组织数据以及知道如何使用 Analysis Workspace 的用户，但不希望更改项目，则此角色非常有用。

   **可以查看：**&#x200B;收件人无法执行&#x200B;**[!UICONTROL 保存]**&#x200B;或&#x200B;**[!UICONTROL 另存为]**&#x200B;操作，并且不具有访问左边栏的权限。 项目交互受到限制。如果您希望将项目共享给不太熟悉您组织的数据结构或不太熟悉 Analysis Workspace 和 Adobe Analytics 的一般用户，则此角色非常有用。 但是，您可能仍然希望这些用户在一个安全的环境中使用数据和信息分析。详细了解[“可以查看”角色提供的项目体验](/help/analyze/analysis-workspace/curate-share/view-only-projects.md)。

1. 选择共享项目时是否启用以下选项：

   * **共享嵌入的项目组件：**&#x200B;与所有接收人共享区段、计算量度和日期范围。 共享后，这些组件将显示在接收人工作区的“组件”下拉菜单中。此设置不具有持续性，属于分享时的一次性操作。

   * **设置为收件人的登陆页面：** 将此页面设置为收件人的登陆页面。 此设置不具有持续性，属于分享时的一次性操作。

1. 单击&#x200B;**[!UICONTROL 共享]**。(如果项目已共享，请单击 [!UICONTROL **更新**].)

   或

   单击 **[!UICONTROL 组织并共享]** 自动应用项目策划。 (如果项目已共享，请单击 **[!UICONTROL 策划和更新]**.) 了解有关[项目策划](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hans)的更多信息。

## 共享项目链接

按本节所述共享链接时，请考虑以下事项：

* 使用链接的收件人必须登录 Adobe Analytics 才能访问项目。

* 如果收件人未分配角色，并收到 [链接](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=zh-Hans) 默认情况下，项目会为其分配角色。 管理员将收到 **[!UICONTROL 可以编辑]** 和非管理员接收 **[!UICONTROL 可以复制]**.

与组织中的用户共享项目链接：

1. 保存项目。如果存在未保存的更改，系统会在共享链接之前提示您保存项目。

1. 选择 **[!UICONTROL 共享]** > **[!UICONTROL 与工作区用户共享]**，然后选择 **[!UICONTROL 复制]** 旁边 **[!UICONTROL 按链接共享]** 字段。

   ![](assets/share-proj-modal.png)

1. 与组织中的用户共享项目链接。 例如，您可以将其粘贴到电子邮件中，粘贴到内部网站上，等等。

## 与任何人共享项目（无需登录） {#share-public-link}

{{release-limited-testing-section}}

您可以授予 [只读访问](/help/analyze/analysis-workspace/curate-share/view-only-projects.md) 向无法访问Analysis Workspace的人员实施项目。 这包括：

* 组织外的人员

* 您组织中未配置Adobe Analytics的人员

>[!NOTE]
>
>与无权访问Analysis Workspace的人员共享Adobe Analytics项目时，请考虑以下事项：
>
>* Analytics管理员可以禁用以这种方式共享项目的功能，如 [首选项](/help/analyze/analysis-workspace/user-preferences.md). 如果无法按照本节所述共享项目，则Analytics管理员已禁用此功能。
>
>* 无法与无权访问Adobe Analytics的人员共享具有超过14个扩展可视化的项目。
>
>* 与您共享的用户可以查看在 [策划](curate.md).
> 
>* 您与共享的用户可以更改项目日期范围。 默认情况下，会显示您为项目设置的日期范围。


要与无权访问Analysis Workspace的人员共享Adobe Analytics项目，请执行以下操作：

1. 打开要共享的Analysis Workspace项目。

1. 单击 **[!UICONTROL 共享]** > **[!UICONTROL 与任何人共享]**.

   如果存在未保存的更改，系统会提示您保存项目。

   <!-- Add screen shot of new modal -->

1. 启用 **[!UICONTROL 链接处于活动状态]** 选项。

   选择此选项将创建一个指向项目的链接，该链接可供任何人共享。 您可以随时通过禁用此选项来禁用对项目的访问权限。

   项目的所有者也是此链接的所有者。 仅当项目所有权被转移时，链接所有权才能转移给其他用户，如 [转移用户资产或设置帐户过期日期](/help/admin/admin/user-management2/users-assets.md) 管理指南中的。

1. 选择是否启用以下安全选项（此选项可由Analytics管理员控制）：

   * **[!UICONTROL 需要 Experience Cloud 身份验证]:**

      启用此选项后，只有能够登录到创建了您共享的项目的Adobe Experience Cloud组织的用户才能访问该项目。

      Analytics管理员可以为公司配置此首选项，如 [首选项](/help/analyze/analysis-workspace/user-preferences.md). 根据管理员配置此选项的方式，您可能会遇到以下情况：

      * 如果此选项不可见，则您的Analytics管理员未启用此功能。

      * 如果此选项处于启用状态且灰显，则您的Analytics管理员需要对任何访问Analysis Workspace项目的人进行Experience Cloud身份验证。

1. 在 **[!UICONTROL 与任何人共享（无需登录）]** 字段，单击 **复制链接** 图标 ![复制链接图标](assets/copy-link-icon.png) 将链接复制到系统剪贴板。

1. 与您希望拥有项目访问权限的人员共享该链接。 例如，您可以将链接粘贴到电子邮件中。

   与您共享该链接的任何人都可以查看Analysis Workspace项目。

1. （可选）您可以单击 **生成新链接** 图标 ![生成链接图标](assets/regenerate-link.png) 删除之前收到项目链接的用户的访问权限。 系统会生成一个新链接，您可以与想要访问该项目的用户共享该链接。

1. 选择 **[!UICONTROL 关闭]** 关闭“共享”对话框。 您的更改将自动保存。

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
| 如果收件人打开项目链接，他们会获得什么体验？ | 收件人将获得您在共享模式中为其分配的角色。如果收件人未分配角色，并收到指向项目的链接(**[!UICONTROL 共享]** > **[!UICONTROL 与工作区用户共享]**，然后选择 **[!UICONTROL 复制]** 旁边 **[!UICONTROL 按链接共享]** 字段)，则默认情况下会将他们置于角色中。 管理员将获得&#x200B;**[!UICONTROL 可以编辑]**&#x200B;角色，非管理员将获得&#x200B;**[!UICONTROL 可以复制]**&#x200B;角色。 |
