---
description: 有关登录 Report Builder 的三种方法的信息。
title: Report Builder 登录
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Report Builder 登录

有关登录 Report Builder 的三种方法的信息。

当前，单击“Report Builder”时，可使用以 **[!UICONTROL Sign In]** 下登录选项。

![](assets/login_screen.png)

* [标准](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [单点登录](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)
* [Experience Cloud和单点登录](/help/analyze/report-builder/setup/login.md#section_1FA230F35AB54021A874A7A28DE4C850)

## 标准 {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

如果您要使用 Adobe Analytics 凭据登录 Report Builder，请使用此登录方法。

**Report Builder 登录 - 字段定义**

| 字段 | 定义 |
|--- |--- |
| 公司 | 您用于Adobe Analytics的公司登录凭据。 |
| 用户名 | 您用于Adobe Analytics的用户名登录名。 用户的计划任务链接到用户名。 如果您使用相同的登录凭据登录到报表生成器，则可以从任何计算机视图计划任务。 |
| 密码 | 您的Analytics密码。 |
| 记住我 | 登录信息经过加密并存储在安装了Report Builder的计算机上的用户用户档案文件中。 由于登录信息已保存，因此使用同一台计算机以报表创建者身份打开包含报表的电子表格的任何人，都能够刷新和编辑数据。如果您与其他人共用一台计算机，并且不希望公开电子表格数据，请不要启用此选项。要禁用自动登录设置，请单击工 **[!UICONTROL Log in With Different Credentials]** 具栏上的并禁用 **[!UICONTROL Remember Me]**。 |
| 使用代理服务器 | 如果您通过代理服务器访问Internet并且需要提供代理用户名和密码，则启用此选项。 |

## 单点登录 {#section_6970A5F926774976B85FFE576610E85F}

此（旧版）单点登录仅会将您登录到Adobe Analytics，而不是整个Experience Cloud。

您还可以键入域，系统将识别该域并将您重定向到公司的登录页面以登录Adobe Analytics。

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

通过Experience Cloud登录名，您可以使用您的企业ID（电子邮件和密码）登录Adobe Experience Cloud。 单 **[!UICONTROL Sign In]** 击> **[!UICONTROL Sign in with an Enterprise ID]** 可重定向到公司的单一登录页面。 有关Enterprise ID的详细信息，请单击 [此处](https://helpx.adobe.com/cn/enterprise/kb/enterprise-id-faq.html#whatis)。

![](assets/adobe_id_login.png)

>[!NOTE] Experience Cloud 登录基于会话，且令牌在 30 天后到期。

