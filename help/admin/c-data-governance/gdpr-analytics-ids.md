---
description: 'null'
seo-description: 'null'
seo-title: 标签设置最佳实践
title: 标签设置最佳实践
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: 2e78524a1ec88ace687ef293332bbee532388c7a

---


# 标签设置最佳实践

>[!NOTE]
>
>请记住，每次创建新报表包或在现有报表包中启用新变量时，都需要查看标签。 当启用新的解决方案集成时，您可能也需要审核标签设置，因为这些集成将出现要求设置标签的新变量。重新实施您的移动应用程序或网站时，可能会改变现有变量的使用方式，这或许也需要更新标签。

## 直接与间接可识别 ID {#section_030799AA1397433FBA61A2BC60A7A750}

在确定应将哪些标签应用于哪些变量／字段之前，首先必须了解您在Analytics数据中捕获的ID，并决定将哪些用于数据隐私请求。 数据隐私扩展了可视为ID的范围。 ID 分为两大类：直接可识别（身份标签：I1）和间接可识别（身份标签：I2）。

* **直接可识别 ID (I1)**：对人员命名或提供他们的直接联系方式。示例包括某人的姓名（甚至是像 John Smith 这种有数百人共用的常见名），他们的任意电子邮件地址或电话号码等等。不含名称的邮寄地址虽然只能识别某个家庭或企业而不能识别该家庭或企业中的具体成员，但它也被视为直接可识别 ID。
* **间接可识别 ID (I2)**：本身不能识别个人的身份，但是可以与其他信息（不管该信息是否由您持有）结合起来，用于识别某人的身份。示例包括客户会员号，或公司的 CRM 系统为其每个客户使用的唯一 ID。根据数据隐私，Analytics使用的跟踪Cookie中存储的匿名ID可能被视为间接识别，即使它们只能识别设备而不能识别个人；在共享设备上，这些Cookie无法区分系统的不同用户。 例如，虽然 Cookie 不能用于查找包含该 Cookie 的计算机，但如果有人能够访问该计算机并找到该 Cookie，则他们可以将该 Analytics Cookie 数据绑定到该计算机。

   IP 地址也被视为间接可识别 ID，因为在任何给定的时间，它只能被分配到一个设备。但是，ISP 可以并且经常会定期更改大部分用户的 IP 地址，因此一个 IP 地址可能会在一段时间内被它们的任何用户使用。还有一种较为常见的情况，某个 ISP 的许多客户或某家企业内位于同一内联网的多名员工共享相同的外部 IP 地址。Because of this, Adobe will not support using an IP address as the ID for a [Data Privacy request.](../../admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests)但是，当我们接受的 ID 用于删除请求时，我们也会清除随该 ID 发生的 IP 地址。您必须确定您收集的其他ID是否属于I1或I2的此类别，但不适合用作数据隐私请求的区别ID。

即使您的公司在您的Analytics数据中收集了许多不同的ID，您也可以选择仅将这些ID的子集用于数据隐私请求。 其原因可能包括：

* 在您自己的系统内，您可以将其中一个 ID（例如，电子邮件地址）映射到其他 ID（例如 CRM ID）。然后，为保持一致性，您决定在数据隐私处理中仅使用数据隐私请求的CRM ID。
* 您没有办法来验证某个人实际上就是与该 ID 关联的人员。例如，您很难验证某个 IP 地址只被一个人使用过，而提交请求的正好就是这个人。
* 某些 ID 可能对应多个人员，而您不希望将某个人的相关信息冒险返回给具有同一 ID 的其他人员。例如，即使您可以确认某个人的姓名就是 John Smith，您也可能不希望返回系统中关于所有 John Smith 的所有数据。
* 另一个示例是设备 ID，例如 Analytics Cookie ID。如果 ID 出现在手机应用程序中，您可以确定使用此 ID 的所有交互都应可用于该手机的所有者。但是，如果它出现在共享设备上，例如家用计算机或者图书馆或网吧中的计算机，您可以确定无法区分使用该设备的多名用户，而且将数据返回给其他用户的风险太大，因而不允许使用此类 ID。

## Analytics 支持的 ID 最佳实践 {#section_B6481505FF1949498D4B4B35B780D050}

