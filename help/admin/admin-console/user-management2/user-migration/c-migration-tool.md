---
description: 在 Adobe Experience Cloud 中将 Analytics 用户 ID 迁移到 Admin Console 的应知事项。
title: 将 Analytics 用户迁移到 Admin Console
feature: Admin Tools
exl-id: f4bc0e92-af53-40db-8138-44d29e4b25fe
source-git-commit: beef45403f3c3eb7ac423ca8e0b6db0143ff1b9b
workflow-type: tm+mt
source-wordcount: '3162'
ht-degree: 71%

---

# 将Analytics用户迁移到Adobe Admin Console{#analytics-user-migration-to-the-admin-console}

有关将Analytics用户ID迁移到Adobe Experience Cloud中的Adobe Admin Console的信息，请了解相关信息。

有关Adobe Admin Console主题的常规帮助（与Analytics迁移无关），请参阅 [Admin Console用户指南](https://helpx.adobe.com/cn/enterprise/administering/user-guide.html).

迁移后，您可以 [管理Experience Cloud用户和产品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 在Adobe Admin Console。

## 什么是 Analytics 用户 ID 迁移？ {#section-adbe49aba10c4e62afa836a97894107c}

通过 Analytics 用户 ID 迁移，管理员可以轻松地将 Analytics“用户管理”中的用户帐户迁移到 Adobe Admin Console。在您的用户被迁移后，他们将能够访问 Experience Cloud 中可用的解决方案与核心服务。Adobe 正在分阶段向客户推出这项迁移功能。

使用Adobe Admin Console的好处包括：

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 好处 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>单点登录 </p> </td> 
   <td colname="col2"> <p>Analytics 用户可以使用其 Adobe ID 或企业 ID 登录到 Experience Cloud 及所有解决方案。这种登录允许用户在 Experience Cloud 中访问集成解决方案与核心服务。 </p> <p>迁移后，尝试通过旧版登录（<span class="filepath">my.omniture.com</span> 和 <span class="filepath">sc.omniture.com</span>）进行登录的用户将被重定向至 <span class="filepath">experiencecloud.adobe.com</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理用户身份和权限 </p> </td> 
   <td colname="col2"> <p>Analytics 可专门在 <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> 中管理用户和权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理产品和核心服务 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">邀请新用户 </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">创建产品配置文件 </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">授予用户对特定产品和服务的权限 </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">获取对 Adobe Experience Cloud 中提供的<a href="https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html">跨解决方案核心服务</a>的访问权限。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 迁移用户 ID 前应知事项（和应做事项）（常见问题解答） {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

针对迁移之前可能存在问题的解答。

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题/任务 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>我是 Analytics 管理员并收到了预迁移电子邮件。我首先该怎么做？ </p> </td> 
   <td colname="col2"> <p>确认您具有 Adobe ID 并能够访问 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> <p>如果没有，请联系 <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。（您应当先联系邀请您加入相应的组织的系统或产品管理员。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM 与 Analytics 集成 </p> </td> 
   <td colname="col2"> <p> 与 Analytics 集成的 AEM 用户需要更改其配置，以使用 Analytics 共享密钥而不是密码。 </p> <p> 您应该在启用迁移之前完成此任务。禁用迁移后，最初配置的密码将不再有效。 </p> <p><b>在 Analytics 中获取共享密钥</b> </p> <p> 共享密钥可以从 Analytics（<span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">用户管理</span>）获取，并且每个用户的共享密钥各不同。 </p> <p><b>使用共享密钥更新 AEM 配置</b> </p> <p>请参阅<a href="https://helpx.adobe.com/cn/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">连接到 Adobe Analytics 和创建框架</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新 Report Builder </p> </td> 
   <td colname="col2"> <p> <p>重要信息：将安装的 <a href="https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html">Report Builder</a> 更新至最新版本。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>何时开始迁移？ </p> </td> 
   <td colname="col2"> <p>Adobe 将通过电子邮件通知 Analytics 管理员，其中将包含对迁移开始时间的说明。 </p> <p>向Adobe Admin Console的迁移将分批进行。 在迁移当天，Adobe 将通知 Analytics 管理员并授予他们访问集成工具的权限。如果登录公司符合为每个迁移批次定义的条件，Adobe 将： </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">设置公司迁移的开始和结束日期。 </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">向公司的当前 Analytics 管理员发送电子邮件通知，发送时间大概是在迁移前 30 天左右。 </li> 
     <li id="li_476265B24CE2404B995201170C75D674">显示产品内通知，以告知管理员迁移的开始日期。 </li> 
    </ul> <p> 在迁移当天，您以前的权限组将自动复制到Adobe Admin Console。 您将无法在 Analytics 管理工具中邀请新用户或创建新群组。 </p> <p>迁移后： </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">管理员将使用Adobe Admin Console管理其Analytics用户和权限。 （您将无法在“Analytics”&gt;“管理员”&gt;“用户管理”中使用用户管理界面。） </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">用户将使用其 Adobe ID 或 Enterprise ID 通过 Experience Cloud 访问 Analytics，而不是通过 <span class="filepath">my.omniture.com</span> 来访问。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在迁移开始当天将发生什么情况？ </p> </td> 
   <td colname="col2"> <p>在迁移开始当天的上午 10 点（世界协调时间）： </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">您在Analytics中的现有权限组将作为产品配置文件自动复制到Adobe Admin Console中，包括其描述以及报表包、量度、维度、Analytics和报表包工具中的粒度权限。 </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">如果您当前的任何Analytics用户是在Adobe Admin Console中创建的(即他们具有关联的Adobe/Enterprise ID)，则会将他们添加到Adobe Admin Console中的相应产品配置文件中。 </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Analytics中“管理员”选项卡下的“用户管理”部分将设置为 <span class="term"> 只读</span>. 您将无法在此处创建新用户或权限组，并将需要在Adobe Admin Console中执行这两项功能。 请参阅 <a href="/help/admin/admin-console/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56"> Adobe Admin Console中不支持的Analytics功能</a> 以了解更多信息。 </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">将准许管理员访问<a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/t-migrate-users.html">用户 ID 迁移工具</a>。此外，还会显示一则产品内通知，其中包含迁移的结束日期（通常是未来 60 天）以及帮助内容和常见问题解答的链接。 </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">您将获得对Adobe Admin Console中“权限”选项卡的访问权限，该选项卡允许您使用您在Analytics中熟悉的所有粒度选项创建产品配置文件。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如何迁移用户 ID？ </p> </td> 
   <td colname="col2"> <p> 单击“管理员”页面中“用户管理”下的<a href="/help/admin/admin-console/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9">迁移用户 ID</a>。使用该工具将用户添加到Adobe Admin Console中的产品配置文件（从Analytics的权限组复制）。 您可以按照自己的节奏迁移用户 ID。 </p> <p>需要管理权限。迁移完成后将无法撤消。 </p> <p>在迁移结束当天，将禁用登录公司中用户对 <span class="filepath">my.omniture.com</span> 的访问。用户（包括那些尚未迁移的用户）将被重定向，以便通过新的 Experience Cloud URL (<span class="filepath">experiencecloud.adobe.com</span>) 登录 </p> <p>注意：Adobe 建议您利用这个机会在迁移之前对用户和组进行审核。删除旧的和未使用的帐户，或不再具有产品访问权限的帐户（例如不再隶属于组织的员工）。 </p> <p>相关主题：<a href="/help/admin/admin-console/user-management2/user-migration/migrate-enterprise.md">迁移 Analytics 用户帐户以使用 Enterprise ID 和 Federated ID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移会影响我的 Analytics 实施或数据的收集方式吗？ </p> </td> 
   <td colname="col2"> <p>不会。 </p> <p>现有的迁移工具可帮助您将用户 ID 和权限从 Analytics 用户管理过渡到 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移过程将持续多长时间？ </p> </td> 
   <td colname="col2"> <p>所有当前的 Analytics 管理员都将在迁移前四周收到一则预迁移通知电子邮件。（实际的开始日期将显示在 Analytics 界面中。） </p> <p>迁移开始后，管理员将有 60 天的时间来完成该过程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以加快迁移进度吗？ </p> </td> 
   <td colname="col2"> <p>可以。但是，Adobe 建议您利用迁移开始前的时间进行如下准备工作： </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">确认您是Adobe Admin Console中的Analytics产品管理员。 </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">与您的用户群沟通，告知他们的登录体验在迁移开始后将发生改变。 </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">审核您的当前用户和权限，并执行清理活动。 </li> 
    </ul> <p>要加快迁移进度，请在 <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html">Adobe 客户关怀</a>联系您的客户成功经理，并提交开始日期提前的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我是Analytics管理员，无权访问Adobe Admin Console。 谁能帮我进入Adobe Admin Console? </p> </td> 
   <td colname="col2"> <p>任何有权访问贵组织Adobe Admin Console的系统或产品管理员都可以授予您访问权限。 如果您不确定您的组织内有谁具有控制台中的管理员权限，请联系 <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我能推迟迁移开始日期吗？ </p> </td> 
   <td colname="col2"> <p>能。联系 <a href="https://helpx.adobe.com/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。 </p><p>有关在开始日期对当前 Analytics 用户和权限管理所做的更改的说明，请参见下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>现在，我的公司正在迁移到Adobe Admin Console，在迁移开始日期之前，我该在哪里创建新用户和权限组？ </p> </td> 
   <td colname="col2"> <p>在迁移开始日期之前，您可以在Adobe Admin Console或Analytics &gt;用户管理中创建用户。 </p> <p>迁移开始后，您只能在Adobe Admin Console中创建用户和权限组。 </p><p>有关在迁移开始日期将发生什么的更多详细信息，请参阅下方的“迁移”部分。 </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我什么时候可以使用联合 ID 实施单点登录？ </p> </td> 
   <td colname="col2"> <p> Adobe Admin Console中即将提供一个工具，通过该工具，您可以将ID类型从AdobeID更改为Federated ID。 在迁移期间，您无法将用户作为联合 ID 迁移。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 迁移期间的应知事项（常见问题解答） {#section-d394524aa6d046d79025bbd7499792bc}

关于迁移过程及它对当前用户管理的影响的重要信息。

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>权限组如何复制到Adobe Admin Console? 我的用户会怎样？ </p> </td> 
   <td colname="col2"> <p>迁移的Analytics组称为 <i>产品配置文件</i> 在Adobe Admin Console。 迁移中将保留原始组的权限设置。但是，将不会迁移被分配到组的用户。如果使用迁移工具迁移属于该组的用户，则此用户将被分配到该产品配置文件。 </p> <p>例如，一个“West Coast Operations”权限组若为其成员授予 Report Builder 和 Analysis Workspace（具有某些报表包、指标、维度）的权限，它将成为一个 West Coast Operations 产品配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以将迁移工作委派给其他管理员吗？ </p> </td> 
   <td colname="col2"> <p>在您的迁移开始后，任何可通过 Experience Cloud 访问 Analytics 实例的管理员，都能够使用迁移工具开始（或继续）迁移用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以更新未迁移用户的权限组成员资格吗？ </p> </td> 
   <td colname="col2"> <p>可以。您可以从“Analytics 用户管理”部分中更改未迁移用户的组成员资格。 </p><p>等待 Ashok 提供的关于何处已完成迁移的说明。 </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我能否在迁移开始后在Analytics中创建用户和权限组，然后使用迁移工具将他们移动到Adobe Admin Console? </p> </td> 
   <td colname="col2"> <p> 否。迁移开始后，必须在Adobe Admin Console中创建所有新用户和权限组(在Adobe Admin Console中称为产品配置文件)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用迁移工具迁移的用户会分配他们在 Analytics 中拥有的相同权限吗？ </p> </td> 
   <td colname="col2"> <p>是的。使用工具迁移的用户将被授予他们当前在 Analytics 中拥有的权限。此外，他们在通过 Experience Cloud 访问 Analytics 时，还将保留对其 Analytics 资产（如区段、项目、计算指标等等）的访问权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移到Adobe Admin Console的用户是否可以继续使用 <span class="filepath"> my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>可以。在迁移结束日期之前，迁移用户将能够继续使用其现有的用户名和密码经由 <span class="filepath">my.omniture.com</span> 访问 Analytics，除非您禁止他们通过迁移工具进行旧版登录访问。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的两名或更多用户在其 Analytics 记录中具有相同的电子邮件 ID。如果我迁移它们会怎样？ </p> </td> 
   <td colname="col2"> <p>由于Adobe Admin Console中的用户帐户需要唯一的电子邮件ID，因此当您尝试迁移多个这些用户时，会遇到“重复的电子邮件ID”错误。 在重新尝试迁移之前，您可以在“用户管理”（旧版）部分下方更新未迁移用户的电子邮件 ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 迁移我的用户之后该怎么做？ </p> </td> 
   <td colname="col2"> <p>禁止他们对 <span class="filepath">my.omniture.com</span> 的旧版登录访问。除非已迁移用户，否则将无法关闭旧版登录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以跟踪迁移过程吗？ </p> </td> 
   <td colname="col2"> <p>迁移工具包含一个功能板，可显示已成功迁移的用户数量，及其中已禁用旧版登录的用户数量。 </p> <p> 理想情况下，当100%的用户完成迁移并禁用其旧版登录时，您会将登录公司成功迁移到Adobe Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我需要在迁移期间执行用户和权限管理。我可以使用哪个工具执行此任务？ </p> </td> 
   <td colname="col2"> <p>迁移开始后，您将使用Adobe Admin Console创建和管理新用户和产品配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>当我使用工具迁移用户时，我的用户会遇到什么情况？ </p> </td> 
   <td colname="col2"> <p>他们将收到一封发送到 Analytics 用户记录中电子邮件 ID 的欢迎电子邮件，通知他们通过 Experience Cloud 访问 Analytics 的新方法。如果他们还没有 Adobe ID，系统将提示他们创建一个，在这之后，他们便能使用其 Adobe ID 访问解决方案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以使用 API 代替迁移工具来迁移我的用户吗？ </p> </td> 
   <td colname="col2"> <p>不可以。您必须使用迁移工具以确保所有现有用户都已迁移到Adobe Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>哪些Analytics用户管理功能在Adobe Admin Console中不可用？ </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">资产转移 </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">用户过期 </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">用户日志 </li> 
    </ul> <p>这些功能将在 Analytics 用户管理中保持可用状态。 </p> <p>请参阅 <a href="/help/admin/admin-console/user-management2/user-migration/c-migration-tool.md"> Adobe Admin Console中不支持的Analytics功能</a> 以了解更多信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我们在Adobe Admin Console中创建了多个配置，并将其映射到Analytics权限组。 这些配置在迁移开始后会出现什么情况？ </p> </td> 
   <td colname="col2"> <p>与所有其他组一样，Analytics权限组在Adobe Admin Console中重新创建为产品配置文件。 这意味着您将在控制台中看到两个实际上具有重复权限的产品配置文件。您可以从Adobe Admin Console中删除重复的产品配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我在迁移用户后下一步该怎么做？ </p> </td> 
   <td colname="col2"> <p>在迁移用户或一组用户后，下一步应该禁止他们通过 <span class="filepath">my.omniture.com</span> 进行旧版登录。为此，您可以在迁移工具中选择这些用户，并单击屏幕顶部显示的“禁用旧版登录”上下文选项。请注意，仅当您选择了所有已成功迁移到Adobe Admin Console的用户或用户集时，才会显示此选项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在迁移结束日期会发生什么？ </p> </td> 
   <td colname="col2"> <p>在迁移结束日期（自迁移开始起的 60 天）之后，将重定向登录公司内的所有用户以便使用其 Adobe ID 通过 Experience Cloud 登录页面登录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我未能在迁移结束日期前迁移我的所有用户。未迁移的用户会丢失对 Analytics 的访问权限吗？ </p> </td> 
   <td colname="col2"> <p>截止到结束日期还未被迁移的用户将被重定向到 Experience Cloud 登录页面 (experiencecloud.adobe.com)，并将无法访问 Analytics。但是，您将可以继续访问迁移工具，因此您可以查找并迁移他们以恢复其访问权限。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 迁移后的应知事项（常见问题解答） {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 解答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>从Adobe Admin Console中删除用户 </p> </td> 
   <td colname="col2"> <p> 在Analytics中，已删除的用户被设置为 <span class="term"> 过期</span>，但帐户仍然存在。 保留帐户可使转移资产（例如区段、计算指标、计划报表、项目等）得以进行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帐户过期日期 </p> </td> 
   <td colname="col2"> <p> 您可以在管理工具中手动设置 Analytics 中的帐户过期日期。在过期日期之后，用户将无法访问 Analytics，但其实际的 Experience Cloud 用户帐户（例如 Adobe ID、Enterprise ID、Federated ID 等）不会过期。他们仍然可以登录 Experience Cloud，但无法单击进入 Analytics。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Admin Console中不支持的Analytics功能 {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>检查以下可能会在迁移期间遇到的问题。

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 解答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>登录身份 </p> </td> 
   <td colname="col2"> <p> 迁移到Adobe Admin Console的管理员将无法再使用“登录方式”功能访问已迁移到Adobe Admin Console的非管理员用户帐户。 此功能即将在 Analytics 中弃用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户过期和资产转移 </p> </td> 
   <td colname="col2"> <p> Adobe Admin Console不支持用户过期或资产传输。 管理员将使用管理工具下方的“Analytics 用户和资产”部分来执行这两个功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次访问（上次登录） </p> </td> 
   <td colname="col2"> <p> 有关用户上次登录日期和时间的详细信息，将在Analytics用户和资产链接中提供，而不在Adobe Admin Console中提供。 Analytics 中的上次登录日期与用户从 Experience Cloud 内实际访问 Analytics 的时间有关，而不反映他们登录到 Experience Cloud 的日期/时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户管理 API <a href="https://helpx.adobe.com/cn/enterprise/help/identity.html">Adobe 支持的身份类型</a> </p> </td> 
   <td colname="col2"> <p> 迁移到Adobe Admin Console的管理员应配置<a href="https://developer.adobe.com/UMAPI/"> 用户管理API</a> 在Adobe Developer上提供，用于以编程方式访问Adobe Admin Console中的用户帐户。 </p> <p>为您启用迁移时将会关闭 Analytics 权限 API。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web 服务凭据 </p> </td> 
   <td colname="col2"> <p> 用户的Web服务凭据（及其共享密钥）将在Adobe Admin Console中不可用，并且可以通过从Analytics用户和资产部分单击特定用户来访问这些凭据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>单点登录 </p> </td> 
   <td colname="col2"> <p> 在完成迁移时，将删除 Analytics 单点登录配置。这些配置将在迁移期间保持活动状态。使用 Analytics 单点登录的客户应当升级到 <a href="https://helpx.adobe.com/enterprise/help/identity.html">Adobe 联合 ID</a>。 </p> <p>Analytics 建议您先将用户作为 Adobe ID 迁移，以便轻松创建 Experience Cloud 帐户，然后再将这些帐户转换为联合单点登录用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>下载权限组 </p> </td> 
   <td colname="col2"> <p> Analytics 管理工具或 Adobe Admin Console 中将不再支持下载权限组信息。客户应当使用 adobe.io 用户管理 API 批量获取权限组信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帐户创建日期 </p> </td> 
   <td colname="col2"> <p>Analytics 管理工具或 Adobe Admin Console 中将不再支持帐户创建日期信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>批量电子邮件 </p> </td> 
   <td colname="col2"> <p>Analytics管理工具或Adobe Admin Console将不再支持批量电子邮件发送给用户。 客户可以从 Adobe Admin Console 中批量导出其用户的电子邮件地址，并使用自己希望的任意电子邮件客户端发送电子邮件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何通知您的用户有关迁移的信息 {#section-f3b25f672a3a4d03b0559656fd99d20a}

您可能需要主动将此迁移计划传达给您的当前用户。以下是一个模板，您可以对其进行自定义，以发送给您的所有当前 Analytics 用户：

要向所有用户发送电子邮件，请导航到 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 用户管理]** > [向用户发送电子邮件](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/t-email-users.html)。

**主题：**&#x200B;即将推出 — 一种用于登录到 Adobe Analytics 和 Adobe Experience Cloud 的新方法。

**正文：** Adobe Analytics 用户，您好！

我们公司即将开始把所有 Adobe Analytics 帐户从 [!DNL https://my.omniture.com/login/] 迁移到 Adobe Experience Cloud ([experiencecloud.adobe.com](https://experiencecloud.adobe.com/))。在此次迁移中，将升级您的 Adobe Analytics 帐户以允许通过 Adobe Experience Cloud 访问 Analytics。虽然访问 Analytics 的方法将发生变化，但您对报表包和工具的所有现有权限都将保留下来。

**后续步骤：**&#x200B;我们将从以下日期开始迁移用户：**插入日期**。请查看发送到您 Analytics 帐户下方列出的电子邮件 ID 的欢迎邮件，其中包含您的新登录信息。如果您没有设置链接到电子邮件地址的 [Adobe ID](https://helpx.adobe.com/cn/x-productkb/global/adobe-id-account-change.html)，系统将要求您设置一个帐户。

**有用的资源：**

[登录并管理配置文件设置](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/manage-products.ug.html)。

如果您有任何问题或疑问，请联系您的 Analytics 管理员。

致以最诚挚的问候

Analytics 管理员
