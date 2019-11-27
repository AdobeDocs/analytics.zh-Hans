---
description: 可让您控制对报表数据的访问。相关选项包括强密码、密码过期时间、IP 登录限制及电子邮件域限制。
solution: Analytics
title: 安全管理器
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 28c18d4bab00ad1fe7b8fbd147003ec178a32da6

---


# 安全管理器

通过安全管理器，您可以控制对报告数据的访问。 相关选项包括强密码、密码过期时间、IP 登录限制及电子邮件域限制。

## 设置

**[!UICONTROL Analytics]** &gt;管 **[!UICONTROL 理员]** &gt;公司 **[!UICONTROL 设置]** &gt;安 **[!UICONTROL 全性]**

| 设置 | 描述 |
|--- |--- |
| 需要强密码 | 迫使用户遵循以下规则来创建更安全的密码： <ul><li>长度不少于 8 个字符。</li><li>第一个字符和最后一个字符之间必须至少有一个符号／数字字符。</li><li>必须至少有一个Alpha字符。</li><li>英语词典中找不到或不得包含词典中的单词。</li><li>不能包含登录用户名中的 3 个连续字符。</li><li>必须不同于最近使用过的 10 个密码。</li></ul>**注意**:此功能将在以后的新密码上实施。 它不检查现有密码，或者强制用户更改现有密码。因此，请考虑启用密码过期以强制用户更改其密码并遵守强密码规则。 |
| 密码过期 | 强制用户定期更改其用户帐户密码。您可以指定密码过期的时间周期，也可以强制密码立即过期。 |
| 强制 IP 登录限制 | (此功能不能与Experience cloud登录名一起使用。 请注意，此功能自2020年10月起将不再可用。 [更多……](/help/admin/company/login-restrictions-eol.md)<br> )限制对特定IP地址或IP地址范围的报告访问。 您可以在 IP 地址过滤器列表中添加最多 100 个条目，每个条目可以是一个特定的地址或地址范围。只有当 IP 地址过滤器列表中至少有一个条目时，才会执行强制 IP 登录限制。Accepted IP Address: To specify an IP address range, enclose the range in brackets (for example, `192.168.10.[20-240]`). You can also use wildcards to specify any number from 0 to 255 (for example, `192.168.[10-14].*8) Failed logins are logged and viewable from the [Usage and Access Log](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| 强制执行电子邮件域名限制 | 对电子邮件地址和域进行过滤，以限制 Analytics 能够将书签、可下载报表和警报发送到哪些地址。电子邮件过滤器列表支持最多 100 个条目，每个条目可以是一个电子邮件地址或整个电子邮件域。如果计划的报表有一个未批准的电子邮件目的地，则 Analytics 会发送一封电子邮件告知该问题，并提供链接以取消该报表的运行计划。**[!UICONTROL 只有当]已接受的电子邮件域过滤器列表中至少有一个条目时，才会强制执行电子邮件域名限制**。**[!UICONTROL 已接受的电子邮件地址和域]**:要指定IP地址范围，请将范围括在括号中(例如，192.168.10.[20-240])。 You can also use wildcards to specify any number from 0 to 255 (for example, 192.168.[10-14].*) |
| 密码恢复通知 | 当用户试图重置用户帐户密码时，通知指定的管理员。**[!UICONTROL 现有管理员]**：显示所有管理员。您可以按住 Ctrl 键或 Shift 键并单击，以选择多个管理员。**[!UICONTROL 电子邮件成员：]**&#x200B;显示当前定义的电子邮件群组。 |
