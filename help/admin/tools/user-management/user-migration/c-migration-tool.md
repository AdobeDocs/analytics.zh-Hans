---
description: 在 Adobe Experience Cloud 中将 Analytics 用户 ID 迁移到 Admin Console 的应知事项。
title: 将 Analytics 用户迁移到 Admin Console
feature: Admin Tools
exl-id: f4bc0e92-af53-40db-8138-44d29e4b25fe
role: Admin
TQID: https://experienceleague.adobe.com/bCf6DWIpIVALcGPAi3tL8zlZ5V8lzPR-9XNCm4HuFnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
  - id: e499b847-6dc4-408a-9f0b-70d35ce9b711
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 2971
ht-degree: 61%

---

# 将 Analytics 用户迁移到 Adobe Admin Console{#analytics-user-migration-to-the-admin-console}

在 Adobe Experience Cloud 中将 Analytics 用户 ID 迁移到 Adobe Admin Console 的应知事项。

要获取有关 Adobe Admin Console 主题的常规帮助（与 Analytics 迁移无关），请参阅 [Admin Console 用户指南](https://helpx.adobe.com/cn/enterprise/administering/user-guide.html)。

迁移后，您可以在 Adobe Admin Console 中[管理 Experience Cloud 用户和产品](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

## 什么是Analytics用户ID迁移？ {#section-adbe49aba10c4e62afa836a97894107c}

通过 Analytics 用户 ID 迁移，管理员可以轻松地将 Analytics User Management 中的用户帐户迁移到 Adobe Admin Console。 迁移用户后，他们将有权访问Experience Cloud中提供的解决方案和核心服务。 迁移过程将分阶段向客户推出。

使用 Adobe Admin Console 的好处包括：

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
   <td colname="col2"> <p>Analytics用户可以使用其Adobe ID或Enterprise ID登录到Experience Cloud和所有解决方案。 此登录允许访问Experience Cloud中的集成解决方案和核心服务。 </p> <p>迁移后，尝试通过旧版登录（<span class="filepath">my.omniture.com</span> 和 <span class="filepath">sc.omniture.com</span>）进行登录的用户将被重定向至 <span class="filepath">experiencecloud.adobe.com</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理用户身份标识和权限 </p> </td> 
   <td colname="col2"> <p>Analytics 可专门在 <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> 中管理用户和权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>管理产品和核心服务 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">邀请新用户 </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">创建产品轮廓 </li> 
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
   <td colname="col1"> <p>我是一名Analytics管理员，并收到了一封迁移前电子邮件。 我先做什么？ </p> </td> 
   <td colname="col2"> <p>确认您具有 Adobe ID 并能够访问 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> <p>如果没有，请联系 <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。 （您应当先联系邀请您加入相应的组织的系统或产品管理员。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AEM与Analytics的集成 </p> </td> 
   <td colname="col2"> <p> 与Analytics集成的AEM用户需要更改其配置以使用Analytics共享密钥而不是密码。 </p> <p> 您应在启用迁移之前执行此操作。 禁用迁移后，最初配置的密码将不再有效。 </p> <p><b>在Analytics中获取共享密钥</b> </p> <p> 共享密钥可以从 Analytics（<span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">用户管理</span>）获取，并且每个用户的共享密钥各不同。 </p> <p><b>使用共享密钥更新 AEM 配置</b> </p> <p>请参阅<a href="https://helpx.adobe.com/cn/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">连接到 Adobe Analytics 和创建框架</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新 Report Builder </p> </td> 
   <td colname="col2"> <p> <p>重要信息：将安装的 <a href="/help/analyze/report-builder/report-builder-setup.md">Report Builder</a> 更新至最新版本。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移何时开始？ </p> </td> 
   <td colname="col2"> <p>Adobe将通过电子邮件通知Analytics管理员，告知他们何时开始迁移。 </p> <p>向 Adobe Admin Console 的迁移将分批次进行。 在迁移当天，Adobe会通知Analytics管理员，并授予他们访问迁移工具的权限。 登录公司达到为每个迁移阶段定义的标准后，Adobe将： </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">设置公司迁移的开始和结束日期。 </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">在迁移大约30天前，向公司的当前Analytics管理员发送电子邮件通知。 </li> 
     <li id="li_476265B24CE2404B995201170C75D674">显示产品内通知，通知管理员迁移的开始日期。 </li> 
    </ul> <p> 在迁移当日，您以前的权限组将被自动复制到 Adobe Admin Console。 您将无法在 Analytics 管理工具中邀请新用户或创建新群组。 </p> <p>迁移后： </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">管理员将使用 Adobe Admin Console 管理他们的 Analytics 用户和权限。 （您将无法在“Analytics”&gt;“管理员”&gt;“用户管理”中使用用户管理界面。） </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">用户将使用其 Adobe ID 或 Enterprise ID 通过 Experience Cloud 访问 Analytics，而不是通过 <span class="filepath">my.omniture.com</span> 来访问。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>从迁移开始日期起会出现什么情况？ </p> </td> 
   <td colname="col2"> <p>迁移开始日期上午10:00(UTC)： </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">您在 Analytics 中的现有权限组将作为产品配置文件自动复制到 Adobe Admin Console 中，其中包括它们的描述以及报表包、量度、维度、Analytics 与报表包工具之间的粒度权限。 </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">如果您有任何当前 Analytics 用户是在 Adobe Admin Console 中创建的（这表示他们具有链接的 Adobe/Enterprise ID），他们将被添加到 Adobe Admin Console 中相应的产品配置文件内。 </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">Analytics 中“管理员”选项卡下方的“用户管理”部分将被设置为<span class="term">只读</span>。 您将无法在此处创建新用户或权限组，并需要在 Adobe Admin Console 中执行这两个功能。 有关更多信息，请参阅 <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Adobe Admin Console 中不支持的 Analytics 功能</a>。 </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">将准许管理员访问<a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">用户 ID 迁移工具</a>。 此外，还会显示一则产品内通知，其中包含迁移的结束日期（通常是未来 60 天）以及帮助内容和常见问题解答的链接。 </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">您将在 Adobe Admin Console 中获得“权限”选项卡的访问权限，以便您可以使用 Analytics 中所有熟悉的粒度选项创建产品配置文件。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如何迁移用户ID？ </p> </td> 
   <td colname="col2"> <p> 在“管理”页面的“用户管理”下，单击<a href="/help/admin/tools/user-management/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9">迁移用户ID</a>。 使用该工具将用户添加到 Adobe Admin Console 中的产品配置文件（从 Analytics 的权限组中复制）。 您可以按照自己的步调迁移用户ID。 </p> <p>需要管理权限。 迁移完成后，将无法撤销。 </p> <p>在迁移结束当天，将禁用登录公司中用户对 <span class="filepath">my.omniture.com</span> 的访问。 用户（包括那些尚未迁移的用户）将被重定向，以便通过新的 Experience Cloud URL (<span class="filepath">experiencecloud.adobe.com</span>) 登录 </p> <p>注意：Adobe 建议您利用这个机会在迁移之前对用户和组进行审核。 删除旧的和未使用的帐户，或不再具有产品访问权限的帐户（例如不再隶属于组织的员工）。 </p> <p>相关主题：<a href="/help/admin/tools/user-management/user-migration/migrate-enterprise.md">迁移 Analytics 用户帐户以使用 Enterprise ID 和 Federated ID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移是否会影响我的Analytics实施或数据收集方式？ </p> </td> 
   <td colname="col2"> <p>不会。 </p> <p>现有的迁移工具可帮助您将用户 ID 和权限从 Analytics 用户管理过渡到 <a href="https://adminconsole.adobe.com/enterprise/">Experience Cloud Admin Console</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移过程需要多长时间？ </p> </td> 
   <td colname="col2"> <p>所有当前的Analytics管理员都将在迁移的四周前收到一封迁移前通知电子邮件。 （实际开始日期将显示在Analytics界面中。） </p> <p>迁移开始后，管理员有60天的时间来完成该过程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以加快迁移过程吗？ </p> </td> 
   <td colname="col2"> <p>是的。 但是，Adobe建议您使用迁移开始前的时间： </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">确认您是 Adobe Admin Console 中的 Analytics 产品管理员。 </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">告知您的用户群，他们的登录体验将在迁移开始时发生变化。 </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">审核当前用户和权限并执行清理活动。 </li> 
    </ul> <p>要加快迁移进度，请通过<a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html"> Adobe客户关怀</a>联系您的Adobe客户团队，并提交开始日期提前的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我是 Analytics 管理员但没有 Adobe Admin Console 访问权限。 谁能帮助我获取 Adobe Admin Console 的访问权限？ </p> </td> 
   <td colname="col2"> <p>任何有权访问您组织的 Adobe Admin Console 的系统或产品管理员都可以为您提供访问权限。 如果您不确定您的组织内有谁具有控制台中的管理员权限，请联系 <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我能推迟迁移开始日期吗？ </p> </td> 
   <td colname="col2"> <p>是的。 联系 <a href="https://helpx.adobe.com/cn/marketing-cloud/contact-support.html">Adobe 客户关怀</a>。 </p><p>有关在开始日期对当前 Analytics 用户和权限管理所做的更改的说明，请参见下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的公司当前正在迁移到 Adobe Admin Console，我在迁移开始日期之前应在何处创建新用户和权限组？ </p> </td> 
   <td colname="col2"> <p>在迁移开始日期之前，您可以在 Adobe Admin Console 中或在“Analytics”&gt;“用户管理”中创建用户。 </p> <p>在迁移开始后，您只能在 Adobe Admin Console 中创建用户和权限组。 </p><p>有关在迁移开始日期将发生什么的更多详细信息，请参阅下方的“迁移”部分。 </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 我什么时候可以使用 Federated ID 实施单点登录？ </p> </td> 
   <td colname="col2"> <p> Adobe Admin Console 中即将推出一个工具，允许您将 ID 类型从 Adobe ID 更改为 Federated ID。 在迁移期间，您无法以Federated ID迁移用户。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 迁移期间应了解的事项（常见问题解答） {#section-d394524aa6d046d79025bbd7499792bc}

有关迁移过程及其对当前用户管理的影响的重要信息。

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>权限组将如何复制到 Adobe Admin Console？ 我的用户会怎样？ </p> </td> 
   <td colname="col2"> <p>迁移的 Analytics 组在 Adobe Admin Console 中称为<i>产品配置文件</i>。 原始组的权限设置将保留在迁移中。 但是，分配给该组的用户不会迁移。 使用迁移工具迁移属于该组的用户时，会将该用户分配给该产品配置文件。 </p> <p>例如，一个“West Coast Operations”权限组若为其成员授予 Report Builder 和 Analysis Workspace（具有某些报表包、指标、维度）的权限，它将成为一个 West Coast Operations 产品配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我是否可以将迁移工作委派给其他管理员？ </p> </td> 
   <td colname="col2"> <p>迁移开始后，任何通过Experience Cloud访问Analytics实例的管理员都可以使用迁移工具开始（或继续）迁移用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>能否更新未迁移用户的权限组成员资格？ </p> </td> 
   <td colname="col2"> <p>是的。 您可以从Analytics用户管理部分更改未迁移用户的组成员资格。 </p><p>等待 Ashok 提供的关于何处已完成迁移的说明。 </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我可以在迁移开始后在 Analytics 中创建用户和权限组，然后使用迁移工具将它们移到 Adobe Admin Console 吗？ </p> </td> 
   <td colname="col2"> <p> 否。 迁移开始后，所有新用户和权限组（在 Adobe Admin Console 中称为“产品配置文件”）必须在 Adobe Admin Console 中创建。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我使用迁移工具迁移的用户是否会分配在Analytics中拥有的相同权限？ </p> </td> 
   <td colname="col2"> <p>是的。 使用该工具迁移的用户将获得他们当前在Analytics中的权限。 此外，他们在通过 Experience Cloud 访问 Analytics 时，还将保留对其 Analytics 资产（如区段、项目、计算指标等等）的访问权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>迁移到 Adobe Admin Console 的用户可继续使用 <span class="filepath">my.omniture.com</span> 访问 Analytics 吗？ </p> </td> 
   <td colname="col2"> <p>是的。 在迁移结束日期之前，迁移用户将能够继续使用其现有的用户名和密码经由 <span class="filepath">my.omniture.com</span> 访问 Analytics，除非您禁止他们通过迁移工具进行旧版登录访问。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我的两个或更多用户在其Analytics记录中具有相同的电子邮件ID。 如果我迁移这些客户会发生什么情况？ </p> </td> 
   <td colname="col2"> <p>由于 Adobe Admin Console 中的用户帐户需要唯一电子邮件 ID，因此当您尝试迁移多个此类用户时将遇到“重复的电子邮件 ID”错误。 在重试迁移之前，您可以在用户管理（旧版）部分下更新未迁移用户的电子邮件ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 迁移用户后我该怎么做？ </p> </td> 
   <td colname="col2"> <p>禁止他们对 <span class="filepath">my.omniture.com</span> 的旧版登录访问。 除非旧登录已迁移，否则您将无法关闭旧登录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我是否可以跟踪迁移过程？ </p> </td> 
   <td colname="col2"> <p>迁移工具包括一个功能板，其中显示有多少用户已成功迁移，以及其中有多少用户的旧登录已被禁用。 </p> <p> 理想情况下，当您所有的用户都已完成迁移并禁用其旧版登录时，即表示已成功将登录公司迁移到 Adobe Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在迁移过程中，我需要执行用户和权限管理。 我可以使用哪个工具来执行此任务？ </p> </td> 
   <td colname="col2"> <p>在迁移开始后，您将使用 Adobe Admin Console 创建并管理新用户和产品配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>当我使用该工具迁移用户时，他们会有什么体验？ </p> </td> 
   <td colname="col2"> <p>他们将在Analytics用户记录中收到一封发送到电子邮件ID的欢迎电子邮件，通知他们通过Experience Cloud访问Analytics的新方式。 如果他们没有现有的Adobe ID，则系统将提示他们创建一个，之后他们可以使用其Adobe ID访问解决方案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我能否使用API而不是迁移工具来迁移用户？ </p> </td> 
   <td colname="col2"> <p>否。 您必须使用迁移工具，确保您所有现有用户都能被迁移到 Adobe Admin Console。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>哪些 Analytics 用户管理功能在 Adobe Admin Console 中不可用？ </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">资产转移 </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">用户过期 </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">用户日志 </li> 
    </ul> <p>您在Analytics用户管理中仍可以保留这些设置。 </p> <p>有关更多信息，请参阅 <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">Adobe Admin Console 中不支持的 Analytics 功能</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我们在 Adobe Admin Console 中创建了几个配置并将它们映射到 Analytics 权限组。 这些配置在迁移开始后会出现什么情况？ </p> </td> 
   <td colname="col2"> <p>Analytics 权限组在 Adobe Admin Console 中被重新创建为产品配置文件，这与您所有其他的组一样。 这意味着您将在控制台中看到两个实际上具有重复权限的产品配置文件。 您可以从 Adobe Admin Console 中删除重复的产品配置文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>我在迁移用户后下一步该怎么做？ </p> </td> 
   <td colname="col2"> <p>在迁移用户或一组用户后，下一步应该禁止他们通过 <span class="filepath">my.omniture.com</span> 进行旧版登录。 为此，您可以在迁移工具中选择这些用户，并单击屏幕顶部显示的“禁用旧版登录”上下文选项。 请注意，此选项仅在您选择了一名或一组被成功迁移到 Adobe Admin Console 的用户时才可见。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在迁移结束日期会发生什么？ </p> </td> 
   <td colname="col2"> <p>迁移结束日期后（从迁移开始算起60天），登录公司内的所有用户都将被重定向，以便使用他们的Adobe ID通过Experience Cloud登录页面进行登录。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在迁移结束日期之前，我无法迁移所有用户。 未迁移的用户是否会失去对Analytics的访问权限？ </p> </td> 
   <td colname="col2"> <p>截止到结束日期还未被迁移的用户将被重定向到 Experience Cloud 登录页面 (experiencecloud.adobe.com)，并将无法访问 Analytics。 但是，您将可以继续访问迁移工具，因此您可以查找并迁移他们以恢复其访问权限。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 迁移后须知（常见问题解答） {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题/问题 </th> 
   <th colname="col2" class="entry"> 答案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>从 Adobe Admin Console 中删除用户 </p> </td> 
   <td colname="col2"> <p> 在 Analytics 中，已删除的用户被设置为 <span class="term">过期</span>，但该帐户仍然存在。 保留帐户可使转移资产（例如区段、计算指标、计划报表、项目等）得以进行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帐户过期 </p> </td> 
   <td colname="col2"> <p> 您可以在“管理工具”的Analytics中手动设置帐户到期日期。 过期日期过后，用户将无法访问Analytics，而只能访问他们实际的Experience Cloud用户帐户（例如Adobe ID、Enterprise ID、Federated ID等） 不会过期。 他们仍可以登录Experience Cloud，只是无法单击Analytics。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Admin Console 中不支持的 Analytics 功能 {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>检查以下可能会在迁移期间遇到的问题。

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题/问题 </th> 
   <th colname="col2" class="entry"> 答案 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>登录身份 </p> </td> 
   <td colname="col2"> <p> 迁移到 Adobe Admin Console 的管理员将不能再使用“登录身份”功能访问已迁移到 Adobe Admin Console 的非管理员用户帐户。 此功能已停用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户到期和资产转移 </p> </td> 
   <td colname="col2"> <p> Adobe Admin Console 不支持用户过期或资产转移。 管理员将使用Analytics中的管理工具下的Analytics用户和Assets部分来实现这两个功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次访问（上次登录） </p> </td> 
   <td colname="col2"> <p> 有关用户上次登录日期和时间的详细信息将显示在“Analytics 用户和资产”链接中，而不是显示在 Adobe Admin Console 中。 Analytics 中的上次登录日期与用户从 Experience Cloud 内实际访问 Analytics 的时间有关，而不反映他们登录到 Experience Cloud 的日期/时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户管理 API <a href="https://helpx.adobe.com/cn/enterprise/help/identity.html">Adobe 支持的身份标识类型</a> </p> </td> 
   <td colname="col2"> <p> 迁移到Adobe Admin Console的管理员应当配置在Adobe Developer上提供的用户管理API ，以便在Adobe Admin Console中以编程方式访问用户帐户。 </p> <p>当您启用迁移功能后，Analytics权限API将会关闭。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Web 服务凭据 </p> </td> 
   <td colname="col2"> <p> 用户的 Web 服务凭据（及其共享密钥）将在 Adobe Admin Console 中不可用，并可通过单击“Analytics 用户和资产”部分中的特定用户来访问。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>单点登录 </p> </td> 
   <td colname="col2"> <p> 完成迁移后，Analytics单点登录配置将被删除。 迁移期间，它们将保持活动状态。 使用 Analytics 单点登录的客户应当升级到 <a href="https://helpx.adobe.com/cn/enterprise/help/identity.html">Adobe 联合 ID</a>。 </p> <p>Analytics建议您首先以Adobe ID迁移用户，以便轻松创建Experience Cloud帐户，然后将这些帐户转换为Federated Single-sign用户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>正在下载权限组 </p> </td> 
   <td colname="col2"> <p> Analytics管理工具或Adobe Admin Console中将不再支持下载权限组信息。 客户应使用adobe.io用户管理API批量获取权限组信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>帐户创建日期 </p> </td> 
   <td colname="col2"> <p>Analytics管理工具或Adobe Admin Console中不再支持帐户创建日期信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>批量电子邮件 </p> </td> 
   <td colname="col2"> <p>Analytics 管理工具或 Adobe Admin Console 中将不再支持批量向用户发送电子邮件。 客户可以从 Adobe Admin Console 中批量导出其用户的电子邮件地址，并使用自己希望的任意电子邮件客户端发送电子邮件。 </p> </td> 
  </tr> 
 </tbody> 
</table>
