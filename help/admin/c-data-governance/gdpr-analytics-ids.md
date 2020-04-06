---
description: 'null'
title: 标签设置最佳实践
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 标签设置最佳实践

>[!NOTE]请记住，每次创建新报表包后或在现有报表包中启用新变量时，都需要对标签设置进行审核。在启用新的解决方案集成时，您可能还需要查看标签，因为它们可能会显示需要标签的新变量。 重新实施您的移动应用程序或网站可能会改变现有变量的使用方式，这也可能需要更新标签。

## 直接与间接可识别 ID {#section_030799AA1397433FBA61A2BC60A7A750}

在您搞清楚要将哪些标签应用于哪些变量/字段之前，首先需要知道您在 Analytics 数据中捕获的 ID，并确定要将哪些 ID 用于数据隐私请求。数据隐私法扩展了可视为 ID 的范围。ID分为两个大类：直接识别(标识标签：I1)和间接识别(标识标签：I2)。

* **直接可识别的ID(I1)**:可以为人命名，也可以直接联系他们。 例如某人的姓名（甚至像John Smith这样的常用姓名，可能有数百人共享）、其任何电子邮件地址或电话号码等。 无姓名的邮寄地址可能被视为直接可识别身份，尽管它只能识别家庭或企业，而不能识别该家庭或企业内的特定人。
* **间接可识别ID(I2)**:不允许个人本身的身份识别，但可以与其他信息（可能或可能不在您手中）结合，以识别某人。 例如，客户忠诚度编号或公司CRM系统使用的ID对于每个客户都是独一无二的。 按照数据隐私法规定，Analytics 使用的跟踪 Cookie 中存储的匿名 ID 虽然只能识别设备而不能识别个人，但也被视为间接可识别 ID；在一台共享设备上，这些 Cookie 无法区分该系统的不同用户。例如，虽然cookie不能用于查找包含cookie的计算机，但如果某人有权访问该计算机并定位cookie，则他们随后可以将Analytics cookie数据绑定回该计算机。

   IP地址也被视为间接可识别，因为在任何给定的时间实例中，它都可能只分配给单个设备。 但是，ISP可以并且经常为大多数用户定期更改IP地址，因此随着时间的推移，其任何用户都可能使用了IP地址。 同一内部网中的许多ISP客户或企业内的多个员工共享相同的外部IP地址也并不少见。 因此，Adobe 将不支持使用 IP 地址作为[数据隐私请求的 ID。](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests)但是，当我们接受的 ID 用于删除请求时，我们也会清除随该 ID 发生的 IP 地址。您必须确定您收集的 ID 中是否存在其他一些 ID 属于此类别（I1 或 I2），但不适合用作数据隐私请求的标识 ID。

即使贵公司在 Analytics 数据内收集了许多不同的 ID，您也可以选择只使用这些 ID 中的一部分用于数据隐私请求。原因可能包括：

* 在您自己的系统中，您可以将其中一个ID（例如，电子邮件地址）映射到其他ID（例如CRM ID）。 然后，为了保持一致性，您决定在数据隐私处理中只将 CRM ID 用于数据隐私请求。
* 您没有验证某人是否实际是与ID关联的人的方法。 例如，很难验证是否只有一个人使用过IP地址，而提交请求的人实际上就是该人。
* 某些ID可能与多个人对应，您不希望冒险将一个人的信息返回给具有相同ID的其他人。 例如，即使您可以验证某人的姓名是John Smith，您也可能不希望返回系统中所有John Smiths的所有数据。
* 另一个示例是设备ID，如Analytics Cookie ID。 如果ID在手机应用程序上出现，您可以决定使用该ID的所有交互应该对手机所有者可用。 但是，如果它出现在共享设备上（如家用计算机或图书馆或网吧中的一台），您可能会认为您无法区分该设备的用户，并且为其他用户返回数据的风险太大，无法使用此类ID。

## Analytics支持的ID最佳实践 {#section_B6481505FF1949498D4B4B35B780D050}

