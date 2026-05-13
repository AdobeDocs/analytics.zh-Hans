---
description: 了解您在 Analytics 数据中捕获的 ID，并确定要将哪些 ID 用于数据隐私请求。
title: 标签设置最佳实践
feature: Data Governance
role: Admin
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
TQID: https://experienceleague.adobe.com/btvouuszSZn1h7xDCInebbqYE9vb1bwcU4-DMW3l3oM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 2340
ht-degree: 64%

---

# 标签设置最佳实践

每次创建新报告包或在现有报告包中启用一个新变量时，都需要对标签设置进行审核。 在启用新的解决方案集成时，您可能还需要审核标签设置，因为它们可能会公开需要设置标签的新变量。 重新实施您的移动设备应用程序或网站可能会更改现有变量的使用方式，这或许也需要更新标签。

I1、I2、S1 和 S2 标签与 Adobe Experience Platform 中具有相应名称的 DULE 标签具有相同的含义。 但是它们的用途截然不同。 在 Adobe Analytics 中，这些标签用于帮助识别那些由于隐私服务请求而需要匿名化的字段。 在 Adobe Experience Platform 中，它们用于访问控制、同意管理以及用于对有标签的字段强制执行营销限制。 Adobe Experience Platform 支持许多 Adobe Analytics 不使用的附加标签。 如果您使用 Analytics 数据连接器将 Adobe Analytics 数据导入 Adobe Experience Platform，就应确保在 Adobe Analytics 中应用的任何 I1、I2、S1 和 S2 标签也应用于 Adobe Experience Platform 中被导入的报告包所使用的架构。

## 直接与间接可识别 ID {#direct-vs-indirect}

在您搞清楚要将哪些标签应用于哪些变量/字段之前，首先需要知道您在 Analytics 数据中捕获的 ID，并确定要将哪些 ID 用于数据隐私请求。 数据隐私法扩展了可视为 ID 的范围。 ID可分为两大类：可直接识别（身份标签：I1）和间接识别（身份标签：I2）。

* **可直接识别身份的ID (I1)**：可命名人员或提供直接联系人员的方法。 例如：某人的姓名（甚至包括像“约翰”这样可能会被数百人分享的常见姓名）、任何电子邮件地址或电话号码等。一个没有名字的邮寄地址可能会被认为可以直接识别，尽管它只能识别一个家庭或企业，而不是该家庭或企业中的特定人员。
* **可间接识别身份的ID (I2)**：不允许单独识别个人，但可以与其他信息（可能拥有也可能不拥有）结合使用，以识别某人。 间接可识别 ID 的示例包括客户会员号，或公司的 CRM 系统为其每个客户使用的唯一 ID。 按照数据隐私法规定，Analytics 使用的跟踪 Cookie 中存储的匿名 ID 虽然只能识别设备而不能识别个人，但也被视为间接可识别 ID；在一台共享设备上，这些 Cookie 无法区分该系统的不同用户。 例如，虽然 Cookie 不能用于查找包含该 Cookie 的计算机，但如果有人能够访问该计算机并找到该 Cookie，则他们可以将该 Analytics Cookie 数据绑定到该计算机。

IP 地址也被视为间接可识别 ID，因为在任何给定时刻，它只能被分配到一个设备。 但是，ISP可以而且经常会定期更改大多数用户的IP地址，因此随着时间的推移，IP地址可能已被他们的任何用户使用。 ISP的许多客户或同一企业内联网上同一企业的多个员工共享同一外部IP地址的情况也很常见。 因此，Adobe 不支持使用 IP 地址作为数据隐私请求的 ID。 但是，当我们接受的 ID 用于删除请求时，我们也会清除随该 ID 发生的 IP 地址。 您必须确定是否存在其他一些收集的 ID 属于此类别（I1 或 I2），但不适合用作数据隐私请求的标识 ID。

即使贵公司在 Analytics 数据内收集了许多不同的 ID，您也可以选择只使用这些 ID 中的一部分用于数据隐私请求。 原因可能包括：

