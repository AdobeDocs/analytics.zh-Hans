---
description: 有关登录 Report Builder 的三种方法的信息。
title: Report Builder 登录
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: 5b130de23d7826a266f34ed1830540c8c0865560
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 70%

---


# Report Builder 登录

>[!IMPORTANT]
>
>Report Builder版本5.6.47及更高版本仅支持Experience Cloud登录，不支持传统登录，如Site Catalyst单点登录或标准登录。 到2021年4月30日，所有Report Builder用户必须将Report Builder插件更新到版本5.6.47或更高版本，其中包括登录过程的关键更新。

要登录Report Builder，请使用Experience Cloud登录帐户。

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

Experience Cloud 登录允许您使用企业 ID（电子邮件和密码）登录 Adobe Experience Cloud。单击&#x200B;**[!UICONTROL 登录]** > **[!UICONTROL 使用企业 ID 登录]**&#x200B;可重定向到贵公司的单点登录页面。有关企业 ID 的更多信息，请单击[此处](https://helpx.adobe.com/cn/enterprise/kb/enterprise-id-faq.html#whatis)。

![](assets/adobe_id_login.png)

>[!NOTE]
>
> Experience Cloud 登录基于会话，且令牌在 30 天后到期。

## 登录 Report Builder

登录到Report Builder

1. 在 Excel 中，单击&#x200B;**[!UICONTROL 外接程序]**。
1. 单击&#x200B;**[!UICONTROL 登录]**。可让您登录的其他操作包括：

   * 单击&#x200B;**[!UICONTROL 创建]**。
   * [在请求管理器中选择请求](/help/analyze/report-builder/manage-requests/r-arb-manage-requests.md)，然后单击“添 **** 加或 **[!UICONTROL 管理”]**。
   * 多次在Excel中单击请求。

1. 填写“[!UICONTROL 登录]”页上的字段，然后单击&#x200B;**[!UICONTROL 确定]**。

## 旧版登录类型

>[!IMPORTANT]
>
>到2021年4月30日，旧版登录类型将无法使用。 所有Report Builder用户必须将Report Builder插件更新到版本5.6.47或更高版本，其中包括登录过程的关键更新。 **Report Builder版本5.6.47及更高版本仅支持Experience Cloud登录，不支持传统登录，如标准登录或Site Catalyst单点登录。**

<!-- ![](assets/login_screen.png) -->

* [标准](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [Site Catalyst单点登录](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)

## 标准 {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

如果您要使用 Adobe Analytics 凭据登录 Report Builder，请使用此登录方法。

**Report Builder 登录 - 字段定义**

| 字段 | 定义 |
|--- |--- |
| 公司 | 您用于 Adobe Analytics 的公司登录凭据。 |
| 用户名 | 您用于 Adobe Analytics 的登录用户名。用户的计划任务会链接到用户名。您可以从任何计算机查看计划任务，只要使用相同的登录凭据登录 Report Builder 即可。 |
| 密码 | 您的 Analytics 密码。 |
| 记住我 | 登录信息会加密并存储到安装了 Report Builder 的计算机上的用户配置文件中。由于登录信息已保存，因此使用同一台计算机以报表创建者身份打开包含报表的电子表格的任何人，都能够刷新和编辑数据。如果您与其他人共用一台计算机，并且不希望公开电子表格数据，请不要启用此选项。要禁用自动登录设置，请单击工具栏上的&#x200B;**[!UICONTROL 使用不同的凭证登录]**&#x200B;并禁用&#x200B;**[!UICONTROL 记住我]**。 |
| 使用代理服务器 | 如果您通过代理服务器访问 Internet 并且需要提供代理用户名和密码，请启用此选项。 |

## 单点登录 {#section_6970A5F926774976B85FFE576610E85F}

此（旧版）单点登录只能登录到 Adobe Analytics，而不是整个 Experience Cloud。

您还可以输入域，系统会识别域并将您重定向到贵公司的单点登录页面，以登录 Adobe Analytics。
