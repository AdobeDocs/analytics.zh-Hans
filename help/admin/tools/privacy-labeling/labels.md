---
description: Adobe Analytics 变量的数据隐私标签示例
title: Analytics 变量的数据隐私标签
feature: Data Governance
role: Admin
exl-id: b8c2143a-6e8e-465a-979b-aa8176e8d4e8
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '3757'
ht-degree: 79%

---

# Analytics 变量的数据隐私标签

作为数据控制者，Adobe 的客户有责任遵守适用的数据隐私法，例如《通用数据保护条例》（GDPR）和《加利福尼亚州消费者隐私法案》（CCPA）。客户应咨询自己的法律团队，确定应如何处理其数据才符合数据隐私法。Adobe 了解每个客户都有与隐私相关的独特需求，这就是为什么 Adobe 允许客户自定义其所需的数据隐私数据处理设置。这允许每个独特客户采用对其品牌和独特数据集最为合理的方式处理数据隐私请求。

Adobe Analytics 根据数据的敏感性和合同限制提供了数据标签设置工具。标签对于以下步骤至关重要：（1）识别数据主体，（2）确定哪些数据可在访问请求中返回，以及（3）识别必须在删除请求中删除的数据字段。

在您搞清楚要将哪些标签应用于哪些变量/字段之前，首先需要知道您在 Analytics 数据中捕获的 [ID](/help/admin/tools/privacy-labeling/best-practices.md)，并确定要将哪些 ID 用于数据隐私请求。

Adobe Analytics 数据隐私实施支持以下用于身份标识数据、敏感数据和数据管理的标签。

>[!NOTE]
>
>I1、I2、S1 和 S2 标签与 Adobe Experience Platform 中具有相应名称的 DULE 标签具有相同的含义。但是它们的用途截然不同。在 Adobe Analytics 中，这些标签用于帮助识别那些由于隐私服务请求而需要匿名化的字段。在 Adobe Experience Platform 中，它们用于访问控制、同意管理以及用于对有标签的字段强制执行营销限制。Adobe Experience Platform 支持许多 Adobe Analytics 不使用的附加标签。此外，Adobe Experience Platform 中的标签也应用于架构。如果您使用 Analytics 数据连接器将 Adobe Analytics 数据导入 Adobe Experience Platform，就需要确保在 Adobe Experience Platform 中为每个报告包所使用的架构配置适当的 DULE 标签。Adobe Analytics 中分配的标签不会自动应用于 Adobe Experience Platform 中的这些架构，因为它们仅是您可能需要应用的 DULE 标签的一个子集。此外，不同的报告包可能共享一个架构，但为具有相同编号的 prop 和 evar 分配不同的标签，而且来自其他数据源的数据集可能会共享该架构，这可能会导致对某些字段为何收到这些标签造成困惑。

## 身份标识数据标签 {#identity-data-labels}

身份标识数据“I”标签用于对可识别或联系特定人员的数据进行分类。

| 标签 | 定义 | 其他要求 |
| --- | --- | --- |
| I1 | 直接可识别：可明确识别个人或允许与个人直接联系的数据，例如姓名或电子邮件地址。 | <ul><li>无法在事件上设置</li><li>无法在促销eVar上设置</li></ul> |
| I2 | 间接可识别：可与任何其他数据结合使用来识别个人或设备或者允许与个人或设备直接联系的数据。不允许单独识别某人，但可以结合其他信息（您可能拥有也可能不拥有）来识别某人。 例如，客户忠诚度编号或公司CRM系统使用的ID（每位客户唯一）。 | <ul><li>无法在事件上设置</li><li>无法在促销eVar上设置</li></ul> |

{style="table-layout:auto"}

## 敏感数据标签 {#sensitive-data-labels}

敏感数据“S”标签用于对诸如地理数据之类的敏感数据进行分类。未来，会引入其他敏感数据标签，用于识别其他类型的敏感信息。

| 标签 | 定义 |
| --- | --- |
| S1 | 与纬度和经度相关的精确地理位置数据，可用于确定设备的确切位置（在100米或更短距离内）。 |
| S2 | 地理位置数据，可用于确定广泛定义的地理围栏区域。 |