* 在您自己的系统中，可以将其中一个ID（例如电子邮件地址）映射到另一个ID（例如CRM ID）。 然后，为了保持一致性，您决定在数据隐私处理中只将 CRM ID 用于数据隐私请求。
* 您没有方法验证某人是否是与ID关联的实际人员。 例如，可能很难验证某个IP地址只由一个人使用，并且提交请求的人实际上就是该人。
* 某些 ID 可能对应多个人员，而您不希望将某个人的相关信息冒险返回给具有同一 ID 的其他人员。 例如，即使您可以验证某人的姓名是否为约翰史密斯，您可能也不希望返回系统中有关所有约翰史密斯的所有数据。
* 另一个示例是设备ID，如Analytics Cookie ID。 如果该ID发生在手机应用程序上，则可以决定使用该ID的所有交互都应可供手机所有者使用。 但是，如果这种情况发生在共享设备上，例如家庭计算机或库或网吧中的设备，您可能会认为无法区分该设备的用户，并且为不同用户返回数据的风险太大，因此无法使用此类型的ID。

## Analytics 支持的 ID 最佳实践 {#best-practices-an}

利用这个表格可以确定在向 Analytics 提交数据隐私请求时，您将使用的 ID 类型。 了解此信息后，将更易于确定变量应使用的其他标签。

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
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans"> 身份标识服务 Cookie </a> (ECID)，以前称为 Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>这些Cookie标识设备，或者更具体地说，标识设备的用户的浏览器。 对于使用通用登录的共享设备，此ID可应用于设备的任何/所有用户。 Adobe 创建了一些<a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/">统一的 JavaScript</a>，您可以将它们置于网站中来收集这些 Cookie（如果您希望允许将这些 Cookie 用于数据隐私请求）。 </p> <p>Adobe Analytics Mobile SDK 的用户还拥有 Experience Cloud ID (ECID)。 SDK 内有一些 API 调用可读取此 ID，因此您可以增强应用程序来收集此 ID 以用于数据隐私请求。 </p> <p>许多公司考虑将浏览器 Cookie ID 作为共享设备 ID。 因此，在与法律团队协商后，这些公司可能会选择不支持将它们用作数据隐私请求的可接受 ID。 或者，它们可能会选择在使用这些 ID 时仅返回非常有限的数据量，或者它们可能只接受删除请求。 </p> <p>这些Cookie具有无法更改的ID-DEVICE标签（以及I2和DEL-DEVICE标签）。 默认的Adobe Analytics配置将仅返回有关设备的常规信息，如设备类型、操作系统、浏览器等，以及在使用这些ID时访问您网站的时间/日期。 但是，如果您选择支持将这些 ID 用于数据隐私请求，那么按照下面讨论的内容，您可以添加或删除 ACC-ALL 标签，以配置您希望数据隐私访问请求返回的确切字段集。 </p> <p>如果报告包对应于需要登录的移动应用程序，您可以确定设备的 Experience Cloud ID 确实对应于特定用户。 在这种情况下，您可能希望使用 ACC-ALL 标签标记更多字段，包括访问过的页面名称、查看过的产品等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义变量中的 ID </p> </td> 
   <td colname="col2"> <p>某些客户将 ID 置于<a href="/help/implement/vars/page-vars/evar.md">自定义流量变量 (prop) 或自定义转化变量 (eVar)</a> 中。 最常见的是 CRM ID，其他则包括电子邮件地址、用户登录名、客户会员号或这些值的哈希值。 </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">如果您希望将这些 ID 之一用于数据隐私请求，您应当为包含 ID 的字段设置 ID-PERSON 标签。 </li> 
     <li id="li_94541340B054436297C5565F074413DC">（不太常见）如果其中某个自定义变量中的 ID 只识别可能由多人共享的设备，您可以改用 ID-DEVICE 标签。 </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">这些字段还需要I1或I2标签，并且应该包括DEL-PERSON或DEL-DEVICE标签。 通常， DEL标签的PERSON/DEVICE选项将与ID标签的PERSON/DEVICE选项匹配。 </li> 
    </ul> <p> 报告包很少有一个或两个以上自定义变量包含要用于识别数据隐私请求“数据主体”的 ID。 您可能具有多个分配了I1或I2标签的变量，但通常其中只有一两个变量具有ID-PERSON或ID-DEVICE标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义访客 ID </p> </td> 
   <td colname="col2"> <p>虽然自定义访客ID没有得到广泛使用，但是Analytics也支持可以提供该访客ID的实施，如果存在，该ID将用来替代旧版Analytics跟踪Cookie。 此字段具有标签I2、ID-PERSON和DEL-PERSON。 </p> <p>许多实施从 CRM ID 派生此 ID，因此它仅在某人登录其网站时存在。 这允许跨设备使用相同的自定义访客ID。 一个技术缺陷是，在用户登录之前发生的跟踪不能与登录之后收集的跟踪相关联。 相反，如果您使用自定义访客ID来简单地识别设备，则应当分别将ID-PERSON和DEL-PERSON标签更改为ID-DEVICE和DEL-DEVICE。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设置删除标签的最佳实践 {#best-practices-delete}

>[!NOTE]
>
>Prop 始终不区分大小写。 eVar 在默认情况下不区分大小写，但可通过 Adobe 客户关怀团队将其配置为区分大小写。 如果您拥有一个区分大小写且包含 ID 的 eVar，您应负责在提交数据隐私请求时使用正确的大小写，以便请求中使用的大小写与包含这些 ID 的点击中使用的大小写相匹配。

删除标签 DEL-DEVICE 和 DEL-PERSON 应当谨慎使用。 当应用到的变量不包含数据隐私请求中使用的 ID 时，历史 Analytics 报告中的计数（量度）几乎总要发生更改。

* 我们建议将其中一个标签应用于标记为 I1、I2 或 S1 的任何变量。 它们无法应用于未标记为 I1、I2 或 S1 的任何变量。
* DEL- 标签将导致这些变量[匿名化](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels)（ID 将被前缀为“Data Privacy-”的随机字符串替换）。 在由请求中使用的 ID 所识别的所有点击量当中，将使用相同的匿名值替代原始值的所有实例。 如果此字段中的原始值为这些 ID 之一，则报告量度将不会发生更改。
* 通常，如果某个字段的标签为ID-DEVICE ，那么您也应该为标签指定DEL-DEVICE 。
* 同样，如果字段的标签为ID-PERSON，则您也应该为字段分配标签DEL-PERSON。
* 如果字段没有ID — 标签，但包含您希望匿名处理的标识信息，则应根据您的实施采用相应的标签（DEVICE或PERSON）。 如果您只将 Cookie ID 用于数据隐私请求，则您应当使用 DEL-DEVICE。
* 如果您在具有 ID-PERSON 标签的其他字段中使用自定义 ID，并且只希望在出现该 ID 的行中清除它，则使用 DEL-PERSON。
* 请注意，如果在任意未被用作请求 ID（包括扩展的 ID）的变量上指定 DEL-DEVICE 或 DEL-PERSON 标签，那么该变量的唯一值将只在出现特定（或扩展）ID 的点击量上进行匿名化。 即使其他点击量包含相同的值，该值也并不会在其他位置发生更新。 这可能会导致计数（量度）发生更改。

  例如，如果您在 eVar7 中有三个包含值“foo”的点击量，但其中只有一个点击量还在其他变量中包含了与删除请求匹配的 ID，那么这一个点击量当中的“foo”值将被修改为一个类似“Data Privacy-123456789”这样的值，而在其他两个点击量中，该值将保持不变。 现在，展示 eVar7 唯一值数量的报告会比此前多显示一个唯一值。 在显示 eVar 探顶值的报告中，只有两个实例（而不是以前的 3 个）包含值“foo”，与此同时，还会有一个实例显示新值。

## 设置访问标签的最佳实践 {#best-practices-access}

通常大量字段将具有 ACC 标签，不过也有很少字段将具有任何其他标签。 哪个访问标签适用将取决于您用于隐私数据请求的 ID。

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 如果您使用... </th> 
   <th colname="col2" class="entry"> ...使用这些推荐 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>仅设备ID </p> </td> 
   <td colname="col2"> <p>如果您使用的唯一ID是Cookie ID或带有ID-DEVICE标签的ID，则您应该只使用ACC-ALL标签。 </p> <p>对于每个访问请求，您将获得一对文件：其中一个文件包含与每个匹配点击量对应的一行以及所有指定的 ACC-ALL 字段，另一个摘要文件则包含该数据的摘要。 </p> </td> 
  </tr> 
 </tbody> 
</table>
