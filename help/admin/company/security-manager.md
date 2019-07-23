---
description: 可让您控制对报表数据的访问。相关选项包括强密码、密码过期时间、IP 登录限制及电子邮件域限制。
seo-description: 可让您控制对报表数据的访问。相关选项包括强密码、密码过期时间、IP 登录限制及电子邮件域限制。
seo-title: 安全管理器
solution: Analytics
title: 安全管理器
topic: 管理工具
uuid: b3fbdba0-e2 bf-4d67-92e3-ef05711141 d4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 安全管理器

可让您控制对报表数据的访问。相关选项包括强密码、密码过期时间、IP 登录限制及电子邮件域限制。

**[!UICONTROL “分析]** ”&gt;“ **[!UICONTROL 管理员]** ”&gt;“ **[!UICONTROL 公司设置]** ”&gt; **[!UICONTROL “安全性”]**

<table id="table_F1AD9DE5094A4FC2B9DA8D01198F944B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 需要强密码 </span> </td> 
   <td colname="col2">迫使用户遵循以下规则来创建更安全的密码： 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">长度不少于 8 个字符。 </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">首位和末位字符之间至少包含一个符号或数字。 </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">至少包含一个英文字母。 </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">英语词典中找不到或不得包含词典中的单词。 </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">不能包含登录用户名中的 3 个连续字符。 </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">必须不同于最近使用过的 10 个密码。 </li> 
    </ul> <p>注意：此功能对以后的新密码强制实施。它不检查现有密码，或者强制用户更改现有密码。因此，请考虑启用密码过期以强制用户更改其密码并遵守强密码规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 密码过期</span> </td> 
   <td colname="col2"> 强制用户定期更改其用户帐户密码。您可以指定密码过期的时间周期，也可以强制密码立即过期。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 强制 IP 登录限制</span> </td> 
   <td colname="col2"> <p>将报表访问限定于特定的 IP 地址或 IP 地址范围。 </p> <p>您可以在 IP 地址过滤器列表中添加最多 100 个条目，每个条目可以是一个特定的地址或地址范围。 </p> <p> 只有当 IP 地址过滤器列表中至少有一个条目时，才会执行<span class="wintitle">强制 IP 登录限制</span>。 </p> <p> <span class="uicontrol"> 接受的IP地址</span>：要指定IP地址范围，请将范围包含在括号中(例如，
    <code>
      192.168.10。[20-240]
    </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
    <code>
      192.168.[10-14].*
    </code>) </p> <p>失败的登录将被记录并可从<a href="../../admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232" format="dita" scope="local">使用与访问日志</a>查看。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 强制执行电子邮件域名限制</span> </td> 
   <td colname="col2"> <p>对电子邮件地址和域进行过滤，以限制 Analytics 能够将书签、可下载报表和警报发送到哪些地址。 </p> <p>电子邮件过滤器列表支持最多 100 个条目，每个条目可以是一个电子邮件地址或整个电子邮件域。 </p> <p>如果计划的报表有一个未批准的电子邮件目的地，则 Analytics 会发送一封电子邮件告知该问题，并提供链接以取消该报表的运行计划。 </p> <p> 只有当<span class="wintitle">已接受的电子邮件域过滤器</span>列表中至少有一个条目时，才会<span class="wintitle">强制执行电子邮件域名限制</span>。 </p> <p> <span class="uicontrol"> 已接受的电子邮件地址和域</span>：要指定IP地址范围，请将范围包含在括号中(例如，
    <code>
      192.168.10。[20-240]
    </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
    <code>
      192.168.[10-14].*
    </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 密码恢复通知</span> </td> 
   <td colname="col2"> <p>当用户试图重置用户帐户密码时，通知指定的管理员。 </p> <p> <span class="uicontrol">现有管理员</span>：显示所有管理员。您可以按住 Ctrl 键或 Shift 键并单击，以选择多个管理员。 </p> <p> <span class="uicontrol">电子邮件成员：</span>显示当前定义的电子邮件群组。 </p> </td> 
  </tr> 
 </tbody> 
</table>

