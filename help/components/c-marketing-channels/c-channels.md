---
description: 在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。
seo-description: 在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。
seo-title: 管理营销渠道
solution: Analytics
subtopic: 营销渠道
title: 管理营销渠道
topic: Reports & Analytics
uuid: 9d367bb6-a17 b-49b8-9cd5-24fac35 ae982
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 管理营销渠道

在营销渠道管理器中添加或启用营销渠道。对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。

## Manage marketing channels {#topic_45CF1C6A783B4F96ABF6317EAB6A854F}

Add or enable marketing channels in the [!UICONTROL Marketing Channel Manager]. 对于没有营销渠道的报表包，自动设置让您可以创建多个渠道及渠道规则。您可以编辑预定义渠道以满足您的需求，或创建您自己的渠道（最多 25 个）。

以下是创建渠道的一些指示：

* 通过列出所有渠道进行预先计划，以便将所有访客点击划分到正确的渠道。
* 始终包括[内部](../../components/c-marketing-channels/c-faq.md#section_179A2BE5C8E24719A9E5C0DC09AF0947)点击和[直接](../../components/c-marketing-channels/c-faq.md#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A)点击类别的渠道。

将渠道添加到[!UICONTROL “营销渠道”]页面与在[“营销渠道处理规则”](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08)页面上创建规则是两项不同的操作。创建规则时，您应将规则和渠道相关联。

## 添加营销渠道 {#task_98C9D3F5DBBC4B198E0A9ED4D3891E03}

在营销渠道管理器中添加营销渠道。

>[!NOTE]
>
>无法删除渠道。如果您不想使用某个渠道，您可以禁用或重命名该渠道并将其保存以供日后使用。

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. 在[!UICONTROL “报表包管理器”]页面上，选择一个报表包。

   如果您选择多个报表包，则需要选择一个可将设置从模板复制到选定报表包的模板。

   请参阅[将模板报表包设置应用于多个报表包](../../components/c-marketing-channels/t-template.md#task_0DE0A320EDA94FC5A6E5912868B6E2DC)。

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Manager]**.

   If your report suite does not have channels defined, the [Auto Setup](../../components/c-marketing-channels/c-channel-autosetup.md#topic_E9ABE9E9E71B4E40A4E7EA9AD2C0372B) page displays.

1. On the [!UICONTROL Marketing Channel Manager] page, click **[!UICONTROL Add Channel]**.

   当定义了 25 个渠道时，此选项便不再可用。

1. Click **[!UICONTROL Save.]**
1. To configure rules for the channel, click **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08).

## Marketing Channel Manager - interface definitions {#reference_01779A2928054BF48339897D4033AFB9}

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
   <td colname="col2"> <p> 指定用户访问您网站的途径。您可以选择<span class="uicontrol">在线</span>或<span class="uicontrol">离线</span>。对于通过搜索引擎或电子邮件促销活动来访的访客，使用“在线”渠道。“离线”渠道适用于通过报纸优惠券或杂志广告发现您网站的访客。离线渠道通常包括通过报表数据源导入的数据。 </p> <p>请参阅<a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/" scope="external" format="http">数据源</a>。 </p> <p>See <a href="../../components/c-marketing-channels/t-offline-data.md#task_FC96E6A48F0D4D37A79BD234E90DAA26" type="task" format="dita" scope="local"> Add Offline Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>颜色 </p> </td> 
   <td colname="col2"> <p>与此营销渠道关联的颜色。此颜色代表<span class="wintitle">营销渠道</span>报表中的渠道。 </p> </td> 
  </tr> 
 </tbody> 
</table>

