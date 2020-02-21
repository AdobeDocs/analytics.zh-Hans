---
description: 'null'
keywords: groups;permissions
subtopic: Users and groups
title: 用户和群组权限更改
topic: Admin tools
uuid: 94f2727b-17e4-4003-a222-35c821d6959e
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 用户和群组权限更改

>[!IMPORTANT]
>
>用户和产品管理即将转移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html) 中。Adobe 会通知您何时迁移用户。在迁移完所有客户之后，将撤销 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员工具]** > **[!UICONTROL 用户管理]**&#x200B;中的帮助内容。

## 更改了哪些内容？{#section_2C205DE94155441B9E9D3E4C46CCF2EE}

**[!UICONTROL 管理员]** > **[!UICONTROL 用户管理]** > **[!UICONTROL 群组]**

> [!NOTE] 由于可用的可能权限组合太多，我们无法提供文档介绍可在每种权限组合中使用的所有 API 方法。通常，被授予 Web 服务访问权限的非管理员将只有 API 方法的读取权限。他们将没有这些方法的写入权限。

由于 API 和界面使用相同的权限系统，因此无论管理员在界面（Adobe Admin Console）中为特定的非管理员授予怎样的权限，该用户在 API 中都将拥有相同的权限。

<table id="table_D1DB0DE37752450BBCCA44DB760BB505"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 增强功能 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p id="reportaccess">更改了<span class="uicontrol">报表访问</span>（自定义群组） </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> 新增群组</span> &gt; <span class="uicontrol">报表访问</span> </p> <p>“<span class="wintitle">定义用户群组</span>”页面上的“<span class="wintitle">报表访问</span>”部分已精简为四个类别，它们允许您在某一个粒度级别自定义权限。 </p> <p><img  src="assets/report-access.png" id="image_CB83E5C7DB4343619421A1FAA61478D0"> </img> </p> <p>这些项目以前位于 </p> 
    <ul id="ul_16D5EF18D57D4608AEEDEC40D90D8828"> 
     <li id="li_F29E84C6228A464C8807F09205AEAAC6"> <p> <a href="/help/admin/user-management2/c-customize-report-access/groups-analytics-tools.md">Analytics 工具</a>：启用常规项目（帐单、日志等）、公司管理、工具、Web 服务访问、Report Builder 和 Data Connectors 集成的用户权限。 </p> <p> <b>注意：</b>“自定义 Admin Console”类别中的“公司设置”已被移动到“Analytics 工具”中。 </p> </li> 
     <li id="li_A6EB788162A2455E94CE54B9279A854D"> <p> <a href="/help/admin/user-management2/c-customize-report-access/groups-report-suite-tools.md">报表包工具</a>：启用 Web 服务、报表包管理、工具和报表及功能板项目的用户权限。 </p> </li> 
     <li id="li_EDB0255E009B4F1CAFAF53966B41363C"> <p> <a href="/help/admin/user-management2/c-customize-report-access/groups-metrics.md">量度</a>：启用流量、转化、自定义事件、解决方案事件和内容识别等的权限。 </p> </li> 
     <li id="li_8DAE87D1DEF54803A9C6FE31C01F0FB0"> <p> <a href="/help/admin/user-management2/c-customize-report-access/groups-dimensions.md">维度</a>：在粒度级别自定义用户访问权限，包括 eVar、流量报表、解决方案报表和路径报表。 </p> </li> 
    </ul> <p>例如，您可以创建一个群组，并为其授予对多个 Analytics 工具（<span class="wintitle">Analysis Workspace</span>、<span class="wintitle">Reports &amp; Analytics</span> 和 <span class="wintitle">Report Builder</span>）的访问权限，以及使用特定量度和维度（包括 eVar）及区段或计算量度创建等功能的权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更改了预定义群组 </p> </td> 
   <td colname="col2"> <p> <b>管理员访问权限：</b>管理员不再需要预定义群组。管理员现在具有对所有项目（工具、量度、维度）以及 Web 服务访问、Report Builder、Activity Map 和 Ad Hoc Analysis 的访问权限。 </p> <p>从此以后，群组的用途是授予或限制非管理用户的访问权限。 </p> <p> <b>自定义群组：</b>自定义群组取代了预定义群组。现有预定义群组将迁移到自定义群组，所用的群组名称保持不变。您已创建的任何自定义群组（包括其设置）将被保留。但您会发现，设置的位置将发生移动。例如，“自定义 Admin Console”中的“公司设置”现在位于<a href="/help/admin/user-management2/c-customize-report-access/groups-analytics-tools.md">自定义 Analytics 工具</a>中。 </p> <p> 属于<span class="term">所有报表访问</span>的用户已迁移到具有以下访问权限的自定义群组： </p> 
    <ul id="ul_696A9243F5FD4AF187352C2F4B1CFDC2"> 
     <li id="li_683A0A3BB7214CFFBC61D5A4CD237F48">所有维度 </li> 
     <li id="li_D8FDBF6A32224731AB706315DEA0A03E">所有量度 </li> 
     <li id="li_65ABE5C95D43444D88E63EE95C9AED05">所有报表包 </li> 
     <li id="li_7ED1505590144B38B3B9851BAA6BBB49">渠道报表 权限 </li> 
     <li id="li_F718FE1FCF9A4B05AB933CA3F105F3EC">异常检测报表权限 </li> 
     <li id="li_527BD52007E846FE8B5F71AB3C12F695">实时报表权限 </li> 
     <li id="li_AFFB58C7FB644AC8A85E2D76BA7D51F5">Analysis Workspace 访问权限 </li> 
    </ul> <p>管理员可以删除自定义群组并创建他们自己的群组，因为之前在预定义群组中提供的所有设置都可以在<a href="/help/admin/user-management2/c-user-groups/groups.md">定义用户群组</a>中的“<span class="wintitle">报表访问</span>”设置下进行自定义。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>维度级别权限 </p> </td> 
   <td colname="col2"> <p>您可以对权限进行自定义，以便包含或排除对维度（和量度）的访问权限。 </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>自定义群组内的所有当前维度和量度均已自动迁移到新类别。如果现有的群组启用了量度，则默认情况下将为其提供所有新增的许可维度（eVar 和内容识别）和量度。 </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> 分类导入器（前身为 SAINT）权限：分类的访问权限取决于对此分类所依据的<a href="https://marketing.adobe.com/resources/help/zh_CN/reference/c_classifications.html">变量</a>的访问权限。 </li> 
    </ul> <p>请参阅<a href="/help/admin/user-management2/c-customize-report-access/groups-dimensions.md">自定义维度权限</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console </p> </td> 
   <td colname="col2"> <p>仅建议新客户或<a href="https://marketing.adobe.com/resources/help/zh_CN/mcloud/core_services.html">已在 Experience Cloud 中设置了</a>公司的客户使用。现有 <span class="keyword">Analytics</span> 客户向 <span class="keyword">Experience Cloud</span> 身份管理系统的迁移已经提上计划日程。 </p> <p>有关更多信息，请参阅<a href="https://helpx.adobe.com/cn/enterprise/using/manage-permissions-and-roles.html">在 Admin Console 中管理产品权限</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 关于权限更改的常见问题解答 {#section_02809EFC95054B40A089E6C6E4FACA13}

以下是有关新更新和计划更新以及这些更新对管理环境有何影响的重要新增信息。

<table id="table_1E93F45C66E841E6882FB602509F30A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>2016 年 7 月</b>版本做出了哪些权限更改？ </td> 
   <td colname="col2"> <p> <b>全部报表包访问</b> </p> <p>在添加要包含在群组中的报表包时，您可以指定<span class="uicontrol">全部报表包访问</span>。此设置会将群组权限应用到所有当前和后续的报表包。 </p> <p>要启用此功能，请导航至<span class="uicontrol">用户管理</span> &gt; <span class="uicontrol">群组</span> &gt; <span class="uicontrol">添加新用户群组</span>，然后选择<span class="uicontrol">全部报表包访问</span>。 </p> <p><img placement="break"  src="assets/all-report-suites.png" width="300px" id="image_9E814D412E87484C940F1100D6DE2B0F" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我应该使用 Admin Console 管理用户，还是应该使用现有的 Analytics 用户管理？ </p> </td> 
   <td colname="col2"> <p>在“Analytics”&gt;“管理员”&gt;“用户管理”中所做的更改不会反映在 Admin Console 中。因此，只有已经使用 Admin Console 进行用户和群组管理的新客户才应该继续这样做。现有 Analytics 群组管理向 Admin Console 的迁移已经提上计划日程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>2016 年 10 月</b>版本做出了哪些权限更改？ </p> </td> 
   <td colname="col2"> <p>在以下方面增强了当前的<span class="wintitle">管理工具</span>界面： </p> <p> 
     <ul id="ul_2A31E8DC17A94B7FABDBA9C87C3947EF"> 
      <li id="li_AE2ECCA01CC64D30B109BE74379EE474">权限更改，如<a href="/help/admin/user-management2/c-user-management/permissions-changes.md">管理更改 - 2016 年秋季版</a>中所述。 </li> 
      <li id="li_33CB2B6A2E5F45BE97CC5E0983AF280E">删除菜单中不再包含的失效流量报表。 </li> 
      <li id="li_57234CF27E1D405987DE89312CD62C52">分类权限：分类的访问权限将取决于对此分类适用变量的访问权限。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我需要做什么来迁移用户？ </p> </td> 
   <td colname="col2"> <p>您不需要做任何操作，所有权限迁移的执行都将是透明的。 </p> <p> 
     <ul id="ul_654F85286EC04416B3E0BA725EBE10AD"> 
      <li id="li_8050B8941F794103B82A0ADF0930D216">当前自定义群组中的所有流量报表都将自动迁移到新的维度类别中。 </li> 
      <li id="li_B97079DB29A346B98D066F11AB7F94AF">如果自定义群组已经启用任何量度，则将自动为其提供所有新增的可授权维度（eVar 和解决方案变量）。 </li> 
      <li id="li_F1219EF490DA473BA15F2B215F2995AE"> 对于至少具有一个量度的自定义群组，将自动为其授予对所有 eVar 及其他内容识别维度的访问权限，新提供的流量维度（以前称为流量报表）<b>除外</b>。 </li> 
      <li id="li_F494CE6144A04A6199CFBBA1D7BEA32B">每个预定义群组都将更改为权限。这些新权限将被添加到新的 <span class="uicontrol">Analytics 工具</span>类别中。 </li> 
      <li id="li_2FCD9254FC3C4FD7871EEF9453E5CE1E">具有任何量度的每个自定义群组会将所有 Analytics 解决方案事件添加为新量度。 </li> 
      <li id="li_34C4560769B64F28A4E83BAE71065DCC">过去位于“全部报表访问”中的每个用户都将被添加到新的自定义群组中。“全部报表访问”将不再存在。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>哪些功能没有变化？ </p> </td> 
   <td colname="col2"> <p>“访客属性”仍将不可授权。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 授权快速参考 {#section_A3FDD8259F524B21A5489833533D1B28}

下表列出了相关任务以及执行这些任务的位置（具体取决于公司的状态）。

> [!NOTE] *`migrated user`* 和 *`Experience Cloud user`* 指已接受加入 Experience Cloud 的电子邮件邀请的用户。如果未接受电子邮件邀请，用户仍是 Analytics 用户，无法在 Admin Console 中对其进行管理。（迁移时使用了[企业或联合 ID](https://helpx.adobe.com/cn/enterprise/using/set-up-identity.html) 的情况除外。在这种情况下，当管理员逐个迁移用户时，将迁移此类用户。）

<table id="table_B68FD00FC5D24823A86BB69558C0327C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任务 </th> 
   <th colname="col2" class="entry"> 未迁移的登录公司 </th> 
   <th colname="col3" class="entry"> 当前正在迁移的公司 </th> 
   <th colname="col4" class="entry"> 已完成迁移的登录公司 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 创建用户 </td> 
   <td colname="col2"> <p>Admin Console（创建用户并将其添加到 Analytics <a href="https://marketing.adobe.com/resources/help/zh_CN/mcloud/admin_getting_started.html">产品配置</a>的同时也会在 Analytics 中创建用户帐户）。 </p> <p> <a href="/help/admin/user-management2/c-user-management/t-add-user-account.md"> 管理工具</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 编辑用户 </td> 
   <td colname="col2"> <p> <a href="/help/admin/user-management2/c-user-management/t-add-user-account.md"> 管理工具</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> </p> <p> 管理工具 - 编辑（对于迁移用户，管理工具中的编辑功能仅限于 API 密钥管理）和删除/转移资产。 </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> </p> <p> 管理工具 - 编辑（仅限于 API 密钥管理）和删除/转移资产。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 删除用户 </td> 
   <td colname="col2"> <p>Admin Console - 适用于 Experience Cloud 用户 </p> <p>管理工具 - 适用于所有用户，但对于 Experience Cloud 用户，只能删除映射的 Analytics 用户，而不能删除 Experience Cloud 帐户。 </p> </td> 
   <td colname="col3"> <p>Admin Console - 适用于已迁移的用户 </p> <p>管理工具 - 适用于仅 Analytics 用户。 </p> </td> 
   <td colname="col4"> <p>Admin Console </p> <p> 管理工具 - 在 Admin Console 中删除 Experience Cloud 用户，或取消关联这些用户的帐户后，您可以从管理工具中删除 Analytics 登录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 登录到 Analytics </td> 
   <td colname="col2"> <p> <b>Experience Cloud：</b><span class="filepath">marketing.adobe.com</span>。仅适用于 Experience Cloud 用户。 </p> <p> <b>Analytics（旧版）：</b><span class="filepath">sc.omniture.com</span>。适用于仅 Analytics 用户以及具有 Analytics 凭据的 Experience Cloud 用户 </p> </td> 
   <td colname="col3"> <p> <span class="filepath">marketing.adobe.com</span> - 仅适用于 Experience Cloud 用户。 </p> <p> <span class="filepath">sc.omniture.com</span> - 适用于仅 Analytics 用户以及具有 Analytics 凭据的 Experience Cloud 用户。 </p> <p>在迁移过程中，管理员可以针对特定用户关闭 <span class="filepath">omniture.com</span> 登录功能。 </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 创建群组 </td> 
   <td colname="col2"> <p>Admin Console - 在 Admin Console 中创建群组后，管理工具中将出现一个在 Analytics 中映射的群组，不过无法从管理工具中更改此映射群组的名称，也无法将其删除。 </p> <p>管理工具。 </p> </td> 
   <td colname="col3"> <p>Admin Console（<a href="https://marketing.adobe.com/resources/help/zh_CN/mcloud/admin_getting_started.html">创建产品配置</a>） </p> </td> 
   <td colname="col4"> <p>Admin Console（<a href="https://marketing.adobe.com/resources/help/zh_CN/mcloud/admin_getting_started.html">创建产品配置</a>） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 编辑群组中的用户 </td> 
   <td colname="col2"> <p>Admin Console - 仅适用于 Experience Cloud 用户。 </p> <p>管理工具 - 可以从管理工具中编辑仅 Analytics 用户和 Experience Cloud 用户的群组成员资格。但是，如果 Experience Cloud 用户属于 Admin Console 中的群组，则无法在管理工具中将其从该群组中删除。 </p> </td> 
   <td colname="col3"> <p>Admin Console - 仅适用于 Experience Cloud 用户 </p> <p> 管理工具 - 仍可以在管理工具中将仅 Analytics 登录添加到群组或从群组中删除。 </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 编辑群组的权限 </td> 
   <td colname="col2"> <p>Admin Console - 您可以编辑在 Admin Console 中创建的组。 </p> <p>管理工具 - 可以编辑任何群组的权限。 </p> </td> 
   <td colname="col3"> <p>Admin Console </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 删除群组 </td> 
   <td colname="col2"> <p>Admin Console - 您只能删除在 Admin Console 中创建的组。 </p> <p>管理工具 - 只能删除从管理工具中创建的群组。 </p> </td> 
   <td colname="col3"> <p>Admin Console </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更改用户的管理状态 </td> 
   <td colname="col2"> <p>Admin Console - 仅适用于 Experience Cloud 用户。 </p> <p>管理工具 </p> </td> 
   <td colname="col3"> <p>Admin Console - 仅适用于 Experience Cloud 用户。 </p> <p>管理工具 - 仅适用于 Analytics 用户。 </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
 </tbody> 
</table>