{style="table-layout:auto"}

## 数据治理标签（数据隐私） {#data-governance-labels}

数据治理标签使用户能够对反映隐私相关考虑因素和合同条件的数据进行分类，从而帮助 Adobe 客户遵守法规和公司政策。

### 数据隐私访问标签 {#access}

| 标签 | 定义 | 其他要求 |
| --- | --- | --- |
| 无 | 如果此变量并未包含作为数据隐私访问请求的一部分返回到“数据主体”的数据中必须包括的数据，请选择此选项。 | |
| ACC-ALL | 此字段中的值应当包含在所有数据隐私访问请求中。如果此点击量来自多人共享的设备，则您作为数据控制者，可以通过应用此标签来指示它是可接受的，以便将此字段中的数据与任何有权访问该共享设备的个人共享。 | 将为所有数据隐私请求返回具有此标签的字段。 |
| ACC-PERSON | 仅当您根据与 ID-PERSON 字段值匹配的数据隐私请求 ID，基本确定点击来自“数据主体”时，这个字段中的值才应专门用于数据隐私访问请求。 | 您还必须在此报告包中的某个变量上设置了 ID-PERSON 标签，并使用该 ID 提交请求，否则将绝不会应用此标签。 |

{style="table-layout:auto"}

尽管很少会有变量设置其他任何标签，但预计访问标签将会应用到许多变量中。不过，您需要咨询您的法律团队，以决定应该将收集的哪些数据与“数据主体”共享。

### 数据隐私删除标签 {#delete}

与其他标签不同，这些“删除”标签不是互斥的。 您可以选择两者之一或无。 [!UICONTROL 无]标签不需要另外单独选择，因为不勾选任何一个“删除”选项即表示选择了[!UICONTROL 无]。

“删除”标签仅用于包含某个值的字段，该值允许点击与“数据主体”相关联（即允许标识“数据主体”）。其他个人信息（收藏夹、浏览/购买历史、健康状况等）无需删除，因为与数据主体的关联将被切断。

| 标签 | 定义 | 其他要求 |
| --- | --- | --- |
| DEL-DEVICE | 对于数据隐私删除请求，仅当点击量当中存在请求中指定的 ID-DEVICE 时，才应当对此字段中的值进行匿名化。如果相同的值出现在其他不删除的命中项中，那么将不对这些其他实例进行更改。这会导致在此字段中计算独特计数的报告的计数发生更改。在共享设备上，这可能会移除其他个人（不仅仅是“数据主体”）的标识符。 如果此字段还具有 ID-DEVICE 标签并且此字段中的值用作数据隐私请求的 ID，则计数不会发生更改。 | <ul><li>还需要I1、I2或S1标签</li><li>无法在事件上设置</li><li>无法在促销eVar上设置</li></li><li>无法在分类上设置</li><li>您必须使用ID-DEVICE提交请求，或者将expandIDs设置为true ，否则将绝不会应用此标签。</li></ul> |
| DEL-PERSON | 对于数据隐私删除请求，仅当点击量当中存在请求中指定的 ID-PERSON 时，才应当对此字段中的值进行匿名化。如果相同的值出现在其他不删除的点击中，那么将不对这些其他值进行更改。这会导致在此字段中计算独特计数的报告的计数发生更改。如果此字段还具有 ID-PERSON 标签并且此字段中的值用作数据隐私请求的 ID，则计数不会发生更改。 | <ul><li>还需要I1、I2或S1标签</li><li>无法在事件上设置</li><li>无法在促销eVar上设置</li></li><li>无法在分类上设置</li><li>您还必须通过此报告包中的某个变量上设置的 ID-PERSON 标签提交请求，并使用该 ID 提交请求，否则将绝不会应用此标签。</li></ul> |

{style="table-layout:auto"}

### 数据隐私身份标签 {#identity}

