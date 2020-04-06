---
description: 'null'
title: Analytics 变量的数据隐私标签
uuid: a37a1278-7a0d-4e14-ae35-43bc460e7d12
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analytics 变量的数据隐私标签

## 为何要为您的数据设置标签？{#section_A075CDF3AD0744BD8CEB41CE3FB7BFB3}

许多 Adobe 客户的法律团队都对数据隐私法（GDPR、CCPA 等）进行了仔细研究，并且就如何处理数据以遵守数据隐私法做出了自己的结论。各公司之间做出的法律解释可能有所差异，客户所需的数据处理设置也可能不尽相同。由于客户对数据隐私数据处理存在不同的偏好并且具有不同的数据集，Adobe 允许 Adobe 客户以数据控制者的身份，为其独特数据自定义所需的隐私服务数据处理设置。这允许每个独特客户采用对其品牌和独特数据集最为合理的方式处理数据隐私请求。

Adobe Analytics提供了根据敏感度和合同限制标记数据的工具。 标签对于帮助：(1)识别数据主体，(2)确定作为访问请求的一部分要返回的数据，以及(3)识别作为删除请求的一部分必须删除的数据字段。

在您搞清楚要将哪些标签应用于哪些变量/字段之前，首先需要知道您在 Analytics 数据中捕获的 [ID](/help/admin/c-data-governance/gdpr-analytics-ids.md)，并确定要将哪些 ID 用于数据隐私请求。

Adobe Analytics 数据隐私实施支持以下用于身份数据、敏感数据和数据管理的标签。

## DULE 标签 {#section_B2E78130957647338495EF37DE21D6BC}

>[!NOTE] 数据使用标签和执行 (DULE) 框架旨在提供一个跨所有 Adobe 解决方案/服务/平台的统一方式，以便在整个 Adobe Experience Cloud 中捕获、传输和使用有关数据的元数据。元数据可帮助数据控制者指明哪些数据是个人信息，哪些数据是敏感数据，以及哪些合同限制与数据相关。在这个初始版本中，Analytics 只支持与数据隐私相关的 DULE 标签。随着其他Adobe产品实施对DULE标签的支持，未来发行版将引入额外的敏感数据标签以及合同标签，这有助于确保在产品之间共享的数据仅以合法允许的方式使用。

## 标识数据标签(DULE) {#identity-data-labels}

身份数据“I”标签用于对可识别或联系特定人员的数据进行分类。

