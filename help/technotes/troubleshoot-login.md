---
title: 登录Adobe Analytics疑难解答
description: 无法登录Adobe Analytics时要采取的步骤。
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 2%

---


# 登录Adobe Analytics疑难解答

Adobe Analytics使用多种身份验证方法登录：

* Adobe ID穿过Experience Cloud
* 旧版分析ID
* 单点登录

**如果您定期访问Analytics并随机开始遇到登录问题，则清除浏览器的cookie和缓存可解决大多数问题。**

有时，可用性问题会影响登录能力。 检 [查status.adobe.com](https://status.adobe.com) ，查看任何未结事件。 否则，根据组织的身份验证方法，使用相应的部分。

## Adobe ID

使用Experience Cloud登录Adobe Analytics时的疑难解答。

1. 导航 [到experience.adobe.com](https://experience.adobe.com)。 如果您无法访问此站点，则您的组织可能不允许通过防火墙访问此域。 与您组织的IT团队合作，实现这一目标。 请参 [阅Adobe Experience Cloud使用的IP](https://helpx.adobe.com/cn/analytics/kb/adobe-ip-addresses.html) 和域，以获得可提供给您的IT团队的有用信息。

2. 使用Adobe ID进行身份验证：单 **[!UICONTROL 击“使用Adobe ID登录”]**。 如果您无法登录，多次会检查您的电子邮件地址键入是否正确。 否则，单击 **[!UICONTROL 重置密码]** ，然后按照提示重置您的Adobe ID密码。

3. 验证后访问分析：单击右上方的9网格图标，然后单击分析。 如果您没有此选项或它灰显，请与您组织中的产品管理员合作，确保您具有访问Analytics的正确权限。

## 旧版分析ID

您组织中的用户尝试登录时可能会收到以下错误：

*为安全起见，由于登录尝试失败的次数过多，此帐户已被锁定。*

如果清除浏览器的cookie/缓存未解决此问题，请与组织中的Analytics管理员联系以重置用户密码。

>[!IMPORTANT]
>
>以下重置用户密码的步骤仅适用于旧版Analytics ID，不适用于Adobe ID。如果您的组织使用Adobe ID的帐户，则可以在adminconsole. [adobe.com上管理用户帐户](https://adminconsole.adobe.com)。

1. 使用具有管理权限的帐户登录Adobe Analytics。
2. 导航到“管 **[!UICONTROL 理员]** ”> **[!UICONTROL “用户管理]**”。
3. 单击“ **[!UICONTROL 用户]** ”选项卡， **[!UICONTROL 然后单击]** 所需用户旁边的“编辑”。
4. 将口令更改为任意值，并选中“要求用 **[!UICONTROL 户在下次登录时更改口令”框]**。
5. 通知用户新密码。

## 单点登录

与组织中的管理员联系以解决单点登录问题。

## 过期登录

您组织中的用户尝试登录时可能会收到以下错误：

*错误：此登录已过期。*

此错误按预期工作。 Adobe Analytics为管理员提供设置用户帐户有效的日期范围的功能。 如果当前日期位于帐户的有效日期范围之外，则他们无法登录。 与组织中的Analytics管理员合作，以延长登录的有效日期范围。 Adobe客户关怀团队无权更改用户帐户的有效登录日期范围。

## 其他登录问题

如果上述步骤均无效，则确定登录问题的范围：

* 使用其他浏览器时是否会发生此问题，或者它是跨所有浏览器出现的问题？
* 该问题是发生在网络上的其他计算机上，还是跨多台计算机出现？
* 尝试使用其他网络（如移动数据连接、库或家庭网络）登录。 跨网络存在问题吗？

如果问题在您的网络中被隔离，请与您组织的IT团队合作解决。 如果它不限于单个网络，请与Adobe客户服务联系。
