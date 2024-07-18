---
title: 排除 Adobe Analytics 登录故障
description: 无法登录 Adobe Analytics 时应采取的步骤。
feature: Analytics Basics
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 100%

---

# 排除 Adobe Analytics 登录故障

Adobe Analytics 使用多种身份验证方法来登录：

* Adobe ID（通过 Experience Cloud）
* 旧版 Analytics ID
* 单点登录

**如果您经常访问 Analytics 但开始随机遇到登录问题，则清理浏览器的 Cookie 和缓存可解决大多数问题。**

有时候，可用性问题也会影响到登录的能力。有关任何维护事件，请查看 [status.adobe.com](https://status.adobe.com)。否则，请根据组织的身份验证方法使用相应的部分。

## Adobe ID

排除使用 Experience Cloud 登录到 Adobe Analytics 时的问题

1. 导航到 [experience.adobe.com](https://experience.adobe.com)。如果您无法访问此网站，则组织的防火墙可能不允许此域通过。请与组织的 IT 团队合作来允许此域。请查看 [Adobe Experience Cloud 中使用的 IP 和域](https://helpx.adobe.com/cn/analytics/kb/adobe-ip-addresses.html)，获取可提供给 IT 团队的有用信息。

2. 使用 Adobe ID 进行身份验证：单击&#x200B;**[!UICONTROL 使用 Adobe ID 登录]**。如果您无法登录，请仔细检查是否正确输入了电子邮件地址。否则，请单击&#x200B;**[!UICONTROL 重置密码]**&#x200B;并按照提示操作，重置您的 Adobe ID 密码。

3. 在通过身份验证之后访问 Analytics：单击右上角的 9 宫格图标，然后单击“Analytics”。如果您没有此选项或者此选项灰显，请与组织的产品管理员合作，确保您拥有正确的权限，可以访问 Analytics。

## 旧版 Analytics ID

组织中的用户在尝试登录时收到以下错误：

*作为安全防范措施，由于登录失败尝试次数过多，此帐户已锁定。*

如果清除浏览器的 Cookie/缓存未能解决此问题，请与组织中的 Analytics 管理员合作来重置用户的密码。

>[!IMPORTANT]
>
>以下重置用户密码的步骤仅适用于旧版 Analytics ID，而不适用于 Adobe ID。如果您的组织使用 Adobe ID，则可以在 [adminconsole.adobe.com](https://adminconsole.adobe.com) 管理用户帐户。

1. 使用具有管理权限的帐户登录 Adobe Analytics。
2. 导航到&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 用户管理]**。
3. 单击&#x200B;**[!UICONTROL 用户]**&#x200B;选项卡，然后单击所需用户旁的&#x200B;**[!UICONTROL 编辑]**。
4. 将密码更改为任意值，然后选中&#x200B;**[!UICONTROL 下次登录时要求用户更改密码]**&#x200B;复选框。
5. 告知用户新密码。

## 单点登录

联系组织中的管理员以解决单点登录问题。

## 已过期登录

组织中的用户在尝试登录时收到以下错误：

*错误：此登录已过期。*

此错误按其设计意图工作。Adobe Analytics 为管理员提供了设置用户帐户的有效日期范围的功能。如果当前日期在帐户的有效日期范围之外，则这些帐户无法登录。与组织的 Analytics 管理员合作，延长登录的有效日期范围。Adobe 客户关怀部门无权更改用户帐户的有效登录日期范围。

## 其他登录问题

如果以上步骤均无效，请考虑更广泛的登录问题：

* 问题出现在使用不同浏览器时还是在所有浏览器上均如此？
* 问题出现在网络上的不同计算机还是多台计算机上均如此？
* 尝试使用不同网络登录，例如移动数据连接、图书馆网络或家庭网络。在不同的网络中问题是否仍然出现？

如果问题仅限于您的网络，请与组织的 IT 团队合作来解决问题。如果不限于某一个网络，请联系 Adobe 客户关怀部门。