<table id="table_6B5368D714424E52835D5DFE189BD080"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
   <th colname="col3" class="entry"> 其他要求 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>I1 </p> </td> 
   <td colname="col2"> <p><b>直接可识别</b>:可明确识别或允许与个人直接联系的数据，例如姓名或电子邮件地址。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_4E2AD59D119E40D28B869D0BB63B9FD9"> 
     <li id="li_AC3E99B57E3A4AE2A12BE219680AFC58">无法在事件上设置 </li> 
     <li id="li_BB66992863C8402F8D58656293F31E71">无法在销售eVar上设置 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I2 </p> </td> 
   <td colname="col2"> <p><b>间接可识别</b>:可与任何其他数据结合使用以识别或允许与个人或设备直接联系的数据。 </p> <p>不允许个人本身的身份识别，但可以与其他信息（可能或不可能由您拥有）结合以识别某人。 示例包括客户忠诚度编号或公司CRM系统使用的ID，该ID对于每个客户都是唯一的。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A0EF0F3DC5804D4FBE228946D697ABEB"> 
     <li id="li_A592EA6DA82C4D8C80E03F02ADF4E20E">无法在事件上设置 </li> 
     <li id="li_46CE7B1E84884CDAB356A6DF89397849">无法在销售eVar上设置 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 敏感数据标签(DULE) {#sensitive-data-labels}

敏感数据“S”标签用于对诸如地理数据之类的敏感数据进行分类。将来将引入其他敏感数据标签，以识别其他类型的敏感信息。

<table id="table_A778A508620545CCB37830E5CF1C75B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>S1 </p> </td> 
   <td colname="col2"> <p> 与纬度和经度相关的精确地理位置数据，可用于确定设备的准确位置（在100米或以下）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S2 </p> </td> 
   <td colname="col2"> <p> 地理位置数据可用于确定广义上的地理围栏区域。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 数据管理标签（数据隐私）{#data-governance-labels}

数据管理标签让用户能够对反映隐私相关考虑因素和合同条件的数据进行分类，以符合相关法规和公司政策规定。

**数据隐私访问标签**

<table id="table_663EFF43A454498386F7F3E60875E0F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
   <th colname="col3" class="entry"> 其他要求 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>无 </p> </td> 
   <td colname="col2"> <p>如果此变量并未包含作为数据隐私访问请求的一部分返回到数据主体的数据中必须包括的数据，请选择此选项。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-ALL </p> </td> 
   <td colname="col2"> <p>此字段中的值应当包含在<u>所有</u>数据隐私访问请求中。 </p> <p>如果此命中来自多人共享的设备，则您作为数据控制者，可以通过应用此标签来指示它是可接受的，以便将此字段中的数据与任何有权访问该共享设备的个人共享。 </p> </td> 
   <td colname="col3"> <p>将为所有数据隐私请求返回具有此标签的字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-PERSON </p> </td> 
   <td colname="col2"> <p> 仅当我们根据与 ID-PERSON 字段值匹配的数据隐私请求 ID，基本确定点击来自数据主体时，这个字段中的值才应专门用于数据隐私访问请求。 </p> </td> 
   <td colname="col3"> <p>您还必须在此报表包中的某个变量上设置ID-PERSON标签，然后使用该ID提交请求，否则此标签将永远不适用。 </p> </td> 
  </tr> 
 </tbody> 
</table>

虽然很少有变量会收到任何其他标签，但访问标签应用于许多变量。 但是，您应与您的法律团队协商，决定您收集的哪些数据应与数据主体共享。

**数据隐私删除标签**

<table id="table_59DFCE4D90214CB5972BDDE5B7391B4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
   <th colname="col3" class="entry"> 其他要求 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>与其他标签不同，这些“删除”标签并不互斥。 您可以选择两者或无。 无需单独添加“无”标签，因为只需不选中任一“删除”选项，即可指示“无”。 </p> </td> 
   <td colname="col3"> <p>仅对于包含允许点击与数据主体相关联的值（即允许识别数据主体）的字段，删除标签是必需的。 </p> <p> 其他个人信息（收藏夹、浏览／购买历史记录、健康状况等）无需删除，因为将切断与数据主体的关联。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-DEVICE </p> </td> 
   <td colname="col2"> <p>对于数据隐私删除请求，仅当命中项当中存在请求中指定的 ID-DEVICE 时，才应当对此字段中的值进行匿名化。 </p> <p>如果其他点击（不会删除）出现相同的值，则这些其他实例将不会更改。 这将导致对于在此字段上计算唯一计数的报表，计数发生更改。 在共享设备上，这可能除了数据主体之外，还会删除其他个人的标识符。 </p> <p>如果此字段还具有 ID-DEVICE 标签并且此字段中的值用作数据隐私请求的 ID，则计数不会发生更改。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_45C3A09E1F05492B97C3F3DEA7C78FBC"> 
     <li id="li_BAB277F92F284ADE9D7B6839BDD716E2">还需要I1或I2或S1标签 </li> 
     <li id="li_6DDFC0571457489CBA9D76F547247F20">无法在事件上设置 </li> 
     <li id="li_E79C6DFC6C58478EAA1504E3820D512C">无法在销售eVar上设置 </li> 
     <li id="li_B78E273212E447D49D0707E174B66DEC">无法在分类上设置 </li> 
     <li id="li_F0F52D0DE7454557A6A97063C1FBC372">您必须使用ID-DEVICE提交请求，或将expandID设置为true，否则此标签将永远不适用。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-PERSON </p> </td> 
   <td colname="col2"> <p>对于数据隐私删除请求，仅当命中项当中存在请求中指定的 ID-PERSON 时，才应当对此字段中的值进行匿名化。 </p> <p>如果其他点击出现相同的值（未删除），则这些其他值不会更改。 这将导致对于在此字段上计算唯一计数的报表，计数发生更改。 如果此字段还具有 ID-PERSON 标签并且此字段中的值用作数据隐私请求的 ID，则计数不会发生更改。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_6722E42E036E47B4B5E17DC213636D51"> 
     <li id="li_6C1A64FF68AF428A827D8C6C33E22970">还需要I1或I2或S1标签 </li> 
     <li id="li_8053533FFE874EE795C8B6043A4F73B3">无法在事件上设置 </li> 
     <li id="li_D6700CF4D03E44DDA83C4DDBB5B70CC3">无法在销售eVar上设置 </li> 
     <li id="li_B6C2B15484B344889DBF29B62E2EA8FD">无法在分类上设置 </li> 
     <li id="li_3BBD0C27D9644C2B9618457A0BFC15EF">您还必须在此报表包中的某个变量上设置ID-PERSON标签，并使用该ID提交请求，否则此标签将永远不适用。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**数据隐私身份标签**

<table id="table_F6BBC868457443A19A7B693BD6C55B4B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 标签 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
   <th colname="col3" class="entry"> 其他要求 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>无 </p> </td> 
   <td colname="col2"> <p>此变量不包含将用于数据隐私请求的 ID。 </p> </td> 
   <td colname="col3"> <p>只有当这个字段包含的 ID 是您在通过数据隐私 API 或用户界面提交访问或删除请求时要使用的 ID 时，才需要设置这些其他标签之一。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-DEVICE </p> </td> 
   <td colname="col2"> <p>该字段包含一个 ID，可用于识别数据隐私请求的设备，但无法区分共享设备的不同用户。 </p> <p>您不需要为包含 ID 的所有变量指定此标签（这是 I1/I2 标签的用途）。如果您使用存储在此变量中的 ID 提交数据隐私请求，并想要为指定的 ID 搜索此变量，请使用此标签。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_618019CB8FCA4A5C94C47636240197B2"> 
     <li id="li_0E5ADED36FF24A348FDD434E2CC8C8EE">还需要I1或I2标签 </li> 
     <li id="li_20BCFF07B2BF468C8E0D477C10B2EF9F">无法在事件上设置 </li> 
     <li id="li_0BD73EEF4184475D8E97878CF8DBEB90">无法在销售eVar上设置 </li> 
     <li id="li_129851035C4A4BF0922296B4C3BEE39B">无法在分类上设置 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-PERSON </p> </td> 
   <td colname="col2"> <p>此字段包含一个 ID，可用于识别数据隐私请求的经过身份验证的用户（特定人员）。 </p> <p>您不需要为包含 ID 的所有变量指定此标签（这是 I1/I2 标签的用途）。如果您要使用存储在此变量中的 ID 提交数据隐私请求，并想要为指定的 ID 搜索此变量，请使用此标签。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_0C7EEC8FCB5C4BCDA5D48F3C98770A67"> 
     <li id="li_2E781AE8D7A046A7996C7300CA854B86">还需要I1或I2标签 </li> 
     <li id="li_EB4C6430C218405DAAE81DEE010DCAA2">无法在事件上设置 </li> 
     <li id="li_05AA67B45974474F9DA520E8B877BA11">无法在销售eVar上设置 </li> 
     <li id="li_8A6BF4B40ED249289EAD46FE1C755FB0">无法在分类上设置 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON {#section_F0A47AF8DA384A26BD56032D0ABFD2D7}

将变量标记为ID-DEVICE或ID-PERSON时，将提示您提供命名空间。 您可以使用以前定义的命名空间，也可以定义新的环境。

**使用以前定义的命名空间**

如果您之前在登录公司中的任何报表包中为其他变量分配了ID标签，则可以选择其中一个现有命名空间。 如果此变量包含的ID类型与已用此命名空间标记的其他变量相同，并且您希望在提交请求时搜索所有这些变量，则应重用命名空间。

1. Click **[!UICONTROL Select Namespace]** and select one of the existing namespaces.
1. 单击 **[!UICONTROL Apply]**.

![](assets/namespace.png)

**定义新命名空间**

您还可以定义新命名空间。 我们建议命名空间字符串仅限于字母数字字符，加上下划线、短划线和空格。 它们将转换为全小写。

1. Click **[!UICONTROL Select Namespace]** and type in the namespace title.

   ![](assets/namespace2.png)

1. 按 **[!UICONTROL Enter]** 以添加此命名空间。只有现在才可以激活“应用”按钮。
1. 单击 **[!UICONTROL Apply]**.

指定为命名空间的字符串与您在通过数据隐私 API 提交请求时，作为“namespace”参数的值使用的字符串相同。然后，该请求将使Adobe Analytics在共享此命名空间的所有报表包中搜索您在请求中指定的ID的所有变量。

您无需在包含ID的所有变量上指定ID-DEVICE或ID-PERSON标签（I1/I2标签的用途）。 如果您要使用存储在此变量中的 ID 提交数据隐私请求，并想要为指定的 ID 搜索此变量，请使用此标签。例如，如果 eVar1 包含一个电子邮件地址，eVar2 包含一个登录用户名，但是您仅使用用户名提交请求，那么您可能会为 eVar1 设置标签 I1、ACC-PERSON、DEL-PERSON，但是为 eVar2 设置标签 I2、ACC-PERSON、DEL-PERSON，以及具有命名空间“user name”的 ID-PERSON。然后，您可以使用用户部分JSON块提交请求，例如：

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

可以对同一报表包中的不同变量使用相同的命名空间。 例如，某些自定义实施在prop和eVar中都存储CRM-ID。 如果CRM-ID始终出现在其中一个（如eVar）中，并且仅偶尔出现在另一个(prop)中，并且当不在eVar中时从不出现在prop中，则只有eVar需要ID标签和命名空间，因为Adobe只能在该eVar中搜索ID。 但是，如果 CRM-ID 有时出现在一个变量中，有时出现在另一个变量中，那么它们应该具有相同的命名空间，而且 Adobe 将搜索这两个变量，以查找指定为使用此命名空间的数据隐私请求一部分的 ID 的出现次数。所有这些变量上仍应有DEL标签，以便不管该值在何处出现，都将其匿名化。

另一个示例是，您可能有一个CRM ID，它有时通过eVar1发送，有时通过prop7发送。 然后，您会有一个处理规则，将eVar1中的值（如果存在）复制到eVar3中。 否则，它会将prop7中的值复制到eVar3中。 在此方案中，eVar3将始终包含已知的CRM ID，因此只有eVar3需要ID-PERSON标签。

>[!CAUTION]命名空间“visitorId”和“customVisitorId”是保留名称，用于识别 Analytics 旧版跟踪 Cookie 和 Analytics 客户的访客 ID。请勿将这些命名空间用于自定义流量或转换变量。

## 变量类型及其支持的数据隐私/DULE 标签{#section_CE7C3EDE1344466A98BC45E394B40762}

数据隐私/DULE 标签功能影响四大类 Analytics 变量。并非所有变量都支持所有标签。 此表显示了支持或不支持哪些标签的变量。

<table id="table_95D4416B3A8A40C28B2610D0003456E6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量类型 </th> 
   <th colname="col2" class="entry"> 支持的标签 </th> 
   <th colname="col3" class="entry"> 不支持的标签 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_0615B545A5AD43F2A6F25698A47AAD3E"> 
     <li id="li_A4B3E8E241B149C99F2A71B21227AD72">自定义成功事件 </li> 
     <li id="li_8AEF688AE9B8426C82D199E4B195330D">销售eVar </li> 
     <li id="li_DFFCA65DCC6146AEB6D47476B4D4CC3B">多值变量(mvVar) </li> 
     <li id="li_3192D08B12C249D1AAA8AAEEDE2FD7D7">层次结构变量 </li> 
    </ul> </td> 
   <td colname="col2"> <p>S1/S2 </p> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2 </p> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>分类 </p> </td> 
   <td colname="col2"> <p>I1/I2、S1/S2 </p> <p>ACC-ALL, ACC-PERSON, </p> </td> 
   <td colname="col3"> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_1C2FD4D606664965A88F10818E1C11A9"> 
     <li id="li_590975F5C7304317B22C80B20718E914">流量变量(prop) </li> 
     <li id="li_6E614B7036994434BFDA71A4424529A0">商务变量（非销售eVar） </li> 
    </ul> </td> 
   <td colname="col2"> <p>所有标签 </p> </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>大多数其他变量 </p> <p><i>（例外情况见下表）</i> </p> </td> 
   <td colname="col2"> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2、S1/S2 </p> <p>ID-DEVICE、ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
  </tr> 
 </tbody> 
</table>

## 可为其分配／修改除ACC-ALL/ACC-PERSON之外的标签的变量 {#section_4FA003003D1B4E2EBCFCDB1A7CD4A824}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 群组 </th> 
   <th colname="col2" class="entry"> 变量 </th> 
   <th colname="col3" class="entry"> 可修改的标签 </th> 
   <th colname="col4" class="entry"> 注释 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_62FA1BAA3B9245909509566D8C03F900"> 
     <li id="li_38F7C4E18ECB42C292370713F502B8EB">转化维度 </li> 
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">自定义流量维度 </li> 
    </ul> </td> 
   <td colname="col2"> <p>除分类外的所有 </p> </td> 
   <td colname="col3"> <p>全部 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>分类 </p> </td> 
   <td colname="col3"> <p>无/ I1 / I2 </p> <p>无/ S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>转化事件 </p> </td> 
   <td colname="col2"> <p>全部 </p> </td> 
   <td colname="col3"> <p>无/ S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>解决方案维度和事件 </p> </td> 
   <td colname="col2"> <p>Activity Map 链接, </p> <p>Activity Map 页面 </p> </td> 
   <td colname="col3"> <p>无/ I1 / I2 </p> <p>无/DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>变量可以包含URL参数，这些参数可能包括直接或间接可识别的数据。 如果您的实施不收集这些变量中的直接或间接可识别数据，则它们不需要身份或删除标签。 </p> <p>请注意，删除时会清除 URL 参数，但保留基本 URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数据处理维度 </p> </td> 
   <td colname="col2"> <p>自定义访客 ID </p> </td> 
   <td colname="col3"> <p>ID-DEVICE/ID-PERSON </p> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>您不可以删除 ID 或 DEL 标签（设置为“无”），但可以根据您的自定义 ID 实施，将其更改为 DEVICE 或 PERSON 变体。 </p> <p>如果您没有使用自定义访客 ID，则此设置无关紧要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">标准维度 </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">数据处理维度 </li> 
    </ul> </td> 
   <td colname="col2"> <p>IP 地址 </p> <p>IP 地址 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>您无法删除DEL标签，但可以将其更改为DEL-DEVICE或DEL-PERSON，或同时更改为DEL-DEVICE或DEL-PERSON。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ClickMap操作（旧版）, </p> <p>ClickMap Context（旧版）, </p> <p>页面, </p> <p>页面 URL、 </p> <p>原始登入页面 URL, </p> <p>反向链接, </p> <p>访问开始页面 URL </p> </td> 
   <td colname="col3"> <p>无/ I1 / I2 </p> <p>无/DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>变量可以包含URL参数，这些参数可能包括直接或间接可识别的数据。 如果您的实施不收集这些变量中的直接或间接可识别数据，则它们不需要身份或删除标签。 </p> <p>请注意，删除时会清除 URL 参数，但保留基本 URL。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 删除处理 {#section_F3DEE591671A4B16A8E043F91C137ECB}

Adobe Analytics 对数据隐私删除请求的支持旨在最大限度地减少对报表的影响。在大多数情况下，报表中显示的量度不应发生变化。在执行数据隐私删除之前运行的历史报表将与执行删除之后运行的同一报表相匹配。这是通过将已删除的数据与数据主体完全解除关联、同时又保留不可识别的数据来完成的，以便使报告的值保持一致。

下表描述了如何“删除”各种变量。这不是一个完整的列表。

<table id="table_A329C2E2645F4685BC208826D070A5F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 删除方法 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>·流量变量(prop) </p> <p>·商务变量(eVar) </p> </td> 
   <td colname="col2"> <p>现有值将被格式为“Data Privacy-356396D55C4F9C7AB3FBB2F2FA223482”的新值替换，其中“Data Privacy-”前缀后面的 32 位十六进制值是一个加密性强的 128 位伪随机数。因为现有值基本上被随机字符串替换，所以无法从这个新值确定原始值，也无法从原始值导出新值。 </p> <p>对于给定变量，若被替换的相同值存在于作为同一数据隐私请求的一部分而被删除的其他命中项中，则该值的所有实例都将被相同的新值替换。 </p> <p>如果某个值的某些实例被替换为一个删除请求，而稍后的请求删除原始值的其他（新）实例，则新替换值将与原始替换值不同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>购买 ID </p> </td> 
   <td colname="col2"> <p>现有值将被格式为“G-7588FCD8642718EC50”的新值替换，其中“G-”前缀后面的 18 位十六进制值是一个加密性强的 128 位伪随机数的前 18 位。适用于删除流量和商务变量的所有注释也适用于此处。 </p> <p>购买ID是交易ID，其主要目的是确保购买不会被记入两次，例如某人刷新其购买确认页面时。 ID本身可能会将购买与您自己的数据库中记录购买的行绑定。 在大多数情况下，无需删除此ID，因此默认情况下不会删除它。 在针对您的数据提出数据隐私删除请求之后，若仍然能够将购买行为与用户绑定，则您可能需要删除此字段，以便该访客的 Analytics 数据无法与购买者绑定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>访客 ID </p> </td> 
   <td colname="col2"> <p>值是128位整数，用加密强的128位伪随机值替换。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• MCID </p> <p>• 自定义访客 ID </p> <p>• IP 地址 </p> <p>• IP 地址 2 </p> </td> 
   <td colname="col2"> <p>清除该值（根据变量的类型，设为空字符串或 0）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>· ClickMap操作（旧版） </p> <p>· ClickMap Context（旧版） </p> <p>• 页面 </p> <p>• 页面 URL </p> <p>• 原始登入页面 URL </p> <p>• 反向链接 </p> <p>• 访问开始页面 URL </p> </td> 
   <td colname="col2"> <p>清除／删除URL参数。 如果该值看起来不像URL，则会清除该值（设置为空字符串）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• 纬度 </p> <p>• 经度 </p> </td> 
   <td colname="col2"> <p>精度降至1公里以下。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 不支持预期删除标签的变量 {#section_956B766EFFEC427E87E6CFF3A4217E86}

本节旨在阐明有关不支持删除的 Analytics 变量的信息。有时候，这些变量会被非 Analytics 用户（例如法律团队）删除，这些用户不了解变量中包含的数据类型，因此会根据变量的名称做出不正确的假设。以下是其中一些变量的列表，以及它们不需要删除、或者不需要特定的删除标签的原因。

<table id="table_6FECF3D654514862912D371E6BE4143B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 备注 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>新访客 ID </p> </td> 
   <td colname="col2"> <p>新的访客ID是一个布尔值，在我们第一次看到给定的访客ID时为true。 一旦访客ID匿名化，就无需删除它。 匿名化之后，它将与我们第一次看到这个匿名ID时相对应。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>邮政编码 </p> <p>地理邮政编码 </p> </td> 
   <td colname="col2"> <p>邮政编码仅针对源自美国的点击设置。 它们并不准备迎接来自欧盟的热播。 即使设置好，它们也只提供一个广泛的地理区域，使数据主体难以重新识别。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>地理纬度 </p> <p>地理经度 </p> </td> 
   <td colname="col2"> <p>这些属性提供从IP地址派生的粗略位置。 其准确度通常与邮政编码相似，距离实际位置只有几十公里。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户代理 </p> </td> 
   <td colname="col2"> <p>用户代理标识所使用的浏览器版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户 ID </p> </td> 
   <td colname="col2"> <p> 指定包含数据的Analytics报表包（作为数字）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>报表包 ID </p> </td> 
   <td colname="col2"> <p> 指定包含数据的Analytics报表包的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>访客 ID </p> <p>MCID / ECID </p> </td> 
   <td colname="col2"> <p> 这些标签有DEL-DEVICE标签，但无法添加DEL-PERSON标签。 If you specify <a href="/help/admin/c-data-governance/gdpr-id-expansion.md"> ID Expansion</a> with each request, then these IDs will automatically be deleted for all delete requests, even those using an ID-PERSON. </p> <p>如果您不使用ID扩展，但希望在prop或eVar中包含匹配ID的点击中匿名化这些Cookie ID，则可以通过用ID-DEVICE标签标记prop或eVar来解决此标记限制，即使它真的识别了某个人（所有DEL-PERSON标签也需要更改为DEL-DEVICE标签）)。 在这种情况下，由于只有访客ID或ECID的某些实例是匿名的，因此唯一访客计数将在历史报告中发生变化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ID </p> </td> 
   <td colname="col2"> <p> Adobe Advertising Cloud ID 是一个解决方案变量，具有不可修改的 DEL-DEVICE 标签。它使用cookie填充，就像访客ID和MCID一样。 只要删除其他ID，就应从点击中删除该ID。 有关更多详细信息，请参阅这些变量的说明。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 访问请求的日期字段 {#section_6678FB4FF42B481C9B78E64F61782397}

有五个标准变量包含时间戳：

<table id="table_49A9255366254F799E1682C30CBD98EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 时间戳 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>点击时间 (UTC) </p> </td> 
   <td colname="col2"> <p>Adobe Analytics收到点击的时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义点击时间 (UTC) </p> </td> 
   <td colname="col2"> <p>点击发生的时间，对于某些移动应用程序和其他实施，该时间可能比收到该点击的时间早。 例如，如果网络连接在发生时不可用，则应用程序可能会保持点击，并在连接可用时发送它。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期时间 </p> </td> 
   <td colname="col2"> <p>与自定义命中时间 UTC 为同一值，但在报表包的时区列显示为 UTC 而不是 GMT。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>首次点击时间 (GMT) </p> </td> 
   <td colname="col2"> <p>为此点击的访客ID值收到的第一次点击的自定义点击时间UTC值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>访问开始时间 (UTC) </p> </td> 
   <td colname="col2"> <p>针对此访客 ID 当前访问收到的首次命中的自定义命中时间 UTC 值。</p> </td> 
  </tr> 
 </tbody> 
</table>

用于生成为数据隐私访问请求返回的文件的代码，要求访问请求中至少包含前三个时间戳变量中的一个（具有一个适用于该请求类型的 ACC 标签）。若不包含上述三个中的任意一个，则“自定义命中时间 UTC”将被视为含有 ACC-ALL 标签。

为数据隐私访问请求返回的命中项级别的 CSV 文件，会将这些字段中的值从 UNIX 时间戳转换为 YYYY-MM-DD HH:MM:SS 格式的日期/时间（例如，2018-05-01 13:49:22）。在 HTML 摘要文件中，这些时间戳值将会被截断为仅包含日期（YYYY-MM-DD），以缩短这些字段中出现的唯一值的长度。