使用此表可确定在向Analytics提交数据隐私请求时将使用的ID类型。 当您清楚了这个信息后，就会比较容易确定应该为变量使用的其他标签了。

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
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service Cookie( </a> ECID)，以前称为Marketing Cloud ID(MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>这些 Cookie 可识别设备，或更具体地说，可识别某设备用户的浏览器。对于使用常规登录的共享设备，此 ID 可应用于该设备的任何/所有用户。Adobe has created some <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> unified JavaScript </a> that you can place on your website to collect these cookies if you want to allow them to be used for Data Privacy requests. </p> <p>Adobe Analytics Mobile SDK 的用户还拥有 Experience Cloud ID (ECID)。SDK中有用于读取此ID的API调用，因此您可以增强应用程序以收集数据隐私请求。 </p> <p>许多公司考虑将浏览器 Cookie ID 作为共享设备 ID。因此，在与其法律团队协商后，他们可能会选择不支持将其用作数据隐私请求的可接受ID，或者在使用这些ID时，他们可能选择仅返回非常有限的数据量，或者他们可能只接受这些ID以请求删除。 </p> <p>这些 Cookie 具有无法更改的 ID-DEVICE 标签（以及 I2 和 DEL-DEVICE 标签）。默认的 Adobe Analytics 配置将只返回有关设备的一般性信息，例如设备类型、操作系统、浏览器等等，以及在使用这些 ID 时，对您的网站进行访问的时间/日期。但是，如果您选择支持以下讨论的数据隐私请求的这些ID，则可以添加或删除ACC-ALL标签，以配置您为数据隐私访问请求返回的确切字段集。 </p> <p>特别是在报表包对应移动设备应用程序，而您的移动设备应用程序又要求登录的情况下，您可以决定将该设备的 Experience Cloud ID 对应于特定的用户，这样一来，您可能希望使用 ACC-ALL 标签来标记更多的字段，其中包括已访问页面的名称、查看的产品等等。 </p> <p>注意： 如果您在数据隐私请求中指定“expandIds”选项，则除了您指定的任何其他ID之外，您的请求将始终包含Cookie ID。 更多详细信息，请参阅 <a href="../../admin/c-data-governance/gdpr-id-expansion.md" format="dita" scope="local">ID 扩展</a>。在这些情况下，对于只具有 Cookie ID 而没有其他 ID 的命中项，则仅为访问请求返回具有 ACC-ALL 标记的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义变量中的 ID </p> </td> 
   <td colname="col2"> <p>某些客户将 ID 置于<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">自定义流量变量 (prop) 或自定义转化变量 (eVar)</a> 中。最常见的是 CRM ID，其他则包括电子邮件地址、用户登录名、客户会员号或这些值的哈希值。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果要将其中一个ID用于数据隐私请求，应为包含该ID的字段提供一个ID-PERSON标签。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">（不太常见）如果其中某个自定义变量中的 ID 只识别可能由多人共享的设备，您可以改用 ID-DEVICE 标签。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">这些字段还需要 I1 或 I2 标签，并且应当包含 DEL-PERSON 或 DEL-DEVICE 标签。通常，DEL 标签的 PERSON/DEVICE 选项将与 ID 标签的 PERSON/DEVICE 选项匹配。 </li> 
    </ul> <p> 报表包中很少有一两个以上包含ID的自定义变量，您需要使用这些ID来标识数据隐私请求的数据主体。 您可能具有多个分配了 I1 或 I2 标签的变量，但是通常其中只有一个或两个变量还具有 ID-PERSON 或 ID-DEVICE 标签。 </p> </td> 
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
>Prop始终不区分大小写。 eVar 在默认情况下不区分大小写，但可通过 Adobe 客户关怀团队将其配置为区分大小写。如果您有包含ID的区分大小写的eVar，则您有责任在提交数据隐私请求时使用正确的大小写，以便请求中使用的大小写与包含这些ID的点击中使用的大小写相匹配。

删除标签 DEL-DEVICE 和 DEL-PERSON 应当谨慎使用。当应用到不包含作为数据隐私请求一部分使用的ID的变量时，历史Analytics报告中的计数（度量）几乎总是会发生变化。

* 我们建议将其中一个标签应用于标记为 I1、I2 或 S1 的任何变量。它们无法应用于未标记为 I1、I2 或 S1 的任何变量。
* The DEL-labels will result in these variables being [anonymized](../../admin/c-data-governance/gdpr-labels.md#section_F3DEE591671A4B16A8E043F91C137ECB) (the ID will be replaced with a random string prefixed with "Data Privacy-"). 在由请求中使用的 ID 所识别的所有命中项当中，将使用相同的匿名值替代原始值的所有实例。如果此字段中的原始值为这些 ID 之一，则报表量度将不会发生更改。
* 通常，如果字段具有标签 ID-DEVICE，则您还应当分配标签 DEL-DEVICE。
* 同样，如果字段具有标签 ID-PERSON，则您还应当分配标签 DEL-PERSON。
* 如果字段没有 ID- 标签，但是包含需要匿名化的识别信息，那么需要根据您的实施来选择适用的标签（DEVICE 或 PERSON）。如果您仅对数据隐私请求使用Cookie ID，则应使用DEL-DEVICE。
* 如果您在具有 ID-PERSON 标签的其他字段中使用自定义 ID，并且只希望在出现该 ID 的行中清除它，则使用 DEL-PERSON。
* 如果您使用 ID 扩展，并且希望为所有已识别设备上的所有命中项清除所有值，则使用 DEL-DEVICE。如果您愿意，可以在这种情况下应用 DEL-DEVICE 和 DEL-PERSON 标签，但 DEL-PERSON 标签并不是必需的，因为 ID 扩展意味着与人员 ID 匹配的所有行也将匹配设备 ID。
* 如果您没有指定要使用 ID 扩展，但是要为不同的请求使用设备和个人混合 ID，那么您在使用其中的任何一类 ID 时，可能希望为应当删除的变量同时指定 DEL-DEVICE 和 DEL-PERSON 标签。
* 请注意，如果在任意未被用作请求 ID（包括扩展的 ID）的变量上指定 DEL-DEVICE 或 DEL-PERSON 标签，那么该变量的唯一值将只在出现特定（或扩展）ID 的命中项上进行匿名化。即使其他命中项包含相同的值，该值也并不会在其他位置发生更新。这会导致计数（量度）发生更改。

   例如，如果您有三个点击，其中包含eVar7中的值“foo”，但其中只有一个点击还包含另一个变量中的ID，该ID与删除匹配，则该点击上的“foo”将被修改为“数据隐私-123456789”等值，而在其他两个点击中它将保持不变。 现在，展示 eVar7 唯一值数量的报表会比此前多显示一个唯一值。在显示 eVar 探顶值的报表中，只有两个实例（而不是以前的 3 个）包含值“foo”，与此同时，还会有一个实例显示新值。

## 设置访问标签的最佳实践 {#section_AC7E216F81C141FCA6A62F8836E06EE7}

通常大量字段将具有 ACC 标签，不过也有很少字段将具有任何其他标签。相应的访问标签取决于您用于数据隐私请求的ID。

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
   <td colname="col2"> <p>如果您在数据隐私请求中同时包含设备ID和人员ID，或者如果您使用自定义ID（自定义访客ID或prop或eVar中的ID），则您需要注意您使用的ACC标签。 每个访问请求将返回两对数据文件，一对包含匹配人员 ID 的命中数据，另一对则包含不匹配人员 ID 但匹配设备 ID 的命中数据。 </p> <p>“人员 ID”文件包含与人员 ID 匹配的所有命中的数据，其中所有字段都具有 ACC-PERSON 或 ACC-ALL 标签（一个文件包含所有匹配的命中，另一个文件作为摘要）。 </p> <p>“设备 ID”文件对只包含具有 ACC-ALL 标签的字段，并且只包含没有任何匹配人员 ID 的命中。这些文件可能包含由共享设备的其他用户生成的数据，因此您需要仔细考虑包含 ACC-ALL 标签的字段集。Analytics 内的默认标签功能只将此标签应用于有关设备的一般性信息字段（设备类型、操作系统、浏览器等等），以及每个命中的日期/时间。 </p> <p>您可以选择从 Adobe 同时接收设备和人员文件组，然后只共享人员文件，以免共享可能由共享设备的其他用户生成的数据。或者，您可能希望将来自一种或两种文件组的数据与您了解的其他数据主体相关信息合并到一起，并以您自己的格式返回这些信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

