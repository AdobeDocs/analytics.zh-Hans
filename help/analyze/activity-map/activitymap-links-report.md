---
description: “链接”报告报告在当前页面上找到的链接。 它不会报告为该页面收集的所有链接。
title: 链接报表
topic: Activity map
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
translation-type: tm+mt
source-git-commit: 6b27755178d156b1eaf159640d466bd84659983d

---


# 链接报表

“链接”报告报告在当前页面上找到的链接。 它不会报告为该页面收集的所有链接。

“页面上的链接”报告优惠链接的表格视图。 有时，您可能希望查看链接点击量（或其他指标）在单个视图中的排名。 这使您能够更好地将一个链接与另一个链接进行比较。 创建页面上的链接报告，其中包括页面中所有链接（按链接ID）、单击信息（#和%）和页面中区域的排名列表。 单击“活动图”工具栏中的“页面中的链接”报告按钮。

The **[!UICONTROL Links On Page]** report opens below the browser frame in the Activity Map dashboard.

## 标准模式 {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

在标准模式中，“页面上的链接”报表显示从单日到多日的链接数据，这些数据在整个日期范围内进行汇总。 将为每个链接显示以下信息：

<table id="table_3DE41B2CFA644B70AF802A3123CE51D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 栏目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 排名 </td> 
   <td colname="col2"> 在页面中排名。 在“标准模式”中，无论单击哪列，排名值都保持不变。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 链接 ID </td> 
   <td colname="col2">The link's primary ID (for more information on how primary ID is defined by the <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md">New Link Tracking Methodology</a>) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 点击 </td> 
   <td colname="col2"> 指定链接的原始点击次数及其在页面上的总点击量百分比。 如果用户在工具栏中选择其他量度，则链接报告将报告该量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地区 </td> 
   <td colname="col2"> 表示链接所在页面中的区域。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 可见性 </td> 
   <td colname="col2">与链接的可见性状态相关。 可能有两个值： 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>隐藏</b>:该链接当前在页面中，但对最终用户不可见（如“导航菜单”中的子菜单，仅当用户悬停在“父菜单”顶部时，该菜单才可见） </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>显示</b>:该链接当前显示在页面上。 但是，它可能显示在折页下方：用户必须滚动页面才能看到它。 </li>
    </ul><p>注意：如果链接被设置为“隐藏”，则不会为此链接显示叠加图。 </p></td> 
  </tr> 
 </tbody> 
</table>

**过滤数据**

When you want to zero in on a specific link, you can search for a related term in the **[!UICONTROL Filter Data]** field. 只有与搜索匹配的链接才会有叠加。 如果没有过滤器，将显示“ [活动映射设置](/help/analyze/activity-map/activitymap-overlay-settings.md) ”中指定的叠加。

## 实时模式 {#section_AC1967217B5A4532ACB01D33636F6770}

在实时模式下，“页面上的链接”报表会显示数分钟范围内的趋势数据。

![](assets/links_on_page.png)

<table id="table_61D1FB0F02894055A1AB394DE4FE4742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 栏目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 排名 </td> 
   <td colname="col2"> 在页面中排名。 在渐变或气泡叠加中，无论单击哪列，排名值都保持不变。 如果为获胜方／失败方叠加，则根据哪些链接获得／失去最多而更改排名值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 链接 ID </td> 
   <td colname="col2">链接的主ID。 有关新链接跟踪方法如何定义主ID的更 <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md"> 多信息</a>。 </td>
  </tr> 
  <tr> 
   <td colname="col1"> 链接点击次数 </td> 
   <td colname="col2"> 所选时间段的总点击量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % 更改 </td> 
   <td colname="col2"> 当前期间链接度量与上一期间链接度量之间的百分比变化。 负%变化以红色显示，以绿色显示。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 趋势 </td> 
   <td colname="col2"> 所有收集期间的折线图。 当前选定的时段由绿色标记指示。 当前悬停的时段由红色标记指示。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地区 </td> 
   <td colname="col2"> 表示链接所在页面中的区域。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 可见性 </td> 
   <td colname="col2">与链接的可见性状态相关。 可能有两个值： 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">隐藏：链接当前位于页面中，但您看不到（例如，加载页面后显示的任何链接）。 </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">显示：链接当前显示在页面上。 但是，它可能显示在折页下方：您必须滚动页面才能看到它。 </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## 排序和过滤 {#section_4B8E8233C21247CAA70DAEC2156548AD}

有时，您只需分析特定页面区域的结果（例如，左侧面板），即可决定如何组织网页中该特定区域的内容。

为此，我们为页面上的链接报告中的链接创建了一个排序和筛选功能。 筛选通过筛选器字段可用，搜索词将应用于链接ID列和链接区域列。 通过单击调用（排名、链接ID、单击、随时间变化、区域、可见性），可以进行排序，并且可以按升序和降序排序。 从“页面上的链接”报告中过滤掉链接时，叠加将从网站中消失。