利用这个表格可以确定在向 Analytics 提交数据隐私请求时，您将使用的 ID 类型。了解此信息后，可更轻松地确定应用于变量的其他标签。

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID类型 </th> 
   <th colname="col2" class="entry"> 建议 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/zh_CN/whitepapers/cookies/cookies_analytics.html">（旧版）Analytics Cookie</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/zh_CN/mcvid/"> Identity 服务 Cookie </a> (ECID)，以前称为 Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>这些Cookie标识设备，或更具体地说，标识设备用户的浏览器。 对于使用通用登录名的共享设备，此ID可应用于设备的任何／所有用户。 Adobe 创建了一些<a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm">统一的 JavaScript</a>，您可以将它们置于网站中来收集这些 Cookie（如果您希望允许将这些 Cookie 用于数据隐私请求）。 </p> <p>Adobe Analytics Mobile SDK 的用户还拥有 Experience Cloud ID (ECID)。SDK 内有一些 API 调用可读取此 ID，因此您可以增强应用程序来收集此 ID 以用于数据隐私请求。 </p> <p>许多公司考虑将浏览器 Cookie ID 作为共享设备 ID。因此，在与公司的法律团队商讨之后，这些公司可能选择不支持使用这些 ID 作为数据隐私请求的可接受 ID，或者他们可能选择在使用这些 ID 时只返回非常有限的数据量或是仅接受这些 ID 用于删除请求。 </p> <p>这些Cookie具有无法更改的ID-DEVICE标签（以及I2和DEL-DEVICE标签）。 默认的Adobe Analytics配置将仅返回有关设备的通用信息，如设备类型、操作系统、浏览器等。 以及使用这些ID时访问网站的时间／日期。 但是，如果您选择支持将这些 ID 用于数据隐私请求，那么按照下面讨论的内容，您可以添加或删除 ACC-ALL 标签，以配置您希望数据隐私访问请求返回的确切字段集。 </p> <p>特别是在报表包对应移动设备应用程序，而您的移动设备应用程序又要求登录的情况下，您可以决定将该设备的 Experience Cloud ID 对应于特定的用户，这样一来，您可能希望使用 ACC-ALL 标签来标记更多的字段，其中包括已访问页面的名称、查看的产品等等。 </p> <p>请注意：如果您在数据隐私请求中指定了“expandIds”选项，那么除了您指定的任何其他 ID 之外，您的请求将始终包含 Cookie ID。更多详细信息，请参阅 <a href="/help/admin/c-data-governance/gdpr-id-expansion.md">ID 扩展</a>。在这些情况下，只有cookie ID而没有其他ID的点击将只返回标记为ACC-ALL的数据作为访问请求的一部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义变量中的 ID </p> </td> 
   <td colname="col2"> <p>某些客户将 ID 置于<a href="https://marketing.adobe.com/resources/help/zh_CN/sc/implement/props_eVars.html">自定义流量变量 (prop) 或自定义转化变量 (eVar)</a> 中。最常见的是 CRM ID，其他则包括电子邮件地址、用户登录名、客户会员号或这些值的哈希值。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果您希望将这些 ID 之一用于数据隐私请求，您应当为包含 ID 的字段设置 ID-PERSON 标签。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">（不太常见）如果其中某个自定义变量中的 ID 只识别可能由多人共享的设备，您可以改用 ID-DEVICE 标签。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">这些字段还需要I1或I2标签，并应包括DEL-PERSON或DEL-DEVICE标签。 通常，DEL标签的PERSON/DEVICE选项将与ID标签的PERSON/DEVICE选项匹配。 </li> 
    </ul> <p> 报表包很少有一个或两个以上自定义变量包含要用于识别数据隐私请求数据主体的 ID。您可能有多个分配了I1或I2标签的变量，但通常只有一两个变量也会有ID-PERSON或ID-DEVICE标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义访客 ID </p> </td> 
   <td colname="col2"> <p>即使这并不广泛使用，Analytics也支持提供自定义访客ID的实施，如果存在，则使用该ID代替传统分析跟踪Cookie。 此字段具有标签I2、ID-PERSON和DEL-PERSON。 </p> <p>许多实施从CRM ID派生此ID，因此它仅在某人登录其站点时存在。 这允许跨设备使用相同的自定义访客ID。 一个技术缺点是，在用户登录之前发生的跟踪无法绑定到在用户登录后收集的跟踪。 相反，如果您只使用自定义访客ID来标识设备，则应将ID-PERSON和DEL-PERSON标签分别更改为ID-DEVICE和DEL-DEVICE。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设置删除标签的最佳实践 {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE]Prop 始终不区分大小写。eVar 在默认情况下不区分大小写，但可通过 Adobe 客户关怀团队将其配置为区分大小写。如果您拥有一个区分大小写且包含 ID 的 eVar，您应负责在提交数据隐私请求时使用正确的大小写，以便请求中使用的大小写与包含这些 ID 的点击中使用的大小写相匹配。

删除标签 DEL-DEVICE 和 DEL-PERSON 应当谨慎使用。当应用到的变量不包含数据隐私请求中使用的 ID 时，历史 Analytics 报表中的计数（量度）几乎总要发生更改。

