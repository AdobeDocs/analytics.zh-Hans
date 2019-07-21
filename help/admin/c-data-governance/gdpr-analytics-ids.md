---
description: 'null'
seo-description: 'null'
seo-title: 标记最佳实践
title: 标记最佳实践
uuid: d1e9bfff-9b04-4e3e-9b4e-a6 e527 b1 b2 e3
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 标记最佳实践

>[!NOTE]
>
>请记住，每次创建新报表包或在现有报表包中启用新变量时，都需要审核标记。当启用新的解决方案集成时，您可能也需要审核标签设置，因为这些集成将出现要求设置标签的新变量。重新实施您的移动应用程序或网站时，可能会改变现有变量的使用方式，这或许也需要更新标签。

## 直接与间接可识别 ID {#section_030799AA1397433FBA61A2BC60A7A750}

在您搞清楚要将哪些标签应用于哪些变量/字段之前，首先需要对您在 Analytics 数据中捕获的 ID 有所了解，并确定要将哪些 ID 用于 GDPR 请求。GDPR 扩展了可视为 ID 的范围。ID 分为两大类：直接可识别（身份标签：I1）和间接可识别（身份标签：I2）。

* **直接可识别 ID (I1)**：对人员命名或提供他们的直接联系方式。示例包括某人的姓名（甚至是像 John Smith 这种有数百人共用的常见名），他们的任意电子邮件地址或电话号码等等。不含名称的邮寄地址虽然只能识别某个家庭或企业而不能识别该家庭或企业中的具体成员，但它也被视为直接可识别 ID。
* **间接可识别 ID (I2)**：本身不能识别个人的身份，但是可以与其他信息（不管该信息是否由您持有）结合起来，用于识别某人的身份。示例包括客户会员号，或公司的 CRM 系统为其每个客户使用的唯一 ID。按照 GDPR 规定，Analytics 使用的跟踪 Cookie 中存储的匿名 ID 虽然只能识别设备而不能识别个人，但也被视为间接可识别 ID；在一台共享设备上，这些 Cookie 无法区分该系统的不同用户。例如，虽然 Cookie 不能用于查找包含该 Cookie 的计算机，但如果有人能够访问该计算机并找到该 Cookie，则他们可以将该 Analytics Cookie 数据绑定到该计算机。

   IP 地址也被视为间接可识别 ID，因为在任何给定的时间，它只能被分配到一个设备。但是，ISP 可以并且经常会定期更改大部分用户的 IP 地址，因此一个 IP 地址可能会在一段时间内被它们的任何用户使用。还有一种较为常见的情况，某个 ISP 的许多客户或某家企业内位于同一内联网的多名员工共享相同的外部 IP 地址。因此，Adobe 将不支持使用 IP 地址作为 [GDPR 请求](../../admin/c-data-governance/gdpr-submit-access-delete.md#concept_0941C076F76641FF8BF865C7C1CB916B)的 ID。但是，当我们接受的 ID 用于删除请求时，我们也会清除随该 ID 发生的 IP 地址。您必须确定您收集的 ID 中是否存在其他一些 ID 属于此类别（I1 或 I2），但不适合用作 GDPR 请求的标识 ID。

即使贵公司在 Analytics 数据内收集了许多不同的 ID，您也可以选择只使用这些 ID 中的一部分用于 GDPR 请求。其原因可能包括：

* 在您自己的系统内，您可以将其中一个 ID（例如，电子邮件地址）映射到其他 ID（例如 CRM ID）。然后，为了保持一致性，您决定在 GDPR 处理中只将 CRM ID 用于 GDPR 请求。
* 您没有办法来验证某个人实际上就是与该 ID 关联的人员。例如，您很难验证某个 IP 地址只被一个人使用过，而提交请求的正好就是这个人。
* 某些 ID 可能对应多个人员，而您不希望将某个人的相关信息冒险返回给具有同一 ID 的其他人员。例如，即使您可以确认某个人的姓名就是 John Smith，您也可能不希望返回系统中关于所有 John Smith 的所有数据。
* 另一个示例是设备 ID，例如 Analytics Cookie ID。如果 ID 出现在手机应用程序中，您可以确定使用此 ID 的所有交互都应可用于该手机的所有者。但是，如果它出现在共享设备上，例如家用计算机或者图书馆或网吧中的计算机，您可以确定无法区分使用该设备的多名用户，而且将数据返回给其他用户的风险太大，因而不允许使用此类 ID。

## Analytics 支持的 ID 最佳实践 {#section_B6481505FF1949498D4B4B35B780D050}

利用这个表格可以确定在向 Analytics 提交 GDPR 请求时，您将使用的 ID 类型。当您清楚了这个信息后，就会比较容易确定应该为变量使用的其他标签了。

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
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external">（旧版）Analytics Cookie</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service cookie </a> (ECID)，以前称为Marketing Cloud ID(MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>这些 Cookie 可识别设备，或更具体地说，可识别某设备用户的浏览器。对于使用常规登录的共享设备，此 ID 可应用于该设备的任何/所有用户。Adobe 创建了一些<a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external">统一的 JavaScript</a>，您可以将它们置于网站中来收集这些 Cookie（如果您希望允许将这些 Cookie 用于 GDPR 请求）。 </p> <p>Adobe Analytics Mobile SDK 的用户还拥有 Experience Cloud ID (ECID)。SDK 内有一些 API 调用可读取此 ID，因此您可以增强应用程序来收集此 ID 以用于 GDPR 请求。 </p> <p>许多公司考虑将浏览器 Cookie ID 作为共享设备 ID。因此，在与公司的法律团队商讨之后，这些公司可能选择不支持使用这些 ID 作为 GDPR 请求的可接受 ID，或者他们可能选择在使用这些 ID 时只返回非常有限的数据量或是仅接受这些 ID 用于删除请求。 </p> <p>这些 Cookie 具有无法更改的 ID-DEVICE 标签（以及 I2 和 DEL-DEVICE 标签）。默认的 Adobe Analytics 配置将只返回有关设备的一般性信息，例如设备类型、操作系统、浏览器等等，以及在使用这些 ID 时，对您的网站进行访问的时间/日期。但是，如果您选择支持将这些 ID 用于 GDPR 请求，那么按照下面讨论的内容，您可以添加或删除 ACC-ALL 标签，以配置您希望 GDPR 访问请求返回的确切字段集。 </p> <p>特别是在报表包对应移动设备应用程序，而您的移动设备应用程序又要求登录的情况下，您可以决定将该设备的 Experience Cloud ID 对应于特定的用户，这样一来，您可能希望使用 ACC-ALL 标签来标记更多的字段，其中包括已访问页面的名称、查看的产品等等。 </p> <p>注意：如果您在 GDPR 请求中指定了“expandIds”选项，那么除了您指定的任何其他 ID 之外，您的请求还将始终包含 Cookie ID。更多详细信息，请参阅 <a href="../../admin/c-data-governance/gdpr-analytics-ids.md#section_D55C0722BC834118BE6F958C30AD5913" format="dita" scope="local">ID 扩展</a>。在这些情况下，对于只具有 Cookie ID 而没有其他 ID 的命中项，则仅为访问请求返回具有 ACC-ALL 标记的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义变量中的 ID </p> </td> 
   <td colname="col2"> <p>某些客户将 ID 置于<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">自定义流量变量 (prop) 或自定义转化变量 (eVar)</a> 中。最常见的是 CRM ID，其他则包括电子邮件地址、用户登录名、客户会员号或这些值的哈希值。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果您希望将这些 ID 之一用于 GDPR 请求，您应当为包含 ID 的字段设置 ID-PERSON 标签。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">（不太常见）如果其中某个自定义变量中的 ID 只识别可能由多人共享的设备，您可以改用 ID-DEVICE 标签。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">这些字段还需要 I1 或 I2 标签，并且应当包含 DEL-PERSON 或 DEL-DEVICE 标签。通常，DEL 标签的 PERSON/DEVICE 选项将与 ID 标签的 PERSON/DEVICE 选项匹配。 </li> 
    </ul> <p> 报表包很少有一个或两个以上自定义变量包含要用于识别 GDPR 请求数据主体的 ID。您可能具有多个分配了 I1 或 I2 标签的变量，但是通常其中只有一个或两个变量还具有 ID-PERSON 或 ID-DEVICE 标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义访客 ID </p> </td> 
   <td colname="col2"> <p>即使它未受到广泛使用，Analytics 依然支持可提供自定义访客 ID 的实施，此实施如果存在，即可用于替代旧版 Analytics 跟踪 Cookie。此字段具有 I2、ID-PERSON 和 DEL-PERSON 标签。 </p> <p>许多实施从 CRM ID 派生此 ID，因此它仅在某人登录其网站时存在。这允许同一自定义访客 ID 在多个设备间使用。它存在一个技术缺陷，即用户登录之前发生的跟踪无法绑定到他们登录之后收集的跟踪。相反，如果您仅仅是使用自定义访客 ID 来识别设备，则应分别将 ID-PERSON 和 DEL-PERSON 标签更改为 ID-DEVICE 和 DEL-DEVICE。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设置删除标签的最佳实践 {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE]
>
>Prop始终区分大小写。eVar 在默认情况下不区分大小写，但可通过 Adobe 客户关怀团队将其配置为区分大小写。如果您拥有一个区分大小写且包含 ID 的 eVar，您应负责在提交 GDPR 请求时使用正确的大小写，以便请求中使用的大小写与包含这些 ID 的命中项使用的大小写相匹配。

删除标签 DEL-DEVICE 和 DEL-PERSON 应当谨慎使用。当应用到的变量不包含 GDPR 请求中使用的 ID 时，历史 Analytics 报表中的计数（量度）几乎总要发生更改。

* 我们建议将其中一个标签应用于标记为 I1、I2 或 S1 的任何变量。它们无法应用于未标记为 I1、I2 或 S1 的任何变量。
* DEL- 标签将导致这些变量[匿名化](../../admin/c-data-governance/gdpr-labels.md#section_F3DEE591671A4B16A8E043F91C137ECB)（ID 将被前缀为“GDPR-”的随机字符串替换）。在由请求中使用的 ID 所识别的所有命中项当中，将使用相同的匿名值替代原始值的所有实例。如果此字段中的原始值为这些 ID 之一，则报表量度将不会发生更改。
* 通常，如果字段具有标签 ID-DEVICE，则您还应当分配标签 DEL-DEVICE。
* 同样，如果字段具有标签 ID-PERSON，则您还应当分配标签 DEL-PERSON。
* 如果字段没有 ID- 标签，但是包含需要匿名化的识别信息，那么需要根据您的实施来选择适用的标签（DEVICE 或 PERSON）。如果您只将 Cookie ID 用于 GDPR 请求，则您应当使用 DEL-DEVICE。
* 如果您在具有 ID-PERSON 标签的其他字段中使用自定义 ID，并且只希望在出现该 ID 的行中清除它，则使用 DEL-PERSON。
* 如果您使用 ID 扩展，并且希望为所有已识别设备上的所有命中项清除所有值，则使用 DEL-DEVICE。如果您愿意，可以在这种情况下应用 DEL-DEVICE 和 DEL-PERSON 标签，但 DEL-PERSON 标签并不是必需的，因为 ID 扩展意味着与人员 ID 匹配的所有行也将匹配设备 ID。
* 如果您没有指定要使用 ID 扩展，但是要为不同的请求使用设备和个人混合 ID，那么您在使用其中的任何一类 ID 时，可能希望为应当删除的变量同时指定 DEL-DEVICE 和 DEL-PERSON 标签。
* 请注意，如果在任意未被用作请求 ID（包括扩展的 ID）的变量上指定 DEL-DEVICE 或 DEL-PERSON 标签，那么该变量的唯一值将只在出现特定（或扩展）ID 的命中项上进行匿名化。即使其他命中项包含相同的值，该值也并不会在其他位置发生更新。这会导致计数（量度）发生更改。

   例如，如果您在 eVar7 中有三个包含值“foo”的命中项，但其中只有一个命中项还在其他变量中包含了与删除请求匹配的 ID，那么这一个命中项当中的“foo”值将被修改为一个类似“GDPR-123456789”这样的值，而在其他两个命中项中，该值将保持不变。现在，展示 eVar7 唯一值数量的报表会比此前多显示一个唯一值。在显示 eVar 探顶值的报表中，只有两个实例（而不是以前的 3 个）包含值“foo”，与此同时，还会有一个实例显示新值。

## 设置访问标签的最佳实践 {#section_AC7E216F81C141FCA6A62F8836E06EE7}

通常大量字段将具有 ACC 标签，不过也有很少字段将具有任何其他标签。哪个访问标签适用将取决于您用于 GDPR 请求的 ID。

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
   <td colname="col2"> <p>如果您仅使用 Cookie ID 或那些具有 ID-DEVICE 标签的 ID，则应当只使用 ACC-ALL 标签。 </p> <p>对于每个访问请求，您将获得一对文件，其中一个文件包含与每个匹配命中项对应的行，行中提供了所有指定的 ACC-ALL 字段，另一个文件则包含该数据的摘要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>无 ID 扩展的人员 ID </p> </td> 
   <td colname="col2"> <p>如果您仅使用具有 ID-PERSON 标签的自定义 ID 而不进行 ID 扩展，则应当使用 ACC-PERSON 标签。但是，您不需要更改默认的 ACC-ALL 标签；这些字段将自动包含在访问请求中。 </p> <p>对于每个访问请求，您将获得一对文件，其中一个文件包含与每个匹配命中项对应的行，行中提供了所有指定的 ACC-DEVICE 和 ACC-PERSON 字段，另一个文件则包含该数据的摘要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>混合 ID 和/或 ID 扩展 </p> </td> 
   <td colname="col2"> <p>如果您在 GDPR 请求中同时包含设备和人员 ID，或者如果您使用自定义 ID（自定义访客 ID 或者 prop 或 eVar 中的 ID），则您需要注意所使用的 ACC 标签。每个访问请求将返回两对数据文件，一对包含匹配人员 ID 的命中数据，另一对则包含不匹配人员 ID 但匹配设备 ID 的命中数据。 </p> <p>“人员 ID”文件包含与人员 ID 匹配的所有命中的数据，其中所有字段都具有 ACC-PERSON 或 ACC-ALL 标签（一个文件包含所有匹配的命中，另一个文件作为摘要）。 </p> <p>“设备 ID”文件对只包含具有 ACC-ALL 标签的字段，并且只包含没有任何匹配人员 ID 的命中。这些文件可能包含由共享设备的其他用户生成的数据，因此您需要仔细考虑包含 ACC-ALL 标签的字段集。Analytics 内的默认标签功能只将此标签应用于有关设备的一般性信息字段（设备类型、操作系统、浏览器等等），以及每个命中的日期/时间。 </p> <p>您可以选择从 Adobe 同时接收设备和人员文件组，然后只共享人员文件，以免共享可能由共享设备的其他用户生成的数据。或者，您可能希望将来自一种或两种文件组的数据与您了解的其他数据主体相关信息合并到一起，并以您自己的格式返回这些信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

