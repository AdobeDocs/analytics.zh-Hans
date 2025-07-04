---
description: 了解您在 Analytics 数据中捕获的 ID，并确定要将哪些 ID 用于数据隐私请求。
title: 标签设置最佳实践
feature: Data Governance
role: Admin
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
source-git-commit: 3e87d420591405e57e57e18fda4287d5fbd3bf1b
workflow-type: ht
source-wordcount: '2287'
ht-degree: 100%

---

# 标签设置最佳实践

每次创建新报告包或在现有报告包中启用一个新变量时，都需要对标签设置进行审核。当启用新的解决方案集成时，您可能也需要审核标签设置，因为这些集成将出现要求设置标签的新变量。重新实施您的移动应用程序或网站时，可能会改变现有变量的使用方式，这或许也需要更新标签。

I1、I2、S1 和 S2 标签与 Adobe Experience Platform 中具有相应名称的 DULE 标签具有相同的含义。但是它们的用途截然不同。在 Adobe Analytics 中，这些标签用于帮助识别那些由于隐私服务请求而需要匿名化的字段。在 Adobe Experience Platform 中，它们用于访问控制、同意管理以及用于对有标签的字段强制执行营销限制。Adobe Experience Platform 支持许多 Adobe Analytics 不使用的附加标签。如果您使用 Analytics 数据连接器将 Adobe Analytics 数据导入 Adobe Experience Platform，就应确保在 Adobe Analytics 中应用的任何 I1、I2、S1 和 S2 标签也应用于 Adobe Experience Platform 中被导入的报告包所使用的架构。

## 直接与间接可识别 ID {#direct-vs-indirect}

在您搞清楚要将哪些标签应用于哪些变量/字段之前，首先需要知道您在 Analytics 数据中捕获的 ID，并确定要将哪些 ID 用于数据隐私请求。数据隐私法扩展了可视为 ID 的范围。ID 分为两大类：直接可识别（身份标签：I1）和间接可识别（身份标签：I2）。

* **直接可识别 ID (I1)**：对人员命名或提供他们的直接联系方式。示例包括某人的姓名（甚至是像 John Smith 这种有数百人共用的常见名），他们的任意电子邮件地址或电话号码等等。不含名称的邮寄地址虽然只能识别某个家庭或企业而不能识别该家庭或企业中的具体成员，但它也被视为直接可识别 ID。
* **间接可识别 ID (I2)**：本身不能识别个人的身份，但是可以与其他信息（不管该信息是否由您持有）结合起来，用于识别某人的身份。间接可识别 ID 的示例包括客户会员号，或公司的 CRM 系统为其每个客户使用的唯一 ID。按照数据隐私法规定，Analytics 使用的跟踪 Cookie 中存储的匿名 ID 虽然只能识别设备而不能识别个人，但也被视为间接可识别 ID；在一台共享设备上，这些 Cookie 无法区分该系统的不同用户。例如，虽然 Cookie 不能用于查找包含该 Cookie 的计算机，但如果有人能够访问该计算机并找到该 Cookie，则他们可以将该 Analytics Cookie 数据绑定到该计算机。

IP 地址也被视为间接可识别 ID，因为在任何给定时刻，它只能被分配到一个设备。但是，ISP 可以并且经常会定期更改大部分用户的 IP 地址，因此一个 IP 地址可能会在一段时间内被它们的任何用户使用。还有一种较为常见的情况，某个 ISP 的许多客户或某家企业内位于同一内联网的多名员工共享相同的外部 IP 地址。因此，Adobe 不支持使用 IP 地址作为数据隐私请求的 ID。但是，当我们接受的 ID 用于删除请求时，我们也会清除随该 ID 发生的 IP 地址。您必须确定是否存在其他一些收集的 ID 属于此类别（I1 或 I2），但不适合用作数据隐私请求的标识 ID。

即使贵公司在 Analytics 数据内收集了许多不同的 ID，您也可以选择只使用这些 ID 中的一部分用于数据隐私请求。其原因可能包括：

