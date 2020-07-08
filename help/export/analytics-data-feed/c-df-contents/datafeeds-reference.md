---
description: 描述数据馈送中的列的表数据。
keywords: Data Feed;columns
subtopic: data feeds
title: 数据列引用
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: e6bff325cdceb2048554b47944567d50d3c8133f
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 98%

---


# 数据列引用

使用此页面可了解每一列包含哪些数据。大多数实施并不会用到每一列，因此在确定要将哪些列纳入数据馈送导出时，可以参考此页面。

>[!IMPORTANT]
>
>对于任何给定的列（例如，定义为 255 个字符的列），由于在字符串中添加了字符转义值，数据馈送可能会发送额外的字符。如果您的实施发送的值经常超出字符限制，请记住这些潜在的额外字符。

## 列、说明和数据类型

>[!NOTE]
>
>大多数列中包含一个以 `post_` 为前缀的相似列。post 列包含应用服务器端逻辑、处理规则和 VISTA 规则后得出的值。大多数情况下，Adobe 建议使用 post_ 列。有关更多信息，请参阅[数据馈送常见问题解答](../df-faq.md)。

| 列名称 | 列说明 | 数据类型 |
| --- | --- | --- |
| `accept_language` | 列出所有已接受的语言，如图像请求中的 Accept-Language HTTP 标头所示。 | char(20) |
| `aemassetid` | 一个具有多个值的变量，与一组 Adobe Experience Manager 资产的资产 ID (GUID) 相对应。可增加展示事件的计数。 | text |
| `aemassetsource` | 标识资产事件的来源。在 Adobe Experience Manager 中使用。 | varchar(255) |
| `aemclickedassetid` | Adobe Experience Manager 资产的资产 ID可增加点击事件的计数。 | varchar(255) |
| `browser` | 浏览器的数字 ID。引用 browser.tsv 查询表。 | int，无符号 |
| `browser_height` | 浏览器窗口的高度（单位：像素）。 | smallint，无符号 |
| `browser_width` | 浏览器窗口的宽度（单位：像素）。 | smallint，无符号 |
| `c_color` | 调色板的位深度。计算“颜色深度”维度时使用。使用 JavaScript 函数 screen.colorDepth()。 | char(20) |
| `campaign` | 在“跟踪代码”维度中使用的变量。 | varchar(255) |
| `carrier` | Adobe Advertising Cloud 集成变量。指定移动设备运营商。引用运营商查询表。 | varchar(100) |
| `channel` | 在“网站区域”维度中使用的变量。 | varchar(100) |
| `click_action` | 已不再使用。在旧版 Clickmap 工具中点击的链接地址。 | varchar(100) |
| `click_action_type` | 已不再使用。旧版 Clickmap 工具的链接类型。<br>0：HREF URL<br>1：自定义 ID<br>2：JavaScript onClick 事件<br>3：表单元素 | tinyint，无符号 |
| `click_context` | 已不再使用。发生链接点击的页面名称。包含在旧版 ClickMap 工具中。 | varchar(255) |
| `click_context_type` | 已不再使用。指示 click_context 是使用了页面名称，还是默认使用了页面 URL。<br>0：页面 URL<br>1：页面名称 | tinyint，无符号 |
| `click_sourceid` | 已不再使用。页面上点击链接的位置所对应的数字 ID。包含在旧版 ClickMap 工具中。 | int，无符号 |
| `click_tag` | 已不再使用。已点击的 HTML 元素的类型。 | char(10) |
| `clickmaplink` | Activity Map 链接 | varchar(255) |
| `clickmaplinkbyregion` | Activity Map 链接（按地区） | varchar(255) |
| `clickmappage` | Activity Map 页面 | varchar(255) |
| `clickmapregion` | Activity Map 地区 | varchar(255) |
| `code_ver` | 用于编译和发送图像请求的 AppMeasurement 库版本。 | char(16) |
| `color` | 基于 c_color 列值的颜色深度 ID。引用 color_depth.tsv 查询表。 | smallint，无符号 |
| `connection_type` | 表示连接类型的数字 ID。在“连接类型”维度中使用的变量。引用 connection_type.tsv 查询表。 | tinyint，无符号 |
| `cookies` | 在“Cookie 支持”维度中使用的变量。<br>Y：启用<br>N：禁用<br>U：未知 | char(1) |
| `country` | 表示点击来源的国家/地区的数字 ID。Adobe 与 Digital Envoy 合作，以将 IP 地址匹配到国家/地区。使用 country.tsv 查询表。 | smallint，无符号 |
| `ct_connect_type` | 与 connection_type 列相关。最常见的值为“局域网/Wifi”、“移动设备运营商”和“调制调节器”。 | char(20) |
| `curr_factor` | 确定货币的小数位，用于货币兑换。例如，美元使用两个小数位，因此该列的值为 2。 | tinyint |
| `curr_rate` | 交易时的汇率。Adobe 与 XE 合作，以确定当天的汇率。 | decimal(24,12) |
| `currency` | 交易过程中使用的货币代码。 | char(8) |
| `cust_hit_time_gmt` | 仅限启用了时间戳的报表包。随点击发送的时间戳（基于 Unix 时间）。 | int |
| `cust_visid` | 如果设置了自定义访客 ID，此 ID 会填充到该列中。 | varchar(255) |
| `daily_visitor` | 确定点击是否为新的每日访客的标记。 | tinyint，无符号 |
| `date_time` | 以可读格式表示的点击时间（基于报表包所在时区）。 | datetime |
| `domain` | 在“域”维度中使用的变量。基于用户的 Internet 服务提供商 (ISP)。 | varchar(100) |
| `duplicate_events` | 列出计为重复的每个事件。 | varchar(255) |
| `duplicate_purchase` | 表示此次点击对应的购买事件因重复而应忽略的标记。 | tinyint，无符号 |
| `duplicated_from` | 仅在包含点击复制 VISTA 规则的报表包中使用。指示点击是从哪个报表包中复制的。 | varchar(40) |
| `ef_id` | 在 Adobe Advertising Cloud 集成中使用的 ef_id。 | varchar(255) |
| `evar1 - evar250` | 自定义变量 1-250。每个公司使用 eVar 的方式有所不同。要了解有关贵组织如何填充各个 eVar 的更多信息，您最好参阅专为贵组织设计的解决方案文档。 | varchar(255) |
| `event_list` | 以逗号分隔的数字 ID 列表，其中各 ID 表示点击时所触发的各个事件。包含默认事件及自定义事件 1-1000。使用 event.tsv 查询表。 | text |
| `exclude_hit` | 表示点击已从报表中排除的标记。对于已排除的点击，visit_num 列的值不会增加。<br>1：未使用。包含在已弃用的功能中。<br>2：未使用。包含在已弃用的功能中。<br>3：已不再使用。用户代理排除<br>4：基于 IP 地址排除<br>5：缺少重要的点击信息，例如 page_url、pagename、page_event 或 event_list<br>6：JavaScript 未正确处理点击<br>7：特定于帐户的排除，例如在 VISTA 规则中<br>8：未使用。替代特定于帐户的排除。<br>9：未使用。包含在已弃用的功能中。<br>10：无效的货币代码<br>11：仅时间戳报表包上缺少时间戳的点击，或非时间戳报表包上包含时间戳的点击<br>12：未使用。包含在已弃用的功能中。<br>13：未使用。包含在已弃用的功能中。<br>14：与 Analytics 点击不匹配的 Target 点击<br>15：当前未使用。<br>16：与 Analytics 点击不匹配的 Advertising Cloud 点击 | tinyint，无符号 |
| `first_hit_page_url` | 访客访问的第一个 URL。 | varchar(255) |
| `first_hit_pagename` | 在“原始登录页面”维度中使用的变量。访客访问的原始登录页面名称。 | varchar(100) |
| `first_hit_ref_domain` | 在“原始反向链接域名”维度中使用的变量。基于 first_hit_referrer。访客访问的第一个反向链接的域名。 | varchar(100) |
| `first_hit_ref_type` | 数字 ID，表示访客访问的第一个反向链接的类型。使用 referrer_type.tsv 查询表。 | tinyint，无符号 |
| `first_hit_referrer` | 访客访问的第一个反向链接 URL。 | varchar(255) |
| `first_hit_time_gmt` | 访客第一次点击的时间戳（基于 Unix 时间）。 | int |
| `geo_city` | 点击来源的城市的名称（基于 IP）。Adobe 与 Digital Envoy 合作，以将 IP 地址匹配到城市。 | char(32) |
| `geo_country` | 点击来源的国家/地区的缩写（基于 IP）。Adobe 与 Digital Envoy 合作，以将 IP 地址匹配到国家/地区。 | char(4) |
| `geo_dma` | 点击来源的人口统计区的数字 ID（基于 IP）。Adobe 与 Digital Envoy 合作，以将 IP 地址匹配到人口统计区。 | int，无符号 |
| `geo_region` | 点击来源的州/市/自治区或区域的名称（基于 IP）。Adobe 与 Digital Envoy 合作，以将 IP 地址匹配到州/市/自治区/区域。 | char(32) |
| `geo_zip` | 点击来源的地区的邮政编码（基于 IP）。Adobe 与 Digital Envoy 合作，以将 IP 地址匹配到邮政编码。 | varchar(16) |
| `hier1 - hier5` | 由层级变量使用。包含一个分隔的值列表。在“报表包设置”下方选择分隔符。 | varchar(255) |
| `hit_source` | 表示点击的来源。<br>1：不带时间戳的标准图像请求<br>2：带有时间戳的标准图像请求<br>3：带有时间戳的实时数据源上传<br>4：未使用<br>5：通用数据源上传<br>6：完全处理数据源上传<br>7：TransactionID 数据源上传<br>8：不再使用；Adobe Advertising Cloud 数据源的以前版本<br>9：不再使用；Adobe Social 概要量度 | tinyint，无符号 |
| `hit_time_gmt` | Adobe 数据收集服务器收到点击的时间戳，基于 Unix 时间。 | int |
| `hitid_high` | 与 hitid_low 结合使用，用来唯一标识点击。 | bigint，无符号 |
| `hitid_low` | 与 hitid_high 结合使用，用来唯一标识点击。 | bigint，无符号 |
| `homepage` | 已不再使用。指示当前的 URL 是否是浏览器的主页。 | char(1) |
| `hourly_visitor` | 确定点击是否为新的每小时访客的标记。 | tinyint，无符号 |
| `ip` | IP 地址，基于图像请求的 HTTP 标头。 | char(20) |
| `ip2` | 未使用。报表包的后端引用变量，包含基于 IP 地址的 VISTA 规则。 | char(20) |
| `j_jscript` | 浏览器支持的 JavaScript 版本。 | char(5) |
| `java_enabled` | 表示 Java 是否已启用的标记。<br>Y：启用<br>N：禁用<br>U：未知 | char(1) |
| `javascript` | JavaScript 版本的查询 ID（基于 j_jscript）。使用查询表。 | tinyint，无符号 |
| `language` | 语言的数字 ID。使用 languages.tsv 查询表。 | smallint，无符号 |
| `last_hit_time_gmt` | 上次点击的时间戳（基于 Unix 时间）。用于计算“上次访问间隔天数”维度。 | int |
| `last_purchase_num` | 在“客户忠诚度”维度中使用的变量。表示访客以往的购买次数。<br>0：之前没有购买（不是客户）<br>1：1 次先前购买（新客户）<br>2：2 次先前购买（退货客户）<br>3：3 次或更多先前购买（忠诚客户） | int，无符号 |
| `last_purchase_time_gmt` | 在“上次购买间隔天数”维度中使用。上次购买的时间戳（基于 Unix 时间）。对于首次购买及之前未购买过的访客，该值为 0。 | int |
| `latlon1` | 位置（精确到 10 千米） | varchar(255) |
| `latlon23` | 位置（精确到 100 米） | varchar(255) |
| `latlon45` | 位置（精确到 1 米） | varchar(255) |
| `mc_audiences` | 列出访客所属的 Audience Manager 区段 ID。 | text |
| `mcvisid` | Experience Cloud 访客 ID. 一个 128 位的数字（由两个 64 位的数字拼接而成），共占据了 19 位数。 | varchar(255) |
| `mobile_id` | 如果用户使用了移动设备，则为移动设备的数字 ID。 | int |
| `mobileaction` | 移动设备操作。在 Mobile Services 中调用 trackAction 时会自动收集。应用程序支持自动的操作路径。 | varchar(100) |
| `mobileappid` | 移动设备应用程序 ID。采用以下格式存储应用程序名称和版本：[应用程序名称] [包版本] | varchar(255) |
| `mobileappperformanceappid` | 用于 Apteligent Data Connector。Apteligent 中使用的应用程序 ID。 | varchar(255) |
| `mobileappperformancecrashid` | 用于 Apteligent Data Connector。Apteligent 中使用的崩溃 ID。 | varchar(255) |
| `mobileappstoreobjectid` | 用于 Appfigures Data Connector。应用商店对象 ID | varchar(255) |
| `mobilebeaconmajor` | Mobile Services 信标主要 | varchar(100) |
| `mobilebeaconminor` | Mobile Services 信标次要 | varchar(100) |
| `mobilebeaconproximity` | Mobile Services 信标邻近性 | varchar(255) |
| `mobilebeaconuuid` | Mobile Services 信标 UUID | varchar(100) |
| `mobilecampaigncontent` | 显示链接的内容名称或内容 ID。由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobilecampaignmedium` | 营销媒介，如横幅或电子邮件。由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobilecampaignname` | 促销活动的名称，也存储在促销活动变量中。由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobilecampaignsource` | 原始反向链接，如新闻稿或社交媒体网络。由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobilecampaignterm` | 要通过此客户获取跟踪的付费关键词或其他搜索词。由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobiledayofweek` | 应用程序启动的时间（星期几）。 | varchar(255) |
| `mobiledayssincefirstuse` | 距应用程序首次运行的间隔天数。 | varchar(255) |
| `mobiledayssincelastupgrade` | 从上下文数据变量 a.DaysSinceLastUpgrade 收集。自上一个会话以来经过的天数。 | varchar(255) |
| `mobiledayssincelastuse` | 距应用程序上次运行的间隔天数。 | varchar(255) |
| `mobiledeeplinkid` | 从上下文数据变量 a.<span>deeplink</span>.id 收集。在客户获取报表中用作移动客户获取链接的标识符。 | varchar(255) |
| `mobiledevice` | 移动设备名称。在 iOS 上，该变量存储为用逗号分隔的 2 位数的字符串。第一个数字表示设备是第几代的，而另一个数字则表示设备所属的系列。 | varchar(255) |
| `mobilehourofday` | 确定应用程序启动的具体时间。采用 24 小时数字格式。 | varchar(255) |
| `mobileinstalldate` | 移动设备安装日期。表示用户首次打开移动设备应用程序的日期。 | varchar(255) |
| `mobilelaunchessincelastupgrade` | 从上下文数据变量 a.LaunchesSinceUpgrade 收集。报告自上次升级以来的启动次数。 | varchar(255) |
| `mobilelaunchnumber` | 应用程序每启动一次，该变量值便会递增。 | varchar(255) |
| `mobileltv` | 已不再使用。由 trackLifetimeValue 方法填充。 | varchar(255) |
| `mobilemessagebuttonname` | 从上下文数据变量 a.<span>message</span>.button.id 收集。用于应用程序内消息传递，以标识关闭消息的按钮。 | varchar(100) |
| `mobilemessageid` | 应用程序内消息 ID | varchar(255) |
| `mobilemessageonline` | 应用程序内消息在线 | varchar(255) |
| `mobilemessagepushoptin` | 从上下文数据变量 a.push.optin 收集。当用户选择加入推送消息时，设置为“true”；否则，将该值设为“false”。 | varchar(255) |
| `mobilemessagepushpayloadid` | 从上下文数据变量 a.push.payloadid 收集。在推送消息中用作有效负载标识符。 | varchar(255) |
| `mobileosenvironment` | 从上下文数据变量 a.OSEnvironment 收集。指明操作系统环境，如 Android 或 iOS。 | varchar(255) |
| `mobileosversion` | Mobile Services 操作系统版本 | varchar(255) |
| `mobileplaceaccuracy` | 从上下文数据变量 a.loc.acc 收集。指示收集时 GPS 的精度（以米为单位）。 | varchar(255) |
| `mobileplacecategory` | 从上下文数据变量 a.loc.category 收集。描述特定位置的类别。 | varchar(255) |
| `mobileplaceid` | 从上下文数据变量 a.<span>loc</span>.id 收集。给定目标点的标识符。 | varchar(255) |
| `mobilerelaunchcampaigncontent` | Mobile Services 启动内容 | varchar(255) |
| `mobilerelaunchcampaignmedium` | Mobile Services 启动媒介 | varchar(255) |
| `mobilerelaunchcampaignsource` | Mobile Services 启动来源 | varchar(255) |
| `mobilerelaunchcampaignterm` | Mobile Services 启动搜索词 | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | 从上下文数据变量 a.launch.campaign.trackingcode 收集。在客户获取中用作启动促销活动的跟踪代码。 | varchar(255) |
| `mobileresolution` | 移动设备分辨率。宽 x 高（以像素为单位）。 | varchar(255) |
| `monthly_visitor` | 表示访客属于当月的独特访客的标记。 | tinyint，无符号 |
| `mvvar1` - `mvvar3` | 列出变量值。包含分隔的自定义值列表（取决于实施）。 | text |
| `namespace` | 未使用。包含在多年前弃用的功能中。 | varchar(50) |
| `new_visit` | 确定当前点击是否为新访问的标记。在访问处于不活动状态 30 分钟后，由 Adobe 服务器设置。 | tinyint，无符号 |
| `os` | 表示访客操作系统的数字 ID。基于 user_agent 列。使用操作系统查询表。 | int，无符号 |
| `p_plugins` | 已不再使用。可用于浏览器的插件列表。使用 JavaScript 函数 navigator.plugins()。 | text |
| `page_event` | 在图像请求中发送的点击类型（标准点击、下载链接、自定义链接、退出链接）。请参阅[页面事件查找](datafeeds-page-event.md)。 | tinyint，无符号 |
| `page_event_var1` | 仅用于链接跟踪图像请求。单击的下载链接、退出链接或自定义链接的 URL。 | text |
| `page_event_var2` | 仅用于链接跟踪图像请求。链接的自定义名称（如果已指定）。 | varchar(100) |
| `page_event_var3` | 已不再使用。包含调查和媒体模块数据。用于填充 Adobe Analytics 早期版本中的旧版视频报表。 | text |
| `page_type` | 用于填充“未找到页面”维度，仅适用于 404 页面。此变量应为空，或包含“ErrorPage”。 | char(20) |
| `page_url` | 点击的 URL。不用于链接跟踪图像请求。 | varchar(255) |
| `pagename` | 用于填充“页面”维度。如果 pagename 变量为空，Analytics 会改为使用 page_url。 | varchar(100) |
| `paid_search` | 设置点击是否与付费搜索检测匹配的标记。 | tinyint，无符号 |
| `partner_plugins` | 未使用。包含在多年前弃用的功能中。 | varchar(255) |
| `persistent_cookie` | 由“持久性 Cookie 支持”维度使用。指示访客是否要支持每次点击后未被丢弃的 Cookie。 | char(1) |
| `plugins` | 已不再使用。列出与浏览器中可用插件相对应的数字 ID。使用 plugins.tsv 查询表。 | varchar(180) |
| `pointofinterest` | Mobile Services 目标点名称 | varchar(255) |
| `pointofinterestdistance` | Mobile Services 与目标点中心的距离 | varchar(255) |
| `post_ columns` | 包含报表中最终使用的值。每个 post 列会在服务器端逻辑、处理规则和 VISTA 规则后填充。大多数情况下，Adobe 建议使用 post_ 列。 | 请参阅相应的非 post 列 |
| `prev_page` | 未使用。上一页所具有的 Adobe 专有标识符。 | int，无符号 |
| `product_list` | 通过产品变量传递的“产品”列表。各产品用逗号分隔，而各个产品属性则用分号分隔。 | text |
| `product_merchandising` | 未使用。请改为使用 product_list。 | text |
| `prop1` - `prop75` | 自定义流量变量 1 - 75。 | varchar(100) |
| `purchaseid` | 购买的唯一标识符，需使用 s_purchaseID 变量来设置。由 duplicate_purchase 列使用。 | char(20) |
| `quarterly_visitor` | 确定点击是否为新的每季访客的标记。 | tinyint，无符号 |
| `ref_domain` | 基于反向链接列。点击的反向链接域名。 | varchar(100) |
| `ref_type` | 表示点击的反向链接类型的数字 ID。<br>1：网站内<br>2：其他网站<br>3：搜索引擎<br>4：硬盘<br>5：未发送<br>6：已输入/添加书签（无反向链接）<br>7：电子邮件<br>8：无 JavaScript <br>9：社交网络 | tinyint，无符号 |
| `referrer` | 上一页的页面 URL。请注意，在 `referrer` 使用数据类型 varchar(255) 时，`post_referrer` 使用数据类型 varchar(244)。 | varchar(255) |
| `resolution` | 表示显示器分辨率的数字 ID。填充“显示器分辨率”维度。使用 resolution.tsv 查询表。 | smallint，无符号 |
| `s_kwcid` | Adobe Advertising Cloud 集成中使用的关键词 ID。 | varchar(255) |
| `s_resolution` | 原始屏幕分辨率值需使用 JavaScript 函数 screen.width x screen.height 来收集。 | char(20) |
| `sampled_hit` | 已不再使用。之前用于在 Ad Hoc Analysis 中取样。 | char(1) |
| `search_engine` | 表示将访客引荐至您网站的搜索引擎的数字 ID。使用 search_engines.tsv 查询表。 | smallint，无符号 |
| `search_page_num` | 由“所有搜索页面排名”维度使用。指示用户在点进您网站之前您的网站位于搜索结果的第几页。 | smallint，无符号 |
| `secondary_hit` | 用于跟踪次级点击的标记。通常来自于多包标记和用于复制点击的 VISTA 规则。 | tinyint，无符号 |
| `service` | 未使用。请改为使用 page_event。 | char(2) |
| `socialaccountandappids` | 已不再使用。社交帐户和应用程序 ID | varchar(255) |
| `socialassettrackingcode` | 已不再使用。社交网站促销活动变量 | varchar(255) |
| `socialauthor` | 已不再使用。社交网站作者变量 | varchar(255) |
| `socialcontentprovider` | 已不再使用。社交平台/属性 | varchar(255) |
| `socialinteractiontype` | 已不再使用。社交网站互动类型 | varchar(255) |
| `sociallanguage` | 已不再使用。社交网站语言 | varchar(255) |
| `sociallatlong` | 已不再使用。社交网站纬度/经度 | varchar(255) |
| `socialowneddefinitioninsighttype` | 已不再使用。社交网站拥有的定义分析类型 | varchar(255) |
| `socialowneddefinitioninsightvalue` | 已不再使用。社交网站拥有的定义分析值 | varchar(255) |
| `socialowneddefinitionmetric` | 已不再使用。社交网站拥有的定义量度 | varchar(255) |
| `socialowneddefinitionpropertyvspost` | 已不再使用。社交网站拥有的定义属性与帖子 | varchar(255) |
| `socialownedpostids` | 已不再使用。社交网站拥有的帖子 ID | varchar(255) |
| `socialownedpropertyid` | 已不再使用。社交网站拥有的资产 ID | varchar(255) |
| `socialownedpropertyname` | 已不再使用。社交网站拥有的资产名称 | varchar(255) |
| `socialownedpropertypropertyvsapp` | 已不再使用。设计网站拥有的资产与应用程序 | varchar(255) |
| `state` | 状态变量。 | varchar(50) |
| `stats_server` | 已不再使用。处理点击的 Adobe 内部服务器。 | char(30) |
| `t_time_info` | 访客所在地区的当地时间。格式如下：M/D/YYYY HH:MM:SS 月份（0-11，0 = 1 月）时区偏移（以分钟为单位） | varchar(100) |
| `tnt` | 在 Adobe Target 集成中使用。 | text |
| `tnt_action` | 在 Adobe Target 集成中使用。 | text |
| `tnt_post_vista` | 已不再使用。请改为使用 post_tnt。 | text |
| `transactionid` | 稍后可以通过数据源上载各种数据点的唯一标识符。 | text |
| `truncated_hit` | 表示图像请求已被截断的标记。表示收到了不完整的点击。<br>Y：点击被截断；收到部分点击<br>N：点击未被截断；收到完整点击 | char(1) |
| `ua_color` | 已不再使用。之前用作颜色深度的备选项。 | char(20) |
| `ua_os` | 已不再使用。之前用作操作系统的备选项。 | char(80) |
| `ua_pixels` | 已不再使用。之前用作浏览器高度和宽度的备选项。 | char(20) |
| `user_agent` | 在图像请求的 HTTP 标头中发送的用户代理字符串。 | text |
| `user_hash` | 已不再使用。有关报表包 ID 的散列。请改为使用 username。 | int，无符号 |
| `user_server` | 在“服务器”维度中使用的变量。 | varchar(100) |
| `userid` | 已不再使用。表示报表包 ID 的数字 ID。请改为使用 username。 | int，无符号 |
| `username` | 点击的报表包 ID。 | char(40) |
| `va_closer_detail` | 在“最近联系详细信息”维度中使用的变量。 | varchar(255) |
| `va_closer_id` | 用于标识“最近联系渠道”维度的数字 ID。可在营销渠道管理器中找到此 ID 所对应的查询表。 | tinyint，无符号 |
| `va_finder_detail` | 在“首次联系详细信息”维度中使用的变量。 | varchar(255) |
| `va_finder_id` | 用于标识“首次联系渠道”维度的数字 ID。可在营销渠道管理器中找到此 ID 所对应的查询表。 | tinyint，无符号 |
| `va_instance_event` | 用于标识营销渠道实例的标记。由“营销渠道最近联系实例”量度使用。 | tinyint，无符号 |
| `va_new_engagement` | 用于标识营销渠道新参与的标记。由“新参与”量度使用。 | tinyint，无符号 |
| `video` | 视频内容 | varchar(255) |
| `videoad` | 视频广告名称 | varchar(255) |
| `videoadinpod` | 面板位置中的视频广告 | varchar(255) |
| `videoadlength` | 视频广告时长 | varchar(255) |
| `videoadload` | 视频广告加载 | varchar(255) |
| `videoadname` | 视频广告名称 | varchar(255) |
| `videoadplayername` | 视频广告播放器名称 | varchar(255) |
| `videoadpod` | 视频广告组合 | varchar(255) |
| `videoadvertiser` | 视频广告商 | varchar(255) |
| `videoaudioalbum` | 视频音频相册 | varchar(255) |
| `videoaudioartist` | 视频音频艺术家 | varchar(255) |
| `videoaudioauthor` | 视频音频作者 | varchar(255) |
| `videoaudiolabel` | 视频音频标签 | varchar(255) |
| `videoaudiopublisher` | 视频音频发布者 | varchar(255) |
| `videoaudiostation` | 视频音频电台/电视台 | varchar(255) |
| `videocampaign` | 视频促销活动 | varchar(255) |
| `videochannel` | 视频渠道 | varchar(255) |
| `videochapter` | 视频章节名称 | varchar(255) |
| `videocontenttype` | 视频内容类型。自动设为“视频”，以查看所有视频。 | varchar(255) |
| `videodaypart` | 视频播放时段 | varchar(255) |
| `videoepisode` | 视频剧集 | varchar(255) |
| `videofeedtype` | 视频馈送类型 | varchar(255) |
| `videogenre` | 视频流派 | text |
| `videolength` | 视频长度 | varchar(255) |
| `videomvpd` | 视频 MVPD | varchar(255) |
| `videoname` | 视频名称 | varchar(255) |
| `videonetwork` | 视频网络 | varchar(255) |
| `videopath` | 视频路径 | varchar(100) |
| `videoplayername` | 视频播放器名称 | varchar(255) |
| `videoqoebitrateaverageevar` | 视频品质：平均比特率 | varchar(255) |
| `videoqoebitratechangecountevar` | 视频品质：比特率变化计数 | varchar(255) |
| `videoqoebuffercountevar` | 视频品质：缓冲计数 | varchar(255) |
| `videoqoebuffertimeevar` | 视频品质：缓冲时间 | varchar(255) |
| `videoqoedroppedframecountevar` | 视频品质：丢帧计数 | varchar(255) |
| `videoqoeerrorcountevar` | 视频品质：错误计数 | varchar(255) |
| `videoqoeextneralerrors` | 视频品质：外部错误 | text |
| `videoqoeplayersdkerrors` | 视频品质：SDK 错误 | text |
| `videoqoetimetostartevar` | 视频品质：启动时间 | varchar(255) |
| `videoseason` | 视频季 | varchar(255) |
| `videosegment` | 视频区段 | varchar(255) |
| `videoshow` | 视频表演 | varchar(255) |
| `videoshowtype` | 视频表演类型 | varchar(255) |
| `videostreamtype` | 视频流类型 | varchar(255) |
| `visid_high` | 与visid_low结合使用，以唯一标识访客。 | bigint，无符号 |
| `visid_low` | 与visid_high结合使用，以唯一标识访客。 | bigint，无符号 |
| `visid_new` | 用于表示点击是否包含新生成的访客 ID 的标记。 | char(1) |
| `visid_timestamp` | 如果访客 ID 是新生成的，则会提供用于表示访客 ID 生成时间的时间戳（基于 Unix 时间）。 | int |
| `visid_type` | 非外部用途； Adobe内部用于处理优化。 表示用于标识访客的方法的数字ID。<br>0: 自定义访客ID或未知／不适用<br>1: IP和用户代理回 <br>退2: HTTP移动订户标 <br>头3: 旧版cookie值(s_vi) <br>4: 回退cookie值(s_fid) <br>5: 身份服务 | tinyint，无符号 |
| `visit_keywords` | 在“搜索关键字”维度中使用的变量。此列使用非标准字符限制来适应 Adobe 使用的后端逻辑。 | varchar(244) |
| `visit_num` | 在“访问次数”维度中使用的变量。起始值为 1，随后每个访客每启动一次新访问，该值便会递增。 | int，无符号 |
| `visit_page_num` | 在“点击深度”维度中使用的变量。用户每生成一次点击，该变量的值便会增加 1。每次访问后重置。 | int，无符号 |
| `visit_ref_domain` | 基于 visit_referrer 列。访问中第一个反向链接的域名。 | varchar(100) |
| `visit_ref_type` | 数字 ID，表示访问中第一个反向链接的类型。使用 referrer_type.tsv 查询表。 | tinyint，无符号 |
| `visit_referrer` | 访问中的第一个反向链接。 | varchar(255) |
| `visit_search_engine` | 表示访问中所使用的第一个搜索引擎的数字 ID。使用 search_engines.tsv 查询表。 | smallint，无符号 |
| `visit_start_page_url` | 访问中的第一个 URL。 | varchar(255) |
| `visit_start_pagename` | 访问的第一个页面名称。 | varchar(100) |
| `visit_start_time_gmt` | 访问中首次点击的时间戳（基于 Unix 时间）。 | int |
| `weekly_visitor` | 确定点击是否为新的每周访客的标记。 | tinyint，无符号 |
| `yearly_visitor` | 确定点击是否为新的每年访客的标记。 | tinyint，无符号 |
| `zip` | 用于填充“邮政编码”维度。 | varchar(50) |

## 空白列

以下列列表未使用且不包含数据：

* mobileacquisitionclicks
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformanceaffectedusers
* mobileappperformanceappid<span>.</span>app-perf-app-name
* mobileappperformanceappid<span>.</span>app-perf-platform
* mobileappperformancecrashes
* mobileappperformancecrashid<span>.</span>app-perf-crash-name
* mobileappperformanceloads
* mobileappstoreavgrating
* mobileappstoredownloads
* mobileappstoreinapprevenue
* mobileappstoreinapproyalties
* mobileappstoreobjectid<span>.</span>app-store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>application-version
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>country-name
* mobileappstoreobjectid<span>.</span>device-manufacturer
* mobileappstoreobjectid<span>.</span>device-name
* mobileappstoreobjectid<span>.</span>in-app-name
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>rank-category-type
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>review-comment
* mobileappstoreobjectid<span>.</span>review-title
* mobileappstoreoneoffrevenue
* mobileappstoreoneoffroyalties
* mobileappstorepurchases
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstorerating
* mobileappstoreratingdivisor
* mobileavgprevsessionlength
* mobilecrashes
* mobilerashrate
* mobiledailyengatedusers
* mobiledeeplinkid<span>.</span>name
* mobileinstalls
* mobilelaunches
* mobileltvtotal
* mobilemessageclicks
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>name
* mobilemessageid<span>.</span>type
* mobilemessageidespons
* mobilemessagepushpayloadid<span><span>.</span></span>name
* mobilemessageviews
* mobilemonthlyagentedusers
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobileprevsessionlength
* mobilerelaunchcampaigntrackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment（已弃用）
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink（已弃用）
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty（已弃用）
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist（已弃用）
* socialtotalsentiment
* sourceid
* videoauthorized
* videoaverageminuteaudience
* videochaptercomplete
* videochapterstart
* videochaptertime
* videopause
* videopausecount
* videopausetime
* videoplay
* videoprogress10
* videoprogress25
* videoprogress50
* videoprogress75
* videoprogress96
* videoqoebitrateaverage
* videoqoebitratechange
* videoqoebuffer
* videoqoedropbeforestart
* videoqoedroppedframes
* videoqoeerror
* videoresume
* videototaltime
* videouniquetimeplayed