| 标签 | 定义 | 其他要求 |
| --- | --- | --- |
| 无 | 此变量不包含将用于数据隐私请求的 ID。 | 只有此字段包含您将在通过 [Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans) 或 UI 提交访问或删除请求时使用的 ID，才需要设置这些其他标签之一。 |
| ID-DEVICE | 此字段包含一个 ID，它可用于为数据隐私请求识别设备，但无法区分共享设备的不同用户。您不需要为包含 ID 的所有变量指定此标签（这是 I1/I2 标签的用途）。如果您使用存储在此变量中的 ID 提交数据隐私请求，并想要为指定的 ID 搜索此变量，请使用此标签。 | 还需要 I1 或 I2 标签.<ul><li>无法在事件上设置</li><li>无法在促销eVar上设置</li><li>无法在分类上设置</li></ul> |
| ID-PERSON | 此字段包含一个 ID，它可用于为数据隐私请求识别经过身份验证的用户（特定人员）。您不需要为包含 ID 的所有变量指定此标签（这是 I1/I2 标签的用途）。如果您要使用存储在此变量中的 ID 提交数据隐私请求，并想要为指定的 ID 搜索此变量，请使用此标签。 | <ul><li>还需要 I1 或 I2 标签.</li><li>无法在事件上设置</li><li>无法在促销eVar上设置</li><li>无法在分类上设置</li></ul> |

{style="table-layout:auto"}

## 在为变量设置 ID-DEVICE 或 ID-PERSON 标签时提供命名空间 {#provide-namespace}

在为变量设置 ID-DEVICE 或 ID-PERSON 标签时，系统会提示您提供一个命名空间。您可以使用先前已定义的命名空间或者定义一个新的命名空间。

### 使用先前已定义的命名空间 {#previously-defined}

如果以前为登录公司的任何报告包中的其他变量分配了 ID 标签，则可选择这些现有的命名空间之一。如果此变量包含的ID类型与已使用此命名空间标记的其他变量包含的ID类型相同，并且您希望在提交请求时搜索所有这些ID，则应重用命名空间。

1. 单击&#x200B;**[!UICONTROL 选择命名空间]**，然后选择其中一个现有的命名空间。
   ![](assets/namespace.png)
1. 单击&#x200B;**[!UICONTROL 应用]**。


### 定义新的命名空间 {#define}

您还可以定义新的命名空间。 我们建议将命名空间字符串限制为字母数字字符以及字符下划线、短划线和空格。 它们将转换为全部小写。

1. 单击&#x200B;**[!UICONTROL 选择命名空间]**&#x200B;并键入命名空间标题。

   ![](assets/namespace2.png)

1. 按&#x200B;**[!UICONTROL Enter]**&#x200B;以添加此命名空间。只有现在才可以激活“应用”按钮。
1. 单击&#x200B;**[!UICONTROL 应用]**。

指定为命名空间的字符串与您在通过数据隐私 API 提交请求时，作为“namespace”参数的值使用的字符串相同。随后，该请求将促使 Adobe Analytics 搜索报告包中的所有变量，这些变量与该请求指定的 ID 共享此命名空间。

您不需要为包含 ID 的所有变量指定 ID-DEVICE 或 ID-PERSON 标签（这是 I1/I2 标签的用途）。如果您要使用存储在此变量中的 ID 提交数据隐私请求，并想要为指定的 ID 搜索此变量，请使用此标签。例如，如果 eVar1 包含一个电子邮件地址，eVar2 包含一个登录用户名，但是您仅使用用户名提交请求，那么您可能会为 eVar1 设置标签 I1、ACC-PERSON、DEL-PERSON，但是为 eVar2 设置标签 I2、ACC-PERSON、DEL-PERSON，以及具有命名空间“user name”的 ID-PERSON。然后，您可以使用用户部分JSON块提交请求，例如：

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