* 我们建议将其中一个标签应用于标记为 I1、I2 或 S1 的任何变量。它们无法应用于未标记为 I1、I2 或 S1 的任何变量。
* DEL- 标签将导致这些变量[匿名化](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)（ID 将被前缀为“Data Privacy-”的随机字符串替换）。相同的匿名值将替换所有点击中由请求中使用的ID标识的原始值的所有实例。 如果此字段中的原始值是这些ID之一，则报告量度不会更改。
* 通常，如果字段有标签ID-DEVICE，则您还应该指定标签DEL-DEVICE。
* 同样，如果字段具有标签ID-PERSON，则您还应该指定标签DEL-PERSON。
* 如果字段没有ID标签，但确实包含您希望匿名化的标识信息，则相应的标签（DEVICE或PERSON）取决于您的实现。 如果您只将 Cookie ID 用于数据隐私请求，则您应当使用 DEL-DEVICE。
* 如果您在具有ID-PERSON标签的其他字段上使用自定义ID，并且只希望在出现该ID的行上清除该ID，则使用DEL-PERSON。
* 如果您使用ID扩展，并且希望清除所有已识别设备上的所有点击的所有值，则使用DEL-DEVICE。 在这种情况下，您可以根据需要同时应用DEL-DEVICE和DEL-PERSON标签，但DEL-PERSON标签是不必要的，因为ID扩展意味着所有与人员ID匹配的行也将匹配设备ID。
* 如果不指定使用ID扩展，但将对不同请求使用设备ID和人员ID的组合，则您可能希望为使用任一类型ID时应删除的变量指定DEL-DEVICE和DEL-PERSON标签。
* 请注意，如果在任何未用作该请求的ID的变量（包括扩展ID）上指定了DEL-DEVICE或DEL-PERSON标签，则该变量中的唯一值将仅在出现指定（或扩展）ID的点击上匿名化。 如果其他点击包含相同的值，则不会在这些其他位置更新它。 这可能导致计数（度量）发生更改。

   例如，如果您在 eVar7 中有三个包含值“foo”的命中项，但其中只有一个命中项还在其他变量中包含了与删除请求匹配的 ID，那么这一个命中项当中的“foo”值将被修改为一个类似“Data Privacy-123456789”这样的值，而在其他两个命中项中，该值将保持不变。现在，展示 eVar7 唯一值数量的报表会比此前多显示一个唯一值。在显示 eVar 探顶值的报表中，只有两个实例（而不是以前的 3 个）包含值“foo”，与此同时，还会有一个实例显示新值。

## 设置访问标签的最佳实践 {#section_AC7E216F81C141FCA6A62F8836E06EE7}

通常大量字段将具有 ACC 标签，不过也有很少字段将具有任何其他标签。哪个访问标签适用将取决于您用于隐私数据请求的 ID。

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 如果您使用…… </th> 
   <th colname="col2" class="entry"> ...使用这些建议 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>仅限设备ID </p> </td> 
   <td colname="col2"> <p>如果您使用的唯一ID是cookie ID或具有ID-DEVICE标签的ID，则您应仅使用ACC-ALL标签。 </p> <p>对于每个访问请求，您将获得一对文件，其中一对文件包含与所有指定的ACC-ALL字段相匹配的每次点击对应的行，另一对文件包含此数据的摘要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>没有ID扩展的人员ID </p> </td> 
   <td colname="col2"> <p>如果您仅使用具有ID-PERSON标签的自定义ID，而未进行ID扩展，则应使用ACC-PERSON标签。 但是，您无需更改默认的ACC-ALL标签；这些字段将自动包含在访问请求中。 </p> <p>对于每个访问请求，您将获得一对文件，其中一对文件包含与所有指定的ACC-DEVICE和ACC-PERSON字段匹配的点击对应的一行，另一对文件包含此数据的摘要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>混合 ID 和/或 ID 扩展 </p> </td> 
   <td colname="col2"> <p>如果您在数据隐私请求中同时包含设备和人员 ID，或者如果您使用自定义 ID（自定义访客 ID 或者 prop 或 eVar 中的 ID），则您需要注意所使用的 ACC 标签。每个访问请求将返回两对数据文件，一对包含来自包含匹配人员ID的点击的数据，另一对包含来自不匹配人员ID但与设备ID匹配的点击的数据。 </p> <p>“人员ID”文件包含与人员ID匹配的所有点击的数据，这些点击具有ACC-PERSON或ACC-ALL标签的所有字段（一个文件包含所有匹配的点击，另一个文件则作为摘要）。 </p> <p>“设备ID”文件对仅包含具有ACC-ALL标签的字段，并且只包含不包含任何匹配人员ID的点击。 这些文件可能包含共享设备的其他用户生成的数据，因此您需要仔细考虑包含ACC-ALL标签的字段集。 Analytics中的默认标签仅将此标签应用于与设备相关的通用信息字段（设备类型、操作系统、浏览器等）加上每次点击的日期／时间。 </p> <p>您可以选择从Adobe接收设备和人员文件集，然后仅共享人员文件，以便不共享共享共享设备其他用户可能生成的数据。 或者，您可能希望将来自一个或两个集合的数据与您了解的数据主体的其他信息合并，并以您自己的格式返回它。 </p> </td> 
  </tr> 
 </tbody> 
</table>

