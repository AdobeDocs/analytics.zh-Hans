---
description: 针对虚拟报表包新用户的提示和最佳实践。
keywords: 虚拟报表包
seo-description: 针对虚拟报表包新用户的提示和最佳实践。
seo-title: VRS常见问题解答
solution: Analytics
title: VRS常见问题解答
topic: Reports & Analytics
uuid: 91225743-765a-4145-9ce5-4268e80ea7e8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# VRS常见问题解答

针对虚拟报表包新用户的提示和最佳实践。

<table id="table_4D9DE70984674B65AD7D40E3D1479CD2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>我是否应该在实施中将多个报表包整合成一个“全局”报表包，然后使用虚拟报表包向我的用户展示不同的数据区段？</b> </td> 
   <td colname="col2"> <p>也许应该这样做。以下是您应该<b>考虑继续使用单个报表包</b>的一些情况： </p> 
    <ul id="ul_493454A655DE48E0AF94130014203268"> 
     <li id="li_B37C2651D2804FD1B965286C85A765D5">如果您的变量/维度中有大量唯一值，那么整合成一个报表包可能会导致这个全局报表包超出每月唯一值限制，从而发生截断（报表中的行项目显示“低流量”）。 </li> 
     <li id="li_87ABC62EC73D4355A9F768AD1949D3C6">如果您需要针对数据的单个区段（例如，品牌、业务单位等）获取实时或“当前数据”报表。 </li> 
     <li id="li_7252787B2D4C4756836DAEA0EEC0BF8B">如果您的各种报表包均有各自独特的跟踪要求（也就是说，它们使用 Adobe Analytics 变量和事件的方式大不相同），那么请注意，整合成全局报表包后将无法授权其他变量或事件进行跟踪。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>虚拟报表包会从父报表包那里继承哪些设置？</b> </td> 
   <td colname="col2"> <p>虚拟报表包 (VRS) 会继承父报表包的大部分服务级别，如 eVar 设置、处理规则和分类等。 </p> <p>以下设置<b>不会</b>被继承： </p> 
    <ul id="ul_43B0637F095C480B82126C96BFF627FA"> 
     <li id="li_F3DF9D6B0B1A4A46B9D8B1CF2DA09BE3">报表包 ID </li> 
     <li id="li_A735D7BA4DA14DCB8F40D7898A324F1F">报表包名称 </li> 
     <li id="li_BF66DD426EE7464CBF7F2EB56B0C3075">权限群组（可将虚拟报表包分配给其自身的权限群组） </li> 
    </ul> <p>注意：这不包括用户创建的大部分实体，如书签、功能板、计划报表等；VRS 不会从父报表包继承这些项目，可专门针对 VRS 创建并使用这些项目（在下一个问题中会详细说明）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>在 Analytics 用户界面中使用虚拟报表包与使用基础报表包有何不同？</b> </td> 
   <td colname="col2"> <p>创建虚拟报表包后，在整个用户界面中都会像对待基础报表包一样对待虚拟报表包，并且大部分扩展功能通常也支持虚拟报表包。例如： </p> 
    <ul id="ul_D20435FD9B3546DFB611FD09035BACBB"> 
     <li id="li_4A331EB50B7F43E697F67B4A657B4450">报表包选择器中会显示虚拟报表包，可以像选择任何其他基础报表包一样逐个选择虚拟报表包。 </li> 
     <li id="li_6E8C1E45C68943A1BA7C260FA62C40E0">可以针对虚拟报表包创建 DL 报表、书签、功能板、目标、警报、区段和计算量度等，并且这些项目的行为不依赖于父报表包。 </li> 
     <li id="li_5701D7F60BF8452CBEC8DFA2072CE8C2">与任何其他报表包一样，可以将虚拟报表包逐个添加至权限群组。 </li> 
     <li id="li_764475FD352C434D92E876E30699F280">在 VRS 上下文中运行报表时，仍然可以应用区段；在检索报表数据时，会自动将应用的区段与虚拟报表包的区段堆叠在一起。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>在管理控制台和管理 API 中如何对待虚拟报表包？对于虚拟报表包，可以像基础报表包一样保存各项功能吗？</b> </td> 
   <td colname="col2"> <p>不可以，<b>大部分“管理员”功能不支持</b>虚拟报表包。正如上文所述，VRS 会从父报表包继承大部分服务级别和功能（例如，eVar 设置、处理规则和分类等），因此要更改 VRS 中的这些继承设置，您必须更改父报表包。 </p> <p>因此，虚拟报表包仅在用户界面中的<b>以下位置</b>显示： </p> 
    <ul id="ul_64CF126ACF39453A95BD9FC9D2CFA59B"> 
     <li id="li_08EBF87ADF13400C9DD3FFC2695F5CF9">虚拟报表包管理器，在这里您可以创建和编辑 VRS。 <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol">组件</span> &gt; <span class="uicontrol">虚拟报表包 </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> “用户管理”界面，在这里您可以编辑自定义权限群组。这允许将 VRS 帐户添加到权限群组，并使用 VRS 帐户创建仅有权访问虚拟报表包的群组（如果管理员希望拒绝访问父报表包，并仅允许用户访问特定区段）。 <p>（<span class="ignoretag"><span class="uicontrol">管理员</span> &gt; <span class="uicontrol">用户管理</span></span>） </p> </li> 
    </ul> <p>注意：当您使用 Web 服务 API 并尝试为 VRS 保存功能设置时，将会显示异常。您只能为基础报表包设置功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>在 SiteCatalyst 14 用户界面中是否支持虚拟报表包？</b> </td> 
   <td colname="col2"> <p>不支持，我们在 SiteCatalyst 14 中不显示虚拟报表包。报表包选择器中不会显示虚拟报表包以供选择，因而无法选择这类报表包。但是，在 SiteCatalyst 14 管理控制台用户界面中编辑群组时，确实会显示虚拟报表包。在这种特殊情况下，需要显示虚拟报表包，这样便不会从已经对一个/多个虚拟报表包拥有访问权限的已有群组中意外删除虚拟报表包。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>我选中了“在每次应用程序启动后即开始一个新访问”。为何我仍会看到访问次数远大于启动次数？</b> </td> 
   <td colname="col2"> <p> 选中<span class="uicontrol">在每次应用程序启动后即开始一个新访问</span>选项后，超时仍适用。因此，如果用户使用一个应用程序 10 分钟，并且各个操作之间有一分钟的间隔，则会在应用程序启动后开始一次新访问，然后在访问超时时创建其他 9 次访问。选中</span>在每次应用程序启动后即开始一个新访问<span class="uicontrol">选项后，要使启动次数与访问次数尽可能接近，使用的超时时间应大于 SDK 中设置的会话超时时间。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>我设置了“在每次应用程序启动后即开始一个新访问”，且设置的超时时间大于 SDK 中的值。为何我的启动次数仍远小于访问次数？</b> </td> 
   <td colname="col2"> <p> 如果您设置的超时时间大于 SDK 中设置的值，原因很可能是您的应用程序在后台发送了点击，并且这些点击被计为新的访问。可通过使用父报表包中的点击类型维度来查看是否存在任何后台点击。 </p> <p> <p>注意：只有在 SDK 4.13.6 及更高版本中才会区分后台点击和前台点击。如果您使用的是较低版本，则所有点击都会显示为前台点击。如果您使用的是正确的 SDK 版本，则应当已启用<span class="uicontrol">避免将后台点击计算为一次新的访问</span>设置。 </p> </p> <p> <p>注意：如果您在管理控制台中禁用了后台点击旧版处理功能，则这些点击将不会显示在父报表包中，但会显示在虚拟报表包中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>我需要使用哪个 SDK 版本来跟踪后台点击？</b> </td> 
   <td colname="col2"> <p> 您必须使用 SDK 4.13.6 或更高版本。 </p> </td> 
  </tr> 
 </tbody> 
</table>

