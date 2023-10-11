---
description: 实施 Audience Analytics 时可能遇到的问题的解答。
solution: Experience Cloud
title: Audience Analytics 常见问题解答。
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 75%

---

# 常见问题解答

实施 Audience Analytics 时可能遇到的问题的解答。

## 法律方面的常见问题解答 {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>问：如何知道我的 Analytics 数据中是否包含个人可识别信息 (PII)？如果包含，我该怎么做？</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">如果 prop 或 eVar 中包含电子邮件、地址等信息，则应考虑在数据收集期间对数据执行哈希处理。 </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">如果您所在的国家/地区将 IP 地址视为 PII，则应<a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html?lang=zh-Hans"  >开启 IP 模糊处理</a>。 </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">咨询您的 Analytics 管理员，以了解您所收集的信息。 </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">咨询您的法务部门，以了解他们将什么信息视为 PII。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>问：如何知道我的报表包是否进行了现场个性化，或非现场/现场定位？</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">这些操作不适用于将 Adobe Analytics 数据发送至 Adobe Audience Manager。 </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">请思考：您是否要将 Analytics 共享的区段和 MCA 维度共享回 Experience Cloud？ </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">您是否要导出（例如，通过数据馈送）至商业智能 (BI) 系统，以用于上述目的？ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Audience Manager特定的常见问题解答 {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>问：我如何在 Audience Manager 中创建 Analytics 目标？</b> </p> </td> 
   <td colname="col2"> 请参阅 <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=zh-Hans"  > 在Adobe Audience Manager中配置Analytics目标 </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：在创建并保存了 Analytics 目标之后，需要多久才会在我选择的报表包中显示数据？</b> </p> </td> 
   <td colname="col2"> <p>可能需要几个小时的时间才能在您的报表包中填充新数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>问：我已创建了新的 Analytics 目标，但在可用区段的“目标映射”部分中看不到它。<b>那个区段去哪了，或者我该如何找到它？</b> </p> </td> 
   <td colname="col2"> <p>当您在<span class="uicontrol">区段映射</span>中选择<span class="uicontrol">自动映射所有当前和未来区段</span>选项时，Analytics 目标就会从区段的“目标映射”部分中消失。 </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>要防止出现这种情况，请选择<span class="uicontrol">手动映射区段</span>，而不要选择自动选项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>问：Analytics是否会为我提供Adobe Audience Manager中的所有信息？</b> </p> </td> 
   <td colname="col2"> <p>不会，仅提供 Audience Manager 受众启用期间或之后，以及区段鉴定期间或之后访问您站点的用户相关数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>问：这是否会向我提供按区段划分的可寻址受众总数？</b> </p> </td> 
   <td colname="col2"> <p>事实上不会。它会向您提供该区段中，在区段鉴定期间或之后访问您站点的访客数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>问：这与指向 Analytics 的旧 Cookie 目标有何区别？</b> </p> </td> 
   <td colname="col2"> <p>区段是基于同一次点击进行实时鉴定并返回。 </p> <p>将会自动显示易记名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：如果我的某些报表包中包含个人数据，而有些不包含，我该怎么做？</b> </p> </td> 
   <td colname="col2"> <p>提示：创建两个维度 — 将个人数据报表包添加到其中一个维度，并将非个人数据报表包添加到另一个维度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Analytics 特定的常见问题解答 {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>问：这一集成将会在 Analytics 中显现为维度还是区段？</b> </p> </td> 
   <td colname="col2"> <p>显示为维度：受众 ID 和受众名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：我可以在 Analytics 中的哪些地方使用这些维度？</b> </p> </td> 
   <td colname="col2"> <p>几乎任何地方都可以使用；对它们的处理方式与 Analytics 中收集到的任何其他维度类似。有一个例外：这些维度当前在 Data Workbench 中不可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：为何我无法看到在 Analytics 中传入的数据？</b> </p> </td> 
   <td colname="col2"> <p>数据源与目标之间的Adobe Audience Manager隐私控件可能存在冲突。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：为何我的某些区段在 Analytics 中丢失，即使我选择发送所有区段也是如此？</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">目标数据源和区段数据源中的Adobe Audience Manager数据导出控件可能存在冲突，这会阻止发送某些区段。 </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">如果您在区段中使用第三方数据特征，这些区段无法共享到包含个人数据的目标（一组报表包）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：为什么我在 Analytics 报表中看到“已达到受众限制”？（注意：这在 Data Warehouse 中还将表示为 Audience ID = -1 和 "::max_audiences_exceeded::"）</b> </p> </td> 
   <td colname="col2"> <p>默认情况下，Adobe Audience Manager的Audience Analytics集成会按每次点击将所有访客符合条件的区段发送到Analytics。 如果某位访客在一次点击中属于超过150个Adobe Audience Manager区段，则 <b>150个最近符合条件的区段</b> 发送到Analytics，而其余列表会被截断。 </p> <p>此外，还会向 Analytics 发送一个标记，指示区段列表被截断，该标记在“受众名称”维度中显示为“已达到受众限制”，在“受众 ID”维度中显示为“-1”。 </p> <p>虽然访客不太可能在一次点击中有资格使用 150 个以上的区段，但这种情况依然有极小的概率发生。如果您在报表中遇到“已达到受众限制”，可选择以下两个选项： </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>选项 1</b>：继续让集成保持现有工作状态，这会为特定访客发送最近获得授权的 150 个区段。 </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>选项2</b>：在Adobe Audience Manager中，选择对您的业务最重要的150个区段进行集成。 然后，Adobe Audience Manager仅根据这150个区段检查访客。 此方法的缺点在于您只能收到所有访客间的这 150 个区段。而在另一方面，选项 1 方法因为集成的每次点击特性可提供无限的区段。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：对于该集成，额外的服务器调用会记入 Analytics 吗？</b> </p> </td> 
   <td colname="col2"> <p>不会。Adobe Audience Manager受众已纳入Analytics点击服务器端。 这不会对 Analytics 引发额外的服务器调用（主要或次要）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 服务器端转发 (SSF) 常见问题解答 {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>问：如果我实施了旧版 SSF，我还需要转至 Analytics 管理员，开启报表包 SSF 吗？</b> </p> </td> 
   <td colname="col2"> <p>是的。在Adobe Audience Manager目标设置中，您将只看到启用了SSF的报表包。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：为何我无法在 Analytics 管理员中为某些报表包开启 SSF？</b> </p> </td> 
   <td colname="col2"> <p>只能启用映射到您的 Experience Cloud 组织的报表包。 </p> </td> 
  </tr> 
 </tbody> 
</table>

有关此主题的更多常见问题解答，请参阅[服务器端转发常见问题解答](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)。

## 一般常见问题解答 {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>问：为何 Audience Manager 与 Analytics 提供的区段访客计数存在差异？</b> </p> </td> 
   <td colname="col2"> <p>请参阅<a href="/help/integrate/c-audience-analytics/visitor-count-reconciliation.md"  >访客计数差异 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：Adobe Audience Manager中的“受众”与Analytics中的“区段”有何区别？</b> </p> </td> 
   <td colname="col2"> <p>请参阅 <a href="/help/integrate/c-audience-analytics/aam-analytics-segments.md"  > 了解Analytics和Audience Manager中的区段 </a>. </p> <p>Adobe Audience Manager受众作为要在Analytics中使用的“维度”组件进行发送和共享。 它们不会在区段生成器之类的地方显示为区段，但是会作为您可用来构建区段的维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：从Adobe Audience Manager集成的客户属性和客户数据之间有何区别？</b> </p> </td> 
   <td colname="col2"> <p>客户属性不是基于时间的；它们可追溯应用，并可向前应用。 Adobe Audience Manager集成数据是基于时间的，并且仅用于前进。 此外，客户属性是Experience Cloud访客ID的查找表，而Adobe Audience Manager集成是将数据拼合到访客的每次点击中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>问：针对该问题的旧方法效果如何，比如，旧的测试版或咨询插件 Cookie 目标？</b> </p> </td> 
   <td colname="col2"> <p>我们建议您实施新的集成并删除旧目标。 </p> </td> 
  </tr> 
 </tbody> 
</table>