在同一个报告包中，为不同变量使用相同的命名空间是可以接受的。例如，某些自定义实施会将CRM-ID存储在prop和eVar中。 如果 CRM-ID 总是出现在这两者的其中一个当中（例如 eVar）、只是偶尔出现在另外一个当中 (prop)，并且当 CRM-ID 没有出现在 eVar 中时它也绝不会出现在 prop 中，那么，只有 eVar 需要 ID 标签和命名空间，这是因为 Adobe 可以只在该 eVar 中搜索 ID。但是，如果 CRM-ID 有时出现在一个变量中，有时出现在另一个变量中，那么它们应该具有相同的命名空间，而且 Adobe 将搜索这两个变量，以查找指定为使用此命名空间的数据隐私请求一部分的 ID 的出现次数。您仍应该在所有这些变量上具有DEL标签，以便无论值出现在何处，都对其进行匿名处理。

再比如，您可能有一个CRM ID，该ID有时通过eVar1发送，有时通过prop7发送。 然后，您有一个处理规则，将该值从eVar1（如果存在）复制到eVar3。 否则，它会将 prop7 的值复制到 eVar3。在这种情况下，如果 CRM ID是已知的，eVar3 将始终包含该 CRM ID，因此只有 eVar3 需要 ID-PERSON 标签。

>[!CAUTION]
>
>命名空间 `visitorId` 和 `customVisitorId` 是保留名称，用于识别 Analytics 旧版跟踪 Cookie 和 Analytics 客户的访客 ID。请勿将这些命名空间用于自定义流量或转化变量。

## 变量类型及其支持的“数据隐私”标签 {#variable-types}

“数据隐私”标签功能影响四大类 Analytics 变量。 并非所有变量都支持所有标签。下表显示了各类变量对各种标签的支持情况。

| 变量类型 | 支持的标签 | 不支持的标签 |
|--- |--- |--- |
| <ul><li>自定义成功事件</li><li>促销 eVar</li><li>多值变量(mvVar)</li><li>层次结构变量</li></ul> | <ul><li>S1/S2</li><li>ACC-ALL、ACC-PERSON</li></ul> | <ul><li>I1/I2</li>  <li>ID-DEVICE、ID-PERSON</li><li>DEL-DEVICE， DEL-PERSON</li></ul> |
| 分类 | <ul><li>I1/I2 、 S1/S2</li><li>ACC-ALL、ACC-PERSON</li></ul> | <ul><li>ID-DEVICE、ID-PERSON</li><li>DEL-DEVICE， DEL-PERSON</li></ul> |
| <ul><li>流量变量(prop)</li><li>Commerce变量（非推销eVar）</li></ul> | 所有标签 | - |
| 大多数其他变量（*请参阅下表了解例外情况*） | ACC-ALL、ACC-PERSON | <ul><li>I1/I2 、 S1/S2</li><li>ID-DEVICE、ID-PERSON</li><li>DEL-DEVICE、DEL-PERSON</li></ul> |

{style="table-layout:auto"}

