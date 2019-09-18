---
description: 通过使用流量源报表，可以深入分析访客与您的网站之间的交互情况。
seo-description: 通过使用流量源报表，可以深入分析访客与您的网站之间的交互情况。
seo-title: 流量源报表
solution: Analytics
title: 流量源报表
topic: Ad Hoc Analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: tm+mt
source-git-commit: 646d6e01d0f0201c78117ee9bf9ff64fda9a026a

---


# 流量源报表

通过使用流量源报表，可以深入分析访客与您的网站之间的交互情况。

## 流量源报表 {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

通过使用流量源报表，可以深入分析访客与您的网站之间的交互情况。

利用流量源报表，您可以：

* 分析访客行为的重要方面。
* 监视和了解流量模式。
* 确定受欢迎的网站内容。
* 采用任何可度量的标准对访客分类。

**一般持久性**

在“[!UICONTROL 流量源]”中，所有报表值都持续存在且会获得信用，直到它们被覆盖或访问结束（以先发生者为准）。以前，只有“关键词”和“反向链接域名”会持续存在。例如，如果访客用 Google 搜索“DVD”并因此将访客带入您的网站并消费 100 美元，则报表将为关键字“DVD”以及 Google 搜索引擎分别分配 100 美元信用。This functionality is unalterable, regardless of [!DNL Admin Console] settings.

## 搜索关键词 {#concept_071FDCBD0A3B4242BA00744786D1C59C}

显示“全部”、“付费”和“免费”搜索的关键词分类。

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL 搜索关键词 - 全部]**：显示搜索关键词分类细目，其中包含被用来找到您的网站的每个搜索关键词。可点击列表上方的列标题，按页面查看或搜索关键词对列表排序。点击搜索关键词旁边的放大镜，可查看网站的搜索结果。

**[!UICONTROL 搜索关键词 - 付费]**：显示搜索关键词分类细目，其中包含用于查找您的网站的每个付费搜索关键词。可点击列表上方的列标题，按页面查看或搜索关键词对列表排序。点击搜索关键词旁边的放大镜，可查看网站的搜索结果。

**[!UICONTROL 搜索关键词 - 免费]**：显示搜索关键词分类细目，其中包含用于查找您的网站的每个免费搜索关键词。可点击列表上方的列标题，按页面查看或搜索关键词对列表排序。点击搜索关键词旁边的放大镜，可查看网站的搜索结果。

## 搜索引擎 {#concept_351CDE4F5FC44371B6B657064E125134}

显示访客进行“全部”、“付费”和“免费”搜索时所使用的搜索引擎。

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL 搜索引擎 - 全部]**：显示用户使用哪些搜索引擎来查找网页。其中图表显示用于查找网站的搜索引擎的百分比分类。

**[!UICONTROL 搜索引擎 - 付费]**：显示用户使用哪些付费关键词搜索引擎来查找网页。其中图表显示用于查找网站的搜索引擎的百分比分类。

**[!UICONTROL 搜索引擎 - 免费]**：显示用户使用哪些免费关键词搜索引擎来查找网页。其中图表显示用于查找网站的搜索引擎的百分比分类。

## 反向链接域名 {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

显示引用对网站成功量度影响最大的客户的域。反向链接分为两大类别：域和 URL。“域”指的是域名，它显示为不带查询字符串或子目录的基本域。URL 包括基本域名以及任何查询字符串或子目录。

## 原始反向链接域名 {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

显示促成客户访问网站的原始反向链接。客户可以多次访问网站，且每次访问时都使用不同的反向链接。此报表显示客户首次访问贵网站所用的反向链接。这有助于您了解客户是否继续使用同一反向链接，并查看将客户引至贵网站的方式。您可以查看原始反向链接生成的访客人数，也可找出每个原始反向链接对网站收入的贡献。每次访客进入网站时反向链接报表均会填充，即便该访客在一个会话（访问过期之前）中多次进入网站。

## 反向链接 {#concept_40CF9C2D10B94E82819BC65A232F05C3}

显示访客在进入网站前所在的域或 URL、访客找到网站的方法、以及经由这些反向链接位置对您网站的访问次数。

<!-- 

c_reports_referrers.xml

 -->

例如，如果访客点击网站 A 上的链接后转至您的网站，则网站 A 为反向链接（如果它未定义为属于您的域）。在 Marketing Reports &amp; Analytics 实施过程中，实施顾问会帮助您定义属于您网站的域和 URL。（此更改可在实施后完成。）

域和 URL 如果不属于这些定义的对象则会被视为反向链接。例如，网页 A 和网页 B 都被添加到内部 URL 过滤器中，但是网页 C 没有。在这种情况下，网页 C 被视为反向链接。

See [Internal URL Filters](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=internal_URL_filter_admin) in the [!DNL Admin Console] help for more information.

>[!NOTE]
>
>Marketing reports and analytics records a referring domain as an email when visitors click an emailed message link containing the protocol [!DNL imap://] or [!DNL mail://] and arrive at your site. 例如，由于协议为 [!DNL https://mail.yahoo.com]://，因此来自 [!DNL https://] 的任何消息均不会计为电子邮件反向链接。Outlook 电子邮件会报告于“键入/书签式”行上，而任何采用 HTTP 协议（域为已知搜索引擎）的反向链接均报告于“搜索引擎”行上。

## 反向链接类型 {#concept_689E42D8F96C450DA41C7167C7388198}

通过跟踪和记录访客每次访问的反向链接网站，可以确定访客每次访问时如何找到您的网站。

<!-- 

c_reports_ref_types.xml

 -->

以下列表列出了有关不同类型反向链接的定义：

* *其他网站反向链接，在访客点击其他网站（并非定义为您的网站的一部分）页面上的链接，然后转到您的网站时进行记录。*
* *搜索引擎反向链接，在访客使用搜索引擎来访问您的网站时进行记录。*
* *分类/添加书签*&#x200B;的反向链接已进行记录

   * 如果访客通过非浏览器链接进入您的网站（例如，在电子邮件中）。
   * 如果访客在浏览器中直接键入您的网站 URL。
   * 如果访客单击其个人硬盘驱动器上的 HTML 链接。
   * 如果访客通过选择浏览器书签访问您的网站。

**定义**

运行此报表时可能会显示以下行项目：

**网站内部**：这些项目是由内部 URL 过滤器标记的 URL。这些项目将不会计为反向链接实例，但在其他量度的报表中仍然可见。

**无Java脚本**:没有JavaScript，因此类型无法识别（未知）。 这表示浏览器（不会报告可支持 Javascript）上的客户端未提供任何反向链接信息。这些项目将不会计为“反向链接实例”，但在报告其他量度时将会显示这些项目。

**USENET（新闻组）**：这表示反向链接的 URL 以 `news://` :// 开头。因此，反向链接是被发布在 USENET 新闻组中，而不是网页上。

>[!NOTE]
>
>Referrer Type logic matches other traffic sources reports (such as [!UICONTROL Referrers] and [!UICONTROL Referring Domains]). 这会减少[!UICONTROL 反向链接类型]报表中出现“网站内部”和“无 JavaScript”行项目的次数，或者使其不再出现。

