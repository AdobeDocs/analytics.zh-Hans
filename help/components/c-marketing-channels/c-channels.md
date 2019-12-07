---
description: 在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。
subtopic: Marketing channels
title: 管理营销渠道
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 管理营销渠道

在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。

以下是创建渠道的一些指示：

* 通过列出所有渠道进行预先计划，以便将所有访客点击划分到正确的渠道。
* 始终包括[内部](/help/components/c-marketing-channels/c-faq.md)点击和[直接](/help/components/c-marketing-channels/c-faq.md)点击类别的渠道。

将渠道添加到[!UICONTROL “营销渠道”]页面与在[“营销渠道处理规则”](/help/components/c-marketing-channels/t-rules.md)页面上创建规则是两项不同的操作。创建规则时，您应将规则和渠道相关联。

## 添加营销渠道 {#add-mktg-channels}

在营销渠道管理器中添加营销渠道。

> [!NOTE] 您无法删除渠道。如果您不想使用某个渠道，您可以禁用或重命名该渠道并将其保存以供日后使用。

1. 单击 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员]** &gt; **[!UICONTROL 报表包]**。
1. 在“[!UICONTROL 报表包管理器]”页面上，选择一个报表包。

   如果您选择多个报表包，则需要选择一个可将设置从模板复制到选定报表包的模板。

   请参阅 [将模板报表包设置应用于多个报表包](/help/components/c-marketing-channels/t-template.md).

1. 单击&#x200B;**[!UICONTROL 编辑设置]** &gt; **[!UICONTROL 营销渠道]** &gt; **[!UICONTROL 营销渠道管理器]**。

   如果您的报表包未定义渠道，则会显示“[自动设置](/help/components/c-marketing-channels/c-channel-autosetup.md)”页面。

1. 在“[!UICONTROL 营销渠道管理器]”页面上，单击&#x200B;**[!UICONTROL 添加渠道]**。

   当定义了 25 个渠道时，此选项便不再可用。

1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 要配置渠道规则，请单击&#x200B;**[!UICONTROL 营销渠道处理规则]**。

   请参阅[创建营销渠道处理规则](/help/components/c-marketing-channels/t-rules.md)。

## 营销渠道管理器 - 界面定义 {#mktg-channel-mgr}

[!UICONTROL “营销渠道管理器”]页面的字段定义。

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字段 </p> </th> 
   <th colname="col2" class="entry"> <p>定义 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>启用 </p> </td> 
   <td colname="col2"> <p> 启用或禁用此营销渠道。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>渠道名称 </p> </td> 
   <td colname="col2"> <p>营销渠道的易记名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>覆盖最近联系渠道 </p> </td> 
   <td colname="col2"> <p> 您可以选择是否用所选渠道覆盖现有持续的最近联系渠道。如果选中此复选框，任何渠道（包括直接和内部）都将会覆盖现有的最近联系渠道。结果会导致对不该取得信用的渠道进行转换。例如，如果用户此前已经通过免费搜索渠道取得信用，则此选项可以确保直接渠道不会接收用于转换的信用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>渠道划分 </p> </td> 
   <td colname="col2"> <p>允许您使用该值划分渠道。创建营销渠道分类时，您可以添加可能的渠道划分（子渠道）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>类型 </p> </td> 
   <td colname="col2"> <p> 指定用户访问您网站的途径。您可以选择<span class="uicontrol">在线</span>或<span class="uicontrol">离线</span>。对于通过搜索引擎或电子邮件促销活动来访的访客，使用“在线”渠道。“离线”渠道适用于通过报纸优惠券或杂志广告发现您网站的访客。离线渠道通常包括通过报表数据源导入的数据。 </p> <p>请参阅<a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/"  >数据源</a>。 </p> <p>请参阅<a href="/help/components/c-marketing-channels/t-offline-data.md"   >添加离线数据</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>颜色 </p> </td> 
   <td colname="col2"> <p>与此营销渠道关联的颜色。此颜色代表<span class="wintitle">营销渠道</span>报表中的渠道。 </p> </td> 
  </tr> 
 </tbody> 
</table>