## 可为其分配/修改除 ACC-ALL/ACC-PERSON 以外的标签的变量 {#variables}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 组 </th> 
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
   <td colname="col2"> <p>全部（分类除外） </p> </td> 
   <td colname="col3"> <p>全部 </p> </td> 
   <td colname="col4"> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>流量变量 </p> </td> 
   <td colname="col2"> <p>列表属性 </p> </td> 
   <td colname="col3"> <p>无 / S1 / S2 </p> </td> 
   <td colname="col4"> <p>列表属性可能包含多个值，并且不允许作为隐私标识符。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>分类 </p> </td> 
   <td colname="col3"> <p>无/ I1 / I2 </p> <p>无 / S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>转化事件 </p> </td> 
   <td colname="col2"> <p>全部 </p> </td> 
   <td colname="col3"> <p>无 / S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>解决方案维度和事件 </p> </td> 
   <td colname="col2"> <p>Activity Map 链接、 </p> <p>Activity Map 页面 </p> </td> 
   <td colname="col3"> <p>无/ I1 / I2 </p> <p>无/ DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>变量可以包含URL参数，这些参数可能包含直接或间接可识别的数据。 如果您的实施不收集这些变量中的直接或间接可识别数据，则它们不需要身份标识或删除标签。 </p> <p>请注意，删除时会清除 URL 参数，但保留基本 URL。 </p> </td> 
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
   <td colname="col4"> <p>不能删除DEL标签，但可以将其更改为DEL-DEVICE或DEL-PERSON，或同时更改为两者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ClickMap操作（旧版）、 </p> <p>ClickMap上下文（旧版）、 </p> <p>页面, </p> <p>页面 URL、 </p> <p>原始登入页面 URL、 </p> <p>反向链接、 </p> <p>访问起始页 URL </p> </td> 
   <td colname="col3"> <p>无/ I1 / I2 </p> <p>无/ DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>变量可以包含URL参数，这些参数可能包含直接或间接可识别的数据。 如果您的实施不收集这些变量中的直接或间接可识别数据，则它们不需要身份标识或删除标签。 </p> <p>请注意，删除时会清除 URL 参数，但保留基本 URL。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 删除处理 {#deletion}

Adobe Analytics 对数据隐私删除请求的支持旨在最大限度地减少对报告的影响。在大多数情况下，报告中显示的量度不应发生变化。在执行数据隐私删除之前运行的历史报告将与执行删除之后运行的同一报告相匹配。这是通过将已删除的数据与“数据主体”完全解除关联、同时又保留不可识别的数据来完成的，以便使报告的值保持一致。

下表描述了如何“删除”各种变量。这不是完整的列表。

| 变量 | 删除方法 |
| --- | --- |
| <ul><li>流量变量 (prop)</li><li>商务变量 (eVar)</li></ul> | 现有值将被格式为“Data Privacy-356396D55C4F9C7AB3FBB2F2FA223482”的新值替换，其中“Data Privacy-”前缀后面的 32 位十六进制值是一个加密性强的 128 位伪随机数。<p>因为现有值基本上被随机字符串替换，所以无法从这个新值确定原始值，也无法从原始值导出新值。对于给定变量，若被替换的相同值存在于作为同一数据隐私请求的一部分而被删除的其他点击量中，则该值的所有实例都将被相同的新值替换。<p>如果某个值的某些实例被替换为删除请求，而随后的请求删除了原始值的其他（新）实例，则新替换值将与原始替换值不同。 |
| 购买 ID | 现有值将被格式为“G-7588FCD8642718EC50”的新值替换，其中“G-”前缀后面的 18 位十六进制值是一个加密性强的 128 位伪随机数的前 18 位。适用于删除流量和商务变量的所有注释也在此处适用。<p>购买ID是一个交易ID，其主要用途是确保购买不会被计入两次，例如，当有人刷新其购买确认页面时。 ID本身可能会将购买绑定到您自己的数据库中记录该购买的行。 大多数情况下无需删除该 ID，因此默认不会删除它。<p>在针对您的数据提出数据隐私删除请求之后，若仍然能够将购买行为与用户绑定，则您可能需要删除此字段，以便该访客的 Analytics 数据无法与购买者绑定。 |
| 访客 ID | 值是128位整数，替换为加密性强的128位伪随机值。 |
| <ul><li>MCID</li><li>自定义访客 ID</li><li>IP 地址</li><li>IP 地址 2 | 清除该值（根据变量的类型，设为空字符串或 0）。 |
| <ul><li>ClickMap 操作（旧版）</li><li>ClickMap 上下文（旧版）</li><li>页面</li><li>页面 URL</li><li>原始登入页面 URL</li><li>反向链接</li><li>访问起始页 URL</li></ul> | 已清除/删除URL参数。 如果该值不像URL，则清除该值（设置为空字符串）。 |
| <ul><li>纬度</li><li>经度</li></ul> | 精度降低到不低于 1 公里。 |

{style="table-layout:auto"}

## 可能不支持预期“删除”标签的变量 {#no-delete-support}

本节旨在阐明有关可能不支持删除的 Analytics 变量的信息。有时候，这些变量会被非 Analytics 用户（例如法律团队）删除，这些用户不了解变量中包含的数据类型，因此会根据变量的名称做出假设。

在做出有关标签或删除的决定之前，了解每个变量中包含的数据类型非常重要，而不是仅依赖变量名称。以下是其中一些变量的列表，以及它们可能不需要删除、或者可能不需要特定的删除标签的原因：

| 变量 | 评论 |
| --- | --- |
| [!UICONTROL 新访客 ID] | “新访客 ID”是一个布尔值，如果给定的访客 ID 是我们第一次看到，则该值为 True。访客ID匿名化后，无需将其删除。 在匿名化之后，它将对应于我们第一次看到这个匿名化的ID。 |
| [!UICONTROL 邮政编码]<p>[!UICONTROL 地理邮政编码] | 邮政编码已设置为仅适用于来自美国的点击。对于来自欧盟地区的点击，未设置邮政编码。即使设置了邮政编码，它们也只能提供大致的地理区域，很难用来重新识别“数据主体”。 |
| [!UICONTROL 地理纬度]<p>[!UICONTROL 地理经度] | 它们提供了从IP地址派生的粗略位置。 其准确性通常与邮政编码类似，但实际位置只有几十公里。 |
| [!UICONTROL 用户代理] | 用户代理识别所用浏览器的版本。 |
| [!UICONTROL 用户 ID] | 指定包含该数据的 Analytics 报告包（以数字表示）。 |
| [!UICONTROL 报告包 ID] | 指定包含该数据的 Analytics 报告包的名称。 |
| [!UICONTROL 访客 ID]<p>[!UICONTROL MCID] / [!UICONTROL ECID] | 这些 ID 具有 DEL-DEVICE 标签，但不能添加 DEL-PERSON 标签。如果您希望发生 prop 或 eVar 中包含匹配 ID 的点击时这些 Cookie ID 被匿名化，那么即使该 prop 或 eVar 可真正识别个人，您也可以通过为其设置 ID-DEVICE 标签来解决此标签限制（也需要将所有 DEL-PERSON 标签更改为 DEL-DEVICE 标签）。在这种情况下，由于只有访客 ID 或 ECID 的部分实例被匿名化，因此历史报告中的独特访客计数将发生变化。 |
| [!UICONTROL AMO ID] | Adobe Advertising ID是一个解决方案变量，具有不可修改的[!UICONTROL DEL-DEVICE]标签。 它通过Cookie填充，就像访客ID和MCID一样。 只要删除这些其他 ID，它就会从点击量当中删除。有关更多详细信息，请参阅这些变量的描述。 |

{style="table-layout:auto"}

## 访问请求的日期字段 {#access-requests}

共有五个标准变量包含时间戳：

| 时间戳 | 定义 |
| --- | --- |
| 点击时间 UTC | Adobe Analytics 接收到点击量的时间。 |
| 自定义点击时间 UTC | 发生点击的时间，某些移动应用程序和其他实施的点击发生时间可能会早于接收时间。例如，当点击发生时但网络连接不可用，应用程序可能会保留该点击量，并在网络连接可用时将其发出。 |
| 日期时间 | 与自定义点击时间 UTC 为同一值，但在报告包的时区列显示为 UTC 而不是 GMT。 |
| 首次点击时间 GMT | 针对此点击的访客 ID 值收到的首次点击的自定义点击时间 UTC 值。 |
| 访问开始时间 (UTC) | 针对此访客 ID 当前访问收到的首次点击的自定义点击时间 UTC 值。 |

{style="table-layout:auto"}

用于生成为数据隐私访问请求返回的文件的代码，要求访问请求中至少包含前三个时间戳变量中的一个（具有一个适用于该请求类型的 ACC 标签）。若不包含上述三个中的任意一个，则“自定义点击时间 UTC”将被视为含有 ACC-ALL 标签。

为数据隐私访问请求返回的点击级别 CSV 文件将这些字段中的值从 unix 时间戳转换为 `YYYY-MM-DD HH:MM:SS` 格式的日期/时间字段（例如，`2018-05-01 13:49:22`）。在摘要 HTML 文件中，这些时间戳值将被截断为仅包括日期 `YYYY-MM-DD`，以缩短这些字段中出现的唯一值的长度。
