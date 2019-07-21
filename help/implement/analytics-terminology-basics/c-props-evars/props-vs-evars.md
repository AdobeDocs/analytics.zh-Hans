---
description: Marketing Cloud 中可使用多种类型的变量。其中两种最常见的类型 Prop 和 eVar，允许您的组织对网站报告自定义维度，而标准的现成报表则无法提供此功能。
keywords: Analytics实施；prop；evar；props与evar；命名惯例；流量变量；持久性；成功事件；painse
seo-description: Marketing Cloud 中可使用多种类型的变量。其中两种最常见的类型 Prop 和 eVar，允许您的组织对网站报告自定义维度，而标准的现成报表则无法提供此功能。
seo-title: 比较 Prop 和 eVar
solution: Analytics
title: 比较 Prop 和 eVar
topic: 开发人员和实施
uuid: 0f02760f-ff69-481c-a817-799f02 dafe8 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 比较 Prop 和 eVar

Marketing Cloud 中可使用多种类型的变量。其中两种最常见的类型 Prop 和 eVar，允许您的组织对网站报告自定义维度，而标准的现成报表则无法提供此功能。

确定哪些变量应分配到哪里时，非常重要的一点是理解 Prop 与 eVar 功能之间的区别。了解这些区别可帮助您的组织确定最适用的变量类型。

**Prop 与 eVar**

以下是 prop 和 eVar 之间的主要区别：

* **命名规则**：Prop 被视为流量变量，这意味着它们可用于报告您网站上各种维度的受欢迎程度。eVar 被视为转化量度。它们可用于确定您网站对成功事件贡献最大的维度。
* **永久性**：Prop 不可独立于触发它的图像请求之外存在。它们无法与非同一图像请求中的其他变量关联。但 eVar 可永久存在。后端变量用于保存最初触发的值，以便在以后将其与成功事件关联。
* **成功事件**：成功事件，也称为转化事件，是用于度量访客达到目标的次数的量度。该事件可以是任意事件，例如在您的网站上购物，或者订阅商务通讯等等。eVar 旨在报告转化事件，以显示哪些值对访客达到您的目标影响最大。流量变量则不具备此功能。但是，如果您对报表包进行正确的配置，则可以查看参与率量度。
* **路径分析**：Prop 可以使用路径分析，此功能允许您的组织查看用户在当前所查看变量上下文中的特定浏览路径。如有需要，Adobe 代表可以启用路径分析。eVar 无法使用路径分析。
* **潜在可用的量度**：prop 和 eVar 之间可用的量度因变量的设置和数据平台/版本的不同而有很大的差异。以下列表说明可以启用的量度，而非默认启用的量度。如果您希望在报表中使用某个特定量度，但并未看到该量度，请让贵组织的一位受支持用户与客户关怀联系。

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>量度 </p> </th> 
   <th colname="col2" class="entry"> <p>Prop </p> <p>(流量变量) </p> </th> 
   <th colname="col3" class="entry"> <p>eVar </p> <p>(转化变量) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>平均页面深度 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平均逗留时间 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>跳出率 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>跳出次数 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_471A02B78FD842BB97ED3FF4A5908B03" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D2F11B5687484D9EBF6D1DEB3F303A20" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>计算量度 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_7FAB1CF2ACC44D9198C648D3FC9E52D9" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8BCC2EE92CC04778809D1BD48D2623D7" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自定义转化事件 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D75C764B83AE4491A7E68C459FED1300" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>登录 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E9A1FCDFCB924D75ABFAEBD5570D4EE0" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5E57974B5A64F3FA3A145428420EB23" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>退出 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_BE343F94EAD74D54B6ABC80E8A76A9BD" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_3183B2BB62C24B048EDED3295F2BEC85" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>实例 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8733F5AC189E43DAA8D1847416EA68C8" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_B10AB2898F3D4EBA947FADB27B118143" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面查看次数 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8BD2B23FBDA64A648BED40A2993F7C1C" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_CBDFD74340FA4973847033C1F956F0AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>参与量度 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E63F978830FB46809E62654F37C4C182" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_6AB756A4598F4452887D29AD4971985A" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>购买量度 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新载入 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_FBE0C84E01004937B7B408198A33A9E7" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>购物车量度 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_123993465D734EABB311730ED03263F6" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>单次存取 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_038C6991E3F341B18E7A355D17C88895" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>总逗留时间 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_090587D29F1649319033D5A15B34B138" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_841DF09FD32A44B1B1B876F4E0CE29AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>独特访客 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_38556E6A43B04E2E8A01855452D30A83" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5D4BDE1AA9C4C58A6402418390EEC52" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>访问次数 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_017BB279C5824028870360A5D4D27556" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **划分**：Prop 使用关联显示在同一图像请求中触发的其他流量变量的页面查看次数。eVar 使用子关系提供相对于成功事件的其他转化变量的划分。

## prop 或 eVar 的独特优势 {#section_B384031AB8674065BA5187B0A3A3DAB9}

随着版本 15 的发布，prop 和 eVar 之间的功能差异变得更加不明显。eVar 最近已经以最小的处理负载完成更新，更新后包含访问次数/独特访客等新功能以及路径功能量度。

prop 具备 eVar 的多个优势，有些甚至更胜一筹：

* prop 数据一经收集后几乎可以立即显示在报表中。eVar 则要经过 30 多分钟才能显示在报表包数据中。
* 所有的 prop 都可以启用类似于流程图的报表，让您能够看到访客在访问您的网站时所采用的路径。These pathing flow reports are available for both Props and eVars in [!UICONTROL Ad Hoc Analysis].
* prop 可以在多个级别进行关联，而 eVar 只能进行一次子关联。可以通过使用区段、为相同的数据建立关联来消除这种局限性。
* 参与量度可用于查看在一次成功事件之前，都有哪些 prop 值参与。

从另一方面来讲，eVar 相比 prop 的局限性而言也具备一些优势。

* eVar 可以将成功事件作为量度。prop 则不然。
* eVar 的有效期限可以自定义，包括为每次点击定义有效期限（不管怎样，没有永久值）。prop 无论在何种情况下都没有永久值。

路径量度（例如，总逗留时间、登录次数和退出次数）原本并不适用于 eVar。但是，近期的更新使得这些量度同样适用于 eVar，提升了 eVar 的价值。

## 选用标准 {#section_022D016A4EEB45179A15BFF044A261A4}

**Prop：**&#x200B;如果您最关注的问题是延迟，且只想用该维度测量流量（而非成功事件），可使用 prop。

**eVar：**&#x200B;如果您最关注的问题是数据划分和数据之间的关系，可使用 eVar。

>[!TIP]
>
>如果不希望eVar持续存在，您可以更改其到期以“点击”，以免超出点击范围。