* 在您自己的系统内，您可以将其中一个 ID（例如，电子邮件地址）映射到其他 ID（例如 CRM ID）。然后，为了保持一致性，您决定在数据隐私处理中只将 CRM ID 用于数据隐私请求。
* 您没有办法来验证某个人实际上就是与该 ID 关联的人员。例如，您很难验证某个 IP 地址只被一个人使用过，而提交请求的正好就是这个人。
* 某些 ID 可能对应多个人员，而您不希望将某个人的相关信息冒险返回给具有同一 ID 的其他人员。例如，即使您可以确认某个人的姓名就是 John Smith，您也可能不希望返回系统中关于所有 John Smith 的所有数据。
* 另一个示例是设备 ID，例如 Analytics Cookie ID。如果 ID 出现在手机应用程序中，您可以确定使用此 ID 的所有交互都应可用于该手机的所有者。但是，如果它出现在共享设备上，例如家用计算机或者图书馆或网吧中的计算机，您可以确定无法区分使用该设备的多名用户，而且将数据返回给其他用户的风险太大，因而不允许使用此类 ID。

## Analytics 支持的 ID 最佳实践 {#best-practices-an}

利用这个表格可以确定在向 Analytics 提交数据隐私请求时，您将使用的 ID 类型。当您清楚了这个信息后，就会比较容易确定应该为变量使用的其他标签了。

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 类型 </th> 
   <th colname="col2" class="entry"> 建议 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=zh-Hans">（旧版）Analytics Cookie</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans"> Identity 服务 Cookie </a> (ECID)，以前称为 Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>这些 Cookie 可识别设备，或更具体地说，可识别某设备用户的浏览器。对于使用常规登录的共享设备，此 ID 可应用于该设备的任何/所有用户。Adobe 创建了一些<a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/">统一的 JavaScript</a>，您可以将它们置于网站中来收集这些 Cookie（如果您希望允许将这些 Cookie 用于数据隐私请求）。 </p> <p>Adobe Analytics Mobile SDK 的用户还拥有 Experience Cloud ID (ECID)。SDK 内有一些 API 调用可读取此 ID，因此您可以增强应用程序来收集此 ID 以用于数据隐私请求。 </p> <p>许多公司考虑将浏览器 Cookie ID 作为共享设备 ID。因此，在与法律团队协商后，这些公司可能会选择不支持将它们用作数据隐私请求的可接受 ID。或者，它们可能会选择在使用这些 ID 时仅返回非常有限的数据量，或者它们可能只接受删除请求。 </p> <p>这些 Cookie 具有无法更改的 ID-DEVICE 标签（以及 I2 和 DEL-DEVICE 标签）。默认的 Adobe Analytics 配置将只返回有关设备的一般性信息，例如设备类型、操作系统、浏览器等等，以及在使用这些 ID 时，对您的网站进行访问的时间/日期。但是，如果您选择支持将这些 ID 用于数据隐私请求，那么按照下面讨论的内容，您可以添加或删除 ACC-ALL 标签，以配置您希望数据隐私访问请求返回的确切字段集。 </p> <p>如果报告包对应于需要登录的移动应用程序，您可以确定设备的 Experience Cloud ID 确实对应于特定用户。在这种情况下，您可能希望使用 ACC-ALL 标签标记更多字段，包括访问过的页面名称、查看过的产品等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义变量中的 ID </p> </td> 
   <td colname="col2"> <p>某些客户将 ID 置于<a href="https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar.html?lang=zh-Hans">自定义流量变量 (prop) 或自定义转化变量 (eVar)</a> 中。最常见的是 CRM ID，其他则包括电子邮件地址、用户登录名、客户会员号或这些值的哈希值。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果您希望将这些 ID 之一用于数据隐私请求，您应当为包含 ID 的字段设置 ID-PERSON 标签。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">（不太常见）如果其中某个自定义变量中的 ID 只识别可能由多人共享的设备，您可以改用 ID-DEVICE 标签。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">这些字段还需要 I1 或 I2 标签，并且应当包含 DEL-PERSON 或 DEL-DEVICE 标签。通常，DEL 标签的 PERSON/DEVICE 选项将与 ID 标签的 PERSON/DEVICE 选项匹配。 </li> 
    </ul> <p> 报告包很少有一个或两个以上自定义变量包含要用于识别数据隐私请求“数据主体”的 ID。您可能具有多个分配了 I1 或 I2 标签的变量，但是通常其中只有一个或两个变量还具有 ID-PERSON 或 ID-DEVICE 标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义访客 ID </p> </td> 
   <td colname="col2"> <p>即使它未受到广泛使用，Analytics 依然支持可提供自定义访客 ID 的实施，此实施如果存在，即可用于替代旧版 Analytics 跟踪 Cookie。此字段具有 I2、ID-PERSON 和 DEL-PERSON 标签。 </p> <p>许多实施从 CRM ID 派生此 ID，因此它仅在某人登录其网站时存在。这允许同一自定义访客 ID 在多个设备间使用。它存在一个技术缺陷，即用户登录之前发生的跟踪无法绑定到他们登录之后收集的跟踪。相反，如果您仅仅是使用自定义访客 ID 来识别设备，则应分别将 ID-PERSON 和 DEL-PERSON 标签更改为 ID-DEVICE 和 DEL-DEVICE。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设置删除标签的最佳实践 {#best-practices-delete}

>[!NOTE]
>
>Prop 始终不区分大小写。eVar 在默认情况下不区分大小写，但可通过 Adobe 客户关怀团队将其配置为区分大小写。如果您拥有一个区分大小写且包含 ID 的 eVar，您应负责在提交数据隐私请求时使用正确的大小写，以便请求中使用的大小写与包含这些 ID 的点击中使用的大小写相匹配。

删除标签 DEL-DEVICE 和 DEL-PERSON 应当谨慎使用。当应用到的变量不包含数据隐私请求中使用的 ID 时，历史 Analytics 报告中的计数（量度）几乎总要发生更改。

* 我们建议将其中一个标签应用于标记为 I1、I2 或 S1 的任何变量。它们无法应用于未标记为 I1、I2 或 S1 的任何变量。
* DEL- 标签将导致这些变量[匿名化](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels)（ID 将被前缀为“Data Privacy-”的随机字符串替换）。在由请求中使用的 ID 所识别的所有点击量当中，将使用相同的匿名值替代原始值的所有实例。如果此字段中的原始值为这些 ID 之一，则报告量度将不会发生更改。
* 通常，如果字段具有标签 ID-DEVICE，则您还应当分配标签 DEL-DEVICE。
* 同样，如果字段具有标签 ID-PERSON，则您还应当分配标签 DEL-PERSON。
* 如果字段没有 ID- 标签，但是包含需要匿名化的识别信息，那么需要根据您的实施来选择适用的标签（DEVICE 或 PERSON）。如果您只将 Cookie ID 用于数据隐私请求，则您应当使用 DEL-DEVICE。
* 如果您在具有 ID-PERSON 标签的其他字段中使用自定义 ID，并且只希望在出现该 ID 的行中清除它，则使用 DEL-PERSON。
* 请注意，如果在任意未被用作请求 ID（包括扩展的 ID）的变量上指定 DEL-DEVICE 或 DEL-PERSON 标签，那么该变量的唯一值将只在出现特定（或扩展）ID 的点击量上进行匿名化。即使其他点击量包含相同的值，该值也并不会在其他位置发生更新。这会导致计数（量度）发生更改。

  例如，如果您在 eVar7 中有三个包含值“foo”的点击量，但其中只有一个点击量还在其他变量中包含了与删除请求匹配的 ID，那么这一个点击量当中的“foo”值将被修改为一个类似“Data Privacy-123456789”这样的值，而在其他两个点击量中，该值将保持不变。现在，展示 eVar7 唯一值数量的报告会比此前多显示一个唯一值。在显示 eVar 探顶值的报告中，只有两个实例（而不是以前的 3 个）包含值“foo”，与此同时，还会有一个实例显示新值。

## 设置访问标签的最佳实践 {#best-practices-access}

通常大量字段将具有 ACC 标签，不过也有很少字段将具有任何其他标签。哪个访问标签适用将取决于您用于隐私数据请求的 ID。

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 如果您使用... </th> 
   <th colname="col2" class="entry"> ...使用这些建议 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>仅设备 ID </p> </td> 
   <td colname="col2"> <p>如果您仅使用 Cookie ID 或那些具有 ID-DEVICE 标签的 ID，则应当只使用 ACC-ALL 标签。 </p> <p>对于每个访问请求，您将获得一对文件：其中一个文件包含与每个匹配点击量对应的一行以及所有指定的 ACC-ALL 字段，另一个摘要文件则包含该数据的摘要。 </p> </td> 
  </tr> 
 </tbody> 
</table>
