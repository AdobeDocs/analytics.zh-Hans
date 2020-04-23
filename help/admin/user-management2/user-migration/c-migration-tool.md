---
description: 在 Adobe Experience Cloud 中将 Analytics 用户 ID 迁移到 Admin Console 的应知事项。
title: 将 Analytics 用户迁移到 Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# 将 Analytics 用户迁移到 Admin Console{#analytics-user-migration-to-the-admin-console}

在 Adobe Experience Cloud 中将 Analytics 用户 ID 迁移到 Admin Console 的应知事项。

要获取有关 Admin Console 主题的常规帮助（与 Analytics 迁移无关），请参阅 [Admin Console 用户指南](https://helpx.adobe.com/cn/enterprise/administering/user-guide.html)。

迁移后，您可以在 [Admin Console中管理Experience Cloud用户](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/manage-users-and-products/admin-getting-started.html) 和产品。

## 什么是Analytics用户ID迁移？ {#section-adbe49aba10c4e62afa836a97894107c}

通过Analytics用户ID迁移，管理员可以轻松地将Analytics用户管理中的用户帐户迁移到Adobe Admin Console。 迁移用户后，他们将有权访问Experience Cloud中提供的解决方案和核心服务。 迁移将分阶段向客户推出。

使用Admin Console的优势包括：

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 优势 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>单点登录 </p> </td> 
   <td colname="col2"> <p>Analytics用户可以使用其Adobe ID或Enterprise ID登录到Experience Cloud和所有解决方案。 此登录支持访问Experience Cloud中的集成解决方案和核心服务。 </p> <p>迁移后，尝试通过旧版登录（<span class="filepath">my.omniture.com</span> 和 <span class="filepath">sc.omniture.com</span>）进行登录的用户将被重定向至 <span class="filepath">experiencecloud.adobe.com</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理用户身份和权限 </p> </td> 
   <td colname="col2"> <p>Analytics 管理员可以在 <a href="http://adminconsole.adobe.com/enterprise/">Admin Console</a> (http://adminconsole.adobe.com/enterprise/) 中专门管理用户和权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理产品和核心服务 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">邀请新用户 </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">创建产品用户档案 </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">授予用户特定产品和服务的权限 </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">获取 Adobe Experience Cloud 中可用的<a href="https://docs.adobe.com/content/help/zh-Hans/core-services/interface/experience-cloud.html">跨解决方案核心服务</a>的访问权限。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 迁移用户 ID 前应知事项（和应做事项）（常见问题解答）{#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

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
   <td colname="col1"> <p>我是Analytics管理员，并收到一封迁移前电子邮件。 我先做什么？ </p> </td> 
   <td colname="col2"> <p>确认您具有 Adobe ID 并能够访问 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> <p>如果没有，请联系 <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。（您应当先联系邀请您加入相应的组织的系统或产品管理员。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM与Analytics集成 </p> </td> 
   <td colname="col2"> <p> 集成到Analytics的AEM用户需要更改其配置以使用Analytics共享机密而不是密码。 </p> <p> 您应该在启用迁移之前执行此操作。 一旦禁用迁移，最初配置的密码将不再有效。 </p> <p><b>在Analytics中获取共享机密</b> </p> <p> 共享密钥可以从 Analytics（<span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">用户管理</span>）获取，并且每个用户的共享密钥各不同。 </p> <p><b>使用共享密钥更新 AEM 配置</b> </p> <p>请参阅<a href="https://helpx.adobe.com/cn/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">连接到 Adobe Analytics 和创建框架</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新 Report Builder </p> </td> 
   <td colname="col2"> <p> <p>重要信息：将安装的 <a href="https://marketing.adobe.com/resources/help/zh_CN/arb/t_install_arb.html">Report Builder</a> 更新至最新版本。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移从何时开始？ </p> </td> 
   <td colname="col2"> <p>Adobe将通过电子邮件通知Analytics管理员，并说明迁移何时开始。 </p> <p>将在批次中向Admin Console进行迁移。 在迁移日，Adobe会通知Analytics管理员并授予他们对迁移工具的访问权限。 在登录公司满足为每个迁移浪潮定义的条件后，Adobe将： </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">设置公司迁移的开始和结束日期。 </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">在公司迁移前大约30天，向其当前Analytics管理员发送电子邮件通知。 </li> 
     <li id="li_476265B24CE2404B995201170C75D674">显示产品内通知，通知管理员迁移的开始日期。 </li> 
    </ul> <p> 在迁移当天，您以前的权限组将自动复制到Admin Console。 您将无法在 Analytics 管理工具中邀请新用户或创建新群组。 </p> <p>迁移后： </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">管理员将使用Admin Console管理其Analytics用户和权限。 （您将不再使用“分析”&gt;“管理员”&gt;“用户管理”中的用户管理界面。） </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">用户将使用其 Adobe ID 或 Enterprise ID 通过 Experience Cloud 访问 Analytics，而不是通过 <span class="filepath">my.omniture.com</span> 来访问。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移的开始日期会发生什么？ </p> </td> 
   <td colname="col2"> <p>在开始日期的UTC上午10:00: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">您在Analytics中的现有权限组将作为产品用户档案自动在Admin Console中复制，包括其描述以及跨报表包、量度、维度、分析和报表包工具的粒度权限。 </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">如果您当前的任何Analytics用户是在Admin Console中创建的（这意味着他们拥有关联的Adobe/Enterprise ID），他们将添加到Admin Console中相应的产品用户档案。 </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Analytics中“管理员”选项卡下的“用户管理”部分将设置为 <span class="term"> 只读</span>。 您将无法在此处创建新用户或权限组，并将需要在 Admin Console 中执行这两个功能。有关更多信息，请参阅 <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Admin Console 中不支持的 Analytics 功能</a>。 </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">管理员将授予您对用户ID迁移工 <a href="https://marketing.adobe.com/resources/help/zh_CN/experience-cloud/admin-console/analytics-migration/t_migrate-users.html">具的访问权限</a>。 此外，还会显示产品内通知，其中除了帮助内容和常见问题解答的链接之外，还包括迁移的结束日期（通常为将来60天）。 </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">您将获得对Admin Console中的“权限”选项卡的访问权限，该选项卡允许您使用您在Analytics中熟悉的所有粒度选项创建产品用户档案。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如何迁移用户ID? </p> </td> 
   <td colname="col2"> <p> Click <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrate User IDs</a> on the Admin page, under User Management. 使用该工具可将用户添加到Admin Console中的产品用户档案（从Analytics中的权限组复制）。 您可以按自己的进度迁移用户ID。 </p> <p>需要管理员权限。 迁移完成后，将无法颠倒。 </p> <p>在迁移结束当天，将禁用登录公司中用户对 <span class="filepath">my.omniture.com</span> 的访问。用户（包括那些尚未迁移的用户）将被重定向，以便通过新的 Experience Cloud URL (<span class="filepath">experiencecloud.adobe.com</span>) 登录 </p> <p>注意：Adobe 建议您利用这个机会在迁移之前对用户和组进行审核。删除旧的和未使用的帐户，或不再具有产品访问权限的帐户（例如不再隶属于组织的员工）。 </p> <p>相关主题：<a href="/help/admin/user-management2/user-migration/migrate-enterprise.md">为 Enterprise ID 和 Federated ID 迁移 Analytics 用户帐户</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移会影响我的Analytics实施或数据的收集方式吗？ </p> </td> 
   <td colname="col2"> <p>否. </p> <p>现有的迁移工具可帮助您将用户 ID 和权限从 Analytics 用户管理过渡到 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移过程需要多长时间？ </p> </td> 
   <td colname="col2"> <p>所有当前Analytics管理员在迁移前四周将收到一封迁移前通知电子邮件。 (实际开始日期将显示在Analytics界面中。) </p> <p>迁移开始后，管理员将有60天时间完成该过程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我能否加快迁移？ </p> </td> 
   <td colname="col2"> <p>可以。但是，Adobe建议您使用迁移开始前的时间： </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">验证您是Admin Console中的Analytics产品管理员。 </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">向您的用户群传达，在迁移开始时，他们的登录体验将发生更改。 </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">审核当前用户和权限并执行清理活动。 </li> 
    </ul> <p>要加快迁移进度，请在 <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Adobe 客户关怀</a>联系您的客户成功经理，并提交开始日期提前的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我是Analytics管理员，无权访问Admin Console。 谁可以帮助我访问Admin Console? </p> </td> 
   <td colname="col2"> <p>任何有权访问贵组织 Admin Console 的系统或产品管理员都可以为您提供访问权限。如果您不确定您的组织内有谁具有控制台中的管理员权限，请联系 <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我能推迟迁移开始日期吗？ </p> </td> 
   <td colname="col2"> <p>能。联系 <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。 </p> 
    <draft-comment> 
     <p>有关在开始日期对当前 Analytics 用户和权限管理所做的更改的说明，请参见下文。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>现在我的公司正在迁移到Admin Console，在迁移的开始日期之前，我应在何处创建新用户和权限组？ </p> </td> 
   <td colname="col2"> <p>在迁移开始日期之前，您可以在Admin Console中或在“Analytics”&gt;“用户管理”中创建用户。 </p> <p>迁移开始后，您只能在Admin Console中创建用户和权限组。 </p> 
    <draft-comment> 
     <p>请参阅下面的“迁移”部分，以了解有关迁移开始日期所发生情况的详细信息）。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我何时可以使用Federated ID实现单点登录？ </p> </td> 
   <td colname="col2"> <p> Admin Console中即将推出一个工具，它允许您将ID类型从Adobe ID更改为Federated ID。 在迁移过程中，您不能将用户作为Federated ID进行迁移。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 迁移过程中要了解的内容（常见问题解答） {#section-d394524aa6d046d79025bbd7499792bc}

有关迁移过程及其如何影响当前用户管理的重要信息。

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>如何将权限组复制到Admin Console? 我的用户呢？ </p> </td> 
   <td colname="col2"> <p>迁移的Analytics组在Admin Console中称为 <i>产品用户档案</i> 。 迁移中将保留原始组的权限设置。 但是，不会迁移分配给该组的用户。 当使用迁移工具迁移属于该组的用户时，该用户将被分配到该产品用户档案。 </p> <p>例如，授权其成员使用Report Builder和分析工作区（包含某些报表包、度量、维度）的“西海岸操作”权限组将成为“西海岸操作”产品用户档案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我是否可以将迁移工作委派给其他管理员？ </p> </td> 
   <td colname="col2"> <p>迁移开始后，任何通过Experience Cloud访问您的Analytics实例的管理员都可以使用迁移工具开始（或继续）迁移用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我是否可以为未迁移的用户更新权限组成员关系？ </p> </td> 
   <td colname="col2"> <p>可以。您可以从“分析用户管理”部分更改未迁移用户的用户组成员关系。 </p> 
    <draft-comment> 
     <p>等待 Ashok 提供的关于何处已完成迁移的说明。 </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我是否可以在迁移开始后在Analytics中创建用户和权限组，然后使用迁移工具将其移至Admin Console? </p> </td> 
   <td colname="col2"> <p> 不会。迁移开始后，必须在Admin Console中创建所有新用户和权限组(在Admin Console中称为产品用户档案)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我使用迁移工具迁移的用户是否会获得与Analytics中相同的权限？ </p> </td> 
   <td colname="col2"> <p>是的。使用该工具迁移的用户将获得他们在Analytics中当前拥有的权限。 此外，当他们通过Experience Cloud访问Analytics时，他们将保留对其Analytics资产（如区段、项目、计算量度等）的访问权。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移到 Admin Console 的用户可继续使用 <span class="filepath">my.omniture.com</span> 访问 Analytics 吗？ </p> </td> 
   <td colname="col2"> <p>可以。在迁移结束日期之前，迁移用户将能够继续使用其现有的用户名和密码经由 <span class="filepath">my.omniture.com</span> 访问 Analytics，除非您禁止他们通过迁移工具进行旧版登录访问。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的两个或两个以上用户的Analytics记录中具有相同的电子邮件ID。 如果我迁移它们，会发生什么情况？ </p> </td> 
   <td colname="col2"> <p>由于Admin Console中的用户帐户需要唯一的电子邮件ID，因此，当您尝试迁移多个这些用户时，您会遇到“重复电子邮件ID”错误。 在重试迁移之前，您可以在“用户管理（旧版）”部分下更新未迁移用户的电子邮件ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 迁移用户后我该怎么办？ </p> </td> 
   <td colname="col2"> <p>禁止他们对 <span class="filepath">my.omniture.com</span> 的旧版登录访问。除非已迁移旧版登录，否则您将无法关闭旧版登录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>能否跟踪迁移过程？ </p> </td> 
   <td colname="col2"> <p>迁移工具包含一个仪表板，显示成功迁移的用户数，以及已禁用旧版登录的用户数。 </p> <p> 理想情况下，当100%的用户完成迁移并禁用其旧版登录时，您将成功将登录公司迁移到Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在迁移过程中，我需要执行用户和权限管理。 我可以使用哪个工具执行此任务? </p> </td> 
   <td colname="col2"> <p>迁移开始后，您将使用Admin Console创建和管理新用户和产品用户档案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用该工具迁移用户时，我的用户会体验到什么？ </p> </td> 
   <td colname="col2"> <p>他们将收到一封欢迎电子邮件，其地址位于其Analytics用户记录中的电子邮件ID，通知他们通过Experience Cloud访问Analytics的新方式。 如果他们没有现有的Adobe ID，将提示他们创建一个，然后他们可以使用自己的Adobe ID访问解决方案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我是否可以使用API迁移我的用户而不是使用迁移工具？ </p> </td> 
   <td colname="col2"> <p>不会。您必须使用迁移工具来确保将所有现有用户迁移到Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console中不提供哪些Analytics用户管理功能？ </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">资产转让 </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">用户过期 </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">用户日志 </li> 
    </ul> <p>Analytics用户管理中仍将提供这些功能。 </p> <p>有关更多信息，请参阅 <a href="/help/admin/user-management2/user-migration/c-migration-tool.md">Admin Console 中不支持的 Analytics 功能</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我们在Admin Console中创建了多个配置，并将它们映射到Analytics权限组。 迁移开始后，这些配置会发生什么情况？ </p> </td> 
   <td colname="col2"> <p>Analytics权限组在Admin Console中重新创建为产品用户档案，就像您的所有其他组一样。 这意味着您将在控制台中看到两个实质上具有用户档案权限的产品重复。 您可以从Admin Console中删除重复产品用户档案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移用户后，我的下一步是什么？ </p> </td> 
   <td colname="col2"> <p>在迁移用户或一组用户后，下一步应该禁止他们通过 <span class="filepath">my.omniture.com</span> 进行旧版登录。为此，您可以在迁移工具中选择这些用户，然后单击屏幕顶部显示的上下文“禁用旧版登录名”选项。 请注意，仅当您选择所有已成功迁移到Admin Console的用户或用户集时，此选项才可见。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移结束日期会发生什么情况？ </p> </td> 
   <td colname="col2"> <p>迁移结束日期(迁移开始后60天)后，登录公司内的所有用户都将被重定向到使用其Adobe ID通过Experience Cloud登录页面登录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我未能在迁移结束日期前迁移所有用户。 未迁移的用户是否会失去对Analytics的访问权？ </p> </td> 
   <td colname="col2"> <p>截止到结束日期还未被迁移的用户将被重定向到 Experience Cloud 登录页面 (experiencecloud.adobe.com)，并将无法访问 Analytics。但是，您将可以继续访问迁移工具，因此您可以查找并迁移他们以恢复其访问权限。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 迁移后要了解的内容（常见问题解答） {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题／问题 </th> 
   <th colname="col2" class="entry"> 答案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>从Admin Console中删除用户 </p> </td> 
   <td colname="col2"> <p> 在Analytics中，已删除的用户设置为 <span class="term"> 过期</span>，但帐户仍然存在。 保留帐户可转移资产，如区段、计算量度、计划报告、项目等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帐户过期 </p> </td> 
   <td colname="col2"> <p> 您可以在管理工具的Analytics中手动设置帐户过期日期。 到期日期到期后，用户将无法访问Analytics，但无法访问其实际的Experience Cloud用户帐户（例如Adobe ID、Enterprise ID、Federated ID，等等）不会过期。 他们仍可以登录Experience Cloud，但无法单击Analytics。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Admin Console 中不支持的 Analytics 功能 {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>检查以下可能会在迁移期间遇到的问题。

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题／问题 </th> 
   <th colname="col2" class="entry"> 答案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>登录方式 </p> </td> 
   <td colname="col2"> <p> 迁移到Admin Console的管理员将无法再使用“登录方式”功能访问已迁移到Admin Console的非管理员用户帐户。 此功能在Analytics中已弃用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户过期和资产转让 </p> </td> 
   <td colname="col2"> <p> Admin Console不支持用户过期或资产转让。 管理员将在Analytics中的管理工具下使用Analytics的“用户和资产”部分，以实现这两个功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次访问（上次登录） </p> </td> 
   <td colname="col2"> <p> 有关用户上次登录日期和时间的详细信息将显示在“分析用户和资产”链接中，而不在Admin Console中。 Analytics 中的上次登录日期与用户从 Experience Cloud 内实际访问 Analytics 的时间有关，而不反映他们登录到 Experience Cloud 的日期/时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户管理 API <a href="https://helpx.adobe.com/cn/enterprise/help/identity.html">Adobe 支持的身份类型</a> </p> </td> 
   <td colname="col2"> <p> 迁移到 Admin Console 的管理员应当配置在 Adobe I/O 提供的<a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">用户管理 API</a>，以便在 Admin Console 中以编程方式访问用户帐户。 </p> <p>启用迁移后，将关闭Analytics权限API。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web 服务凭据 </p> </td> 
   <td colname="col2"> <p> 用户的Web服务凭据（及其共享机密）将不在Admin Console中可用，并可通过单击“Analytics用户和资产”部分中的特定用户来访问这些凭据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>单点登录 </p> </td> 
   <td colname="col2"> <p> 完成迁移后，将删除分析单点登录配置。 在迁移期间，这些组件将保持活动状态。 使用 Analytics 单点登录的客户应当升级到 <a href="https://helpx.adobe.com/cn/enterprise/help/identity.html">Adobe 联合 ID</a>。 </p> <p>Analytics建议您首先将用户作为Adobe ID进行迁移，以便轻松创建Experience Cloud帐户，然后将这些帐户转换为联合单点签名用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>下载权限组 </p> </td> 
   <td colname="col2"> <p> Analytics管理工具或Adobe Admin Console不再支持下载权限组信息。 客户应使用adobe.io用户管理API批量获取权限组信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帐户创建日期 </p> </td> 
   <td colname="col2"> <p>帐户创建日期信息在Analytics管理工具或Adobe Admin Console中不再受支持。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>批量电子邮件 </p> </td> 
   <td colname="col2"> <p>在Analytics Admin Console或Adobe Admin Console中，不再支持向用户批量发送电子邮件。 客户可以从Adobe Admin Console批量导出其用户的电子邮件地址，并使用他们希望的任何电子邮件客户端发送电子邮件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何通知您的用户有关迁移的信息 {#section-f3b25f672a3a4d03b0559656fd99d20a}

您可能希望主动将此迁移计划与您的当前用户进行沟通。 以下是可自定义的模板，用于发送所有当前Analytics用户：

要向所有用户发送电子邮件，请导航到 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** >电子邮 [件用户](https://marketing.adobe.com/resources/help/zh_CN/reference/t_email_users.html)。

**主题：**&#x200B;即将推出 - 一种用于登录到 Adobe Analytics 和 Adobe Experience Cloud 的新方法。

**正文：** Adobe Analytics 用户，您好！

我们公司即将开始把所有 Adobe Analytics 帐户从 [!DNL https://my.omniture.com/login/] 迁移到 Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/))。通过此迁移，您的Adobe Analytics帐户将得到升级，以便通过Adobe Experience Cloud访问Analytics。 虽然访问Analytics的方法将发生更改，但您对报表包和工具的所有现有权限都将保留。

**后续步骤：**&#x200B;我们将从以下日期开始迁移用户：**插入日期**。观看欢迎消息，新登录名将发送到分析帐户下列出的电子邮件ID。 如果您尚未设置链接到 [您的电子邮件地址](https://helpx.adobe.com/cn/x-productkb/global/adobe-id-account-change.html) ，系统会要求您设置帐户。

**有用资源：**

[登录并管理配置文件设置](https://marketing.adobe.com/resources/help/zh_CN/mcloud/getting-started-experience-cloud.html).

[关于Experience Cloud中的云、核心服务](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html) 和解决方案

如果您有任何问题或疑虑，请与Analytics管理员联系。

最好，

Analytics 管理员
