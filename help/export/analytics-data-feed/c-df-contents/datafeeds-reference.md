---
description: 描述数据馈送中的列的表数据。
keywords: Data Feed;columns
subtopic: data feeds
title: 数据列引用
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 数据列引用

使用此页面可了解每一列包含哪些数据。大多数实施并不会用到每一列，因此在确定要将哪些列纳入数据馈送导出时，可以参考此页面。

>[!IMPORTANT]对于任何给定的列（例如，定义为 255 个字符的列），由于在字符串中添加了字符转义值，数据馈送可能会发送额外的字符。如果您的实施发送的值经常超出字符限制，请记住这些潜在的额外字符。

## 列、说明和数据类型

>[!NOTE]大多数列中包含一个以 `post_` 为前缀的相似列。post 列包含应用服务器端逻辑、处理规则和 VISTA 规则后得出的值。大多数情况下，Adobe 建议使用 post_ 列。有关更多信息，请参阅[数据馈送常见问题解答](../df-faq.md)。

| 列名称 | 列说明 | 数据类型 |
| --- | --- | --- |
| `accept_language` | 列表所有已接受的语言，如图像请求中的“接受语言”HTTP头中所示。 | char(20) |
| `aemassetid` | 与一组Adobe Experience Manager资产的资产ID(GUID)相对应的多值变量。 增加印象事件。 | text |
| `aemassetsource` | 标识资产事件的来源。 用于Adobe Experience Manager。 | varchar(255) |
| `aemclickedassetid` | Adobe Experience Manager资产的资产ID。 增加单击事件。 | varchar(255) |
| `browser` | 浏览器的数字ID。 引用browser.tsv查找表。 | int，无符号 |
| `browser_height` | 浏览器窗口的高度（单位：像素）。 | smallint，无符号 |
| `browser_width` | 浏览器窗口的宽度（单位：像素）。 | smallint，无符号 |
| `c_color` | 调色板的位深度。 用作计算“颜色深度”尺寸的一部分。 使用JavaScript函数screen.colorDepth()。 | char(20) |
| `campaign` | “跟踪代码”维中使用的变量。 | varchar(255) |
| `carrier` | Adobe Advertising Cloud集成变量。 指定移动运营商。 引用运营商查找表。 | varchar(100) |
| `channel` | 在“站点区域”维中使用的变量。 | varchar(100) |
| `click_action` | 已不再使用。在旧版Clickmap工具中单击的链接地址。 | varchar(100) |
| `click_action_type` | 已不再使用。旧版Clickmap工具的链接类型。<br>0：HREF URL<br>1：自定义 ID<br>2：JavaScript onClick 事件<br>3：表单元素 | tinyint，无符号 |
| `click_context` | 已不再使用。发生链接单击的页面名称。 旧版Clickmap工具的一部分。 | varchar(255) |
| `click_context_type` | 已不再使用。指示click_context是具有页面名称还是默认为页面URL。<br>0：页面 URL<br>1：页面名称 | tinyint，无符号 |
| `click_sourceid` | 已不再使用。单击链接页面上的位置的数字ID。 旧版Clickmap工具的一部分。 | int，无符号 |
| `click_tag` | 已不再使用。单击的HTML元素的类型。 | char(10) |
| `clickmaplink` | Activity Map 链接 | varchar(255) |
| `clickmaplinkbyregion` | Activity Map 链接（按地区） | varchar(255) |
| `clickmappage` | Activity Map 页面 | varchar(255) |
| `clickmapregion` | Activity Map 地区 | varchar(255) |
| `code_ver` | 用于编译和发送图像请求的AppMeasurement库版本。 | char(16) |
| `color` | 基于c_color列的值的颜色深度ID。 引用color_depth.tsv查找表。 | smallint，无符号 |
| `connection_type` | 表示连接类型的数字ID。 用于连接类型维的变量。 引用connection_type.tsv查找表。 | tinyint，无符号 |
| `cookies` | 用于Cookie支持维度的变量。<br>Y：启用<br>N：禁用<br>U：未知 | char(1) |
| `country` | 表示点击来源国家／地区的数字ID。 Adobe与Digital Envoy合作，将IP地址与国家／地区相匹配。 使用country.tsv查找。 | smallint，无符号 |
| `ct_connect_type` | 与connection_type列相关。 大多数常用值是LAN/Wifi、移动运营商和调制解调器。 | char(20) |
| `curr_factor` | 确定货币小数位，并用于货币换算。 例如，USD使用两位小数，因此此列值将为2。 | tinyint |
| `curr_rate` | 交易发生时的汇率。 Adobe与XE合作决定当天的汇率。 | decimal(24,12) |
| `currency` | 在事务处理期间使用的货币代码。 | char(8) |
| `cust_hit_time_gmt` | 仅支持时间戳的报表包。 随点击发送的时间戳，基于Unix时间。 | int |
| `cust_visid` | 如果设置了自定义访客ID，则会在此列中填充该ID。 | varchar(255) |
| `daily_visitor` | 确定点击是否为新的每日访客的标记。 | tinyint，无符号 |
| `date_time` | 根据报表包的时区，以可读格式命中的时间。 | datetime |
| `domain` | 域维中使用的变量。 基于用户的Internet服务提供商(ISP)。 | varchar(100) |
| `duplicate_events` | 列表每个被计为重复的事件。 | varchar(255) |
| `duplicate_purchase` | 指示此点击的购买事件应被忽略的标志，因为它是重复。 | tinyint，无符号 |
| `duplicated_from` | 仅用于包含点击复制VISTA规则的报表包。 指示从中复制点击的报表包。 | varchar(40) |
| `ef_id` | Adobe Advertising Cloud集成中使用的ef_id。 | varchar(255) |
| `evar1 - evar250` | 自定义变量1-250。 每个组织使用eVar的方式各不相同。 有关您的组织如何填充各个eVar的更多信息，最好选择特定于您的组织的解决方案设计文档。 | varchar(255) |
| `event_list` | 以逗号分隔的数字ID列表，表示点击时触发的事件。 包括默认事件和自定义事件1-1000。 使用事件.tsv查找。 | text |
| `exclude_hit` | 指示点击的标志从报告中排除。 对于已排除的点击，visit_num 列的值不会增加。<br>1：未使用。包含在已弃用的功能中。<br>2：未使用。包含在已弃用的功能中。<br>3：已不再使用。用户代理排除<br>4：基于 IP 地址排除<br>5：缺少重要的点击信息，例如 page_url、pagename、page_event 或 event_list<br>6：JavaScript 未正确处理点击<br>7：特定于帐户的排除，例如在 VISTA 规则中<br>8：未使用。替代特定于帐户的排除。<br>9：未使用。包含在已弃用的功能中。<br>10：无效的货币代码<br>11：仅时间戳报表包上缺少时间戳的点击，或非时间戳报表包上包含时间戳的点击<br>12：未使用。包含在已弃用的功能中。<br>13：未使用。包含在已弃用的功能中。<br>14：与 Analytics 点击不匹配的 Target 点击<br>15：当前未使用。<br>16：与 Analytics 点击不匹配的 Advertising Cloud 点击 | tinyint，无符号 |
| `first_hit_page_url` | 访客的第一个URL。 | varchar(255) |
| `first_hit_pagename` | 在“条目页面原始”维中使用的变量。 访客的原始条目页面名称。 | varchar(100) |
| `first_hit_ref_domain` | 在“原始引用域”维中使用的变量。 基于first_hit_推荐人。 访客的第一个参照域。 | varchar(100) |
| `first_hit_ref_type` | 数字ID表示推荐人的第一个推荐人的访客类型。 使用推荐人_type.tsv查找。 | tinyint，无符号 |
| `first_hit_referrer` | 访客的第一个引用URL。 | varchar(255) |
| `first_hit_time_gmt` | 在Unix时间中访客的首次点击的时间戳。 | int |
| `geo_city` | 基于IP的点击来源城市名称。 Adobe与Digital Envoy合作，将IP地址与城市匹配。 | char(32) |
| `geo_country` | 根据IP，受到打击的国家的缩写。 Adobe与Digital Envoy合作，将IP地址与国家／地区相匹配。 | char(4) |
| `geo_dma` | 基于IP的点击来自的人口统计区域的数字ID。 Adobe与Digital Envoy合作，将IP地址与人口统计区域相匹配。 | int，无符号 |
| `geo_region` | 根据IP命中来自的州或地区名称。 Adobe与Digital Envoy合作，将IP地址与州／地区匹配。 | char(32) |
| `geo_zip` | 点击来源的地区的邮政编码（基于 IP）。Adobe与Digital Envoy合作，将IP地址与邮政编码相匹配。 | varchar(16) |
| `hier1 - hier5` | 由层次变量使用。 包含值的分隔列表。 在报表包设置下选择分隔符。 | varchar(255) |
| `hit_source` | 表示点击的来源。<br>1：不带时间戳的标准图像请求<br>2：带有时间戳的标准图像请求<br>3：带有时间戳的实时数据源上传<br>4：未使用<br>5：通用数据源上传<br>6：完全处理数据源上传<br>7：TransactionID 数据源上传<br>8：不再使用；Adobe Advertising Cloud 数据源的以前版本<br>9：不再使用；Adobe Social 概要量度 | tinyint，无符号 |
| `hit_time_gmt` | Adobe 数据收集服务器收到点击的时间戳，基于 Unix 时间。 | int |
| `hitid_high` | 与hitid_low结合使用以唯一标识点击。 | bigint，无符号 |
| `hitid_low` | 与hitid_high结合使用以唯一标识点击。 | bigint，无符号 |
| `homepage` | 已不再使用。指示当前URL是否为浏览器的主页。 | char(1) |
| `hourly_visitor` | 确定点击是否为新的每小时访客的标记。 | tinyint，无符号 |
| `ip` | IP地址，基于图像请求的HTTP头。 | char(20) |
| `ip2` | 未使用。基于IP地址的报表包的后端引用变量，其中包含VISTA规则。 | char(20) |
| `j_jscript` | 浏览器支持的JavaScript版本。 | char(5) |
| `java_enabled` | 表示 Java 是否已启用的标记。<br>Y：启用<br>N：禁用<br>U：未知 | char(1) |
| `javascript` | 基于j_jscript的JavaScript版本的查找ID。 使用查找表。 | tinyint，无符号 |
| `language` | 语言的数字ID。 使用languages.tsv查找表。 | smallint，无符号 |
| `last_hit_time_gmt` | 上一次点击的时间戳（在Unix时间中）。 用于计算“自上次访问以来的天数”维。 | int |
| `last_purchase_num` | 在“客户忠诚度”维度中使用的变量。 表示访客以往的购买次数。<br>0：之前没有购买（不是客户）<br>1：1 次先前购买（新客户）<br>2：2 次先前购买（退货客户）<br>3：3 次或更多先前购买（忠诚客户） | int，无符号 |
| `last_purchase_time_gmt` | 在“上次购买后的天数”维中使用。 上次购买的时间戳（在Unix时间内）。 对于首次购买和之前未购买的访客，此值为0。 | int |
| `latlon1` | 位置（精确到 10 千米） | varchar(255) |
| `latlon23` | 位置（精确到 100 米） | varchar(255) |
| `latlon45` | 位置（精确到 1 米） | varchar(255) |
| `mc_audiences` | 列表受众管理器区段ID，该访客属于该区段。 | text |
| `mcvisid` | Experience Cloud 访客 ID. 128位数，由两个连接的64位数字组成，填充为19位。 | varchar(255) |
| `mobile_id` | 如果用户使用了移动设备，则为移动设备的数字 ID。 | int |
| `mobileaction` | 移动操作。 在 Mobile Services 中调用 trackAction 时会自动收集。应用程序支持自动的操作路径。 | varchar(100) |
| `mobileappid` | 移动应用程序ID。 Stores the application name and version in the following format:[AppName] [BundleVersion] | varchar(255) |
| `mobileappperformanceappid` | 用于 Apteligent Data Connector。Apteligent 中使用的应用程序 ID。 | varchar(255) |
| `mobileappperformancecrashid` | 用于 Apteligent Data Connector。Apteligent 中使用的崩溃 ID。 | varchar(255) |
| `mobileappstoreobjectid` | 用于 Appfigures Data Connector。应用商店对象 ID | varchar(255) |
| `mobilebeaconmajor` | Mobile Services 信标主要 | varchar(100) |
| `mobilebeaconminor` | Mobile Services 信标次要 | varchar(100) |
| `mobilebeaconproximity` | Mobile Services 信标邻近性 | varchar(255) |
| `mobilebeaconuuid` | Mobile Services 信标 UUID | varchar(100) |
| `mobilecampaigncontent` | 显示链接的内容的名称或ID。 由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobilecampaignmedium` | 营销媒介，如横幅或电子邮件。 由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobilecampaignname` | 促销活动的名称，也存储在促销活动变量中。由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobilecampaignsource` | 原始推荐人，如新闻稿或社交媒体网络。 由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobilecampaignterm` | 要跟踪此客户获取的付费关键字或其他条款。 由移动设备应用程序客户获取填充。 | varchar(255) |
| `mobiledayofweek` | 启动应用程序的工作日数。 | varchar(255) |
| `mobiledayssincefirstuse` | 应用程序首次运行后的天数。 | varchar(255) |
| `mobiledayssincelastupgrade` | 从上下文数据变量 a.DaysSinceLastUpgrade 收集。自上一个会话以来经过的天数。 | varchar(255) |
| `mobiledayssincelastuse` | 上次运行应用程序后的天数。 | varchar(255) |
| `mobiledeeplinkid` | 从上下文数据变量 a.<span>deeplink</span>.id 收集。在客户获取报表中用作移动客户获取链接的标识符。 | varchar(255) |
| `mobiledevice` | 移动设备名称。 在iOS上，它以逗号分隔的2位字符串形式存储。 第一个数字表示设备生成，第二个数字表示设备系列。 | varchar(255) |
| `mobilehourofday` | 定义应用程序启动当天的小时。 遵循24小时的数字格式。 | varchar(255) |
| `mobileinstalldate` | 移动安装日期。 提供用户首次打开移动应用程序的日期。 | varchar(255) |
| `mobilelaunchessincelastupgrade` | 从上下文数据变量 a.LaunchesSinceUpgrade 收集。报告自上次升级以来的启动次数。 | varchar(255) |
| `mobilelaunchnumber` | 每次启动移动应用程序时递增1。 | varchar(255) |
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
| `mobileresolution` | 移动设备的分辨率。 宽度x高度（以像素为单位）。 | varchar(255) |
| `monthly_visitor` | 表示访客的标志是当月特有的。 | tinyint，无符号 |
| `mvvar1` - `mvvar3` | 列表变量值。 包含自定义值的分隔列表，具体取决于实现。 | text |
| `namespace` | 未使用。多年前，该功能被废弃。 | varchar(50) |
| `new_visit` | 确定当前点击是否为新访问的标记。 由Adobe服务器在30分钟访问不活动后进行设置。 | tinyint，无符号 |
| `os` | 表示访客操作系统的数字ID。 基于user_agent列。 使用操作系统查找。 | int，无符号 |
| `p_plugins` | 已不再使用。列表可用于浏览器的插件。 已使用JavaScript函数navigator.plugins()。 | text |
| `page_event` | 在图像请求中发送的点击类型（标准点击、下载链接、自定义链接、退出链接）。请参阅[页面事件查找](datafeeds-page-event.md)。 | tinyint，无符号 |
| `page_event_var1` | 仅用于链接跟踪图像请求。 单击了下载链接、退出链接或自定义链接的URL。 | text |
| `page_event_var2` | 仅用于链接跟踪图像请求。 链接的自定义名称（如果指定）。 | varchar(100) |
| `page_event_var3` | 已不再使用。包含调查和媒体模块数据。 已在旧版Adobe Analytics中填充旧版视频报告。 | text |
| `page_type` | 用于填充“找不到页面”维，仅用于404页。 此变量应为空或包含“ErrorPage”。 | char(20) |
| `page_url` | 点击的URL。 未用于链接跟踪图像请求。 | varchar(255) |
| `pagename` | 用于填充页面维。 如果pagename变量为空，则Analytics会改用page_url。 | varchar(100) |
| `paid_search` | 点击与付费搜索检测匹配时设置的标志。 | tinyint，无符号 |
| `partner_plugins` | 未使用。多年前，该功能被废弃。 | varchar(255) |
| `persistent_cookie` | 由“永久Cookie支持”维度使用。 指示访客是否支持每次点击后未丢弃的Cookie。 | char(1) |
| `plugins` | 已不再使用。列表与浏览器中可用的插件相对应的数字ID。 使用plugins.tsv查找。 | varchar(180) |
| `pointofinterest` | Mobile Services 目标点名称 | varchar(255) |
| `pointofinterestdistance` | Mobile Services 与目标点中心的距离 | varchar(255) |
| `post_ columns` | 包含报表中最终使用的值。 每个后列都在服务器端逻辑、处理规则和VISTA规则之后填充。 大多数情况下，Adobe 建议使用 post_ 列。 | 查看相应的非帖子列 |
| `prev_page` | 未使用。上一页的Adobe专有标识符。 | int，无符号 |
| `product_list` | 通过产品变量传递的产品列表。 产品以逗号分隔，而各个产品属性以分号分隔。 | text |
| `product_merchandising` | 未使用。请改用product_列表。 | text |
| `prop1` - `prop75` | 自定义流量变量1-75。 | varchar(100) |
| `purchaseid` | 使用s_purchaseID变量设置的购买的唯一标识符。 由重复购买列使用。 | char(20) |
| `quarterly_visitor` | 确定点击是否为新的季度访客的标记。 | tinyint，无符号 |
| `ref_domain` | 基于推荐人列。 点击的引用域。 | varchar(100) |
| `ref_type` | 表示点击的参照类型的数字ID。<br>1：网站内<br>2：其他网站<br>3：搜索引擎<br>4：硬盘<br>5：未发送<br>6：已输入/添加书签（无反向链接）<br>7：电子邮件<br>8：无 JavaScript <br>9：社交网络 | tinyint，无符号 |
| `referrer` | 上一页的页面URL。 请注意，当 `referrer` 使用varchar(255)的数据类型 `post_referrer` 时，使用varchar(244)的数据类型。 | varchar(255) |
| `resolution` | 表示显示器分辨率的数字ID。 填充“监视器分辨率”维。 使用resolution.tsv查找表。 | smallint，无符号 |
| `s_kwcid` | Adobe Advertising Cloud 集成中使用的关键词 ID。 | varchar(255) |
| `s_resolution` | 原始屏幕分辨率值。 使用JavaScript函数screen.width x screen.height收集。 | char(20) |
| `sampled_hit` | 已不再使用。以前用于在临时分析中取样。 | char(1) |
| `search_engine` | 表示将访客引用到站点的搜索引擎的数字ID。 使用search_engines.tsv查找。 | smallint，无符号 |
| `search_page_num` | 由“全部搜索页面排名”维使用。 指示在用户点击到您的站点之前，您的站点显示的搜索结果页面。 | smallint，无符号 |
| `secondary_hit` | 跟踪次要点击的标记。 通常来自复制点击的多套件标记和VISTA规则。 | tinyint，无符号 |
| `service` | 未使用。请改用page_事件。 | char(2) |
| `socialaccountandappids` | 已不再使用。社交帐户和应用程序ID | varchar(255) |
| `socialassettrackingcode` | 已不再使用。社交活动变量 | varchar(255) |
| `socialauthor` | 已不再使用。社交作者变量 | varchar(255) |
| `socialcontentprovider` | 已不再使用。社交平台/属性 | varchar(255) |
| `socialinteractiontype` | 已不再使用。社交交互类型 | varchar(255) |
| `sociallanguage` | 已不再使用。社交语言 | varchar(255) |
| `sociallatlong` | 已不再使用。社交纬度／经度 | varchar(255) |
| `socialowneddefinitioninsighttype` | 已不再使用。社交拥有的定义分析类型 | varchar(255) |
| `socialowneddefinitioninsightvalue` | 已不再使用。社交所有的定义分析值 | varchar(255) |
| `socialowneddefinitionmetric` | 已不再使用。社交所有的定义指标 | varchar(255) |
| `socialowneddefinitionpropertyvspost` | 已不再使用。社交拥有的定义属性与帖子 | varchar(255) |
| `socialownedpostids` | 已不再使用。社交拥有的帖子ID | varchar(255) |
| `socialownedpropertyid` | 已不再使用。社交所有的属性ID | varchar(255) |
| `socialownedpropertyname` | 已不再使用。社交所有财产名称 | varchar(255) |
| `socialownedpropertypropertyvsapp` | 已不再使用。社交所有财产与应用程序 | varchar(255) |
| `state` | 状态变量。 | varchar(50) |
| `stats_server` | 无用。 处理点击的 Adobe 内部服务器。 | char(30) |
| `t_time_info` | 访客的当地时间。 格式如下：M/D/YYYY HH:MM:SS月(0-11, 0=January)时区偏移（以分钟为单位） | varchar(100) |
| `tnt` | 用于Adobe目标集成。 | text |
| `tnt_action` | 用于Adobe目标集成。 | text |
| `tnt_post_vista` | 已不再使用。请改用post_tnt。 | text |
| `transactionid` | 一个唯一标识符，在该标识符中，各种数据点稍后可以通过数据源上传。 | text |
| `truncated_hit` | 指示图像请求被截断的标志。 表示收到了不完整的点击。<br>Y：点击被截断；收到部分点击<br>N：点击未被截断；收到完整点击 | char(1) |
| `ua_color` | 已不再使用。以前用作颜色深度的备用。 | char(20) |
| `ua_os` | 已不再使用。以前用作操作系统的备用。 | char(80) |
| `ua_pixels` | 已不再使用。以前用作浏览器高度和宽度的备用。 | char(20) |
| `user_agent` | 在图像请求的HTTP头中发送的用户代理字符串。 | text |
| `user_hash` | 无用。 报表包ID的哈希。 请改用用户名。 | int，无符号 |
| `user_server` | 服务器维中使用的变量。 | varchar(100) |
| `userid` | 无用。 报表包ID的数字ID。 请改用用户名。 | int，无符号 |
| `username` | 点击的报表包ID。 | char(40) |
| `va_closer_detail` | “上次触控详细信息”维中使用的变量。 | varchar(255) |
| `va_closer_id` | 标识“上次接触”渠道维的数字ID。 此ID的查找可在营销渠道管理器中找到。 | tinyint，无符号 |
| `va_finder_detail` | “首次触控详细信息”维中使用的变量。 | varchar(255) |
| `va_finder_id` | 标识“首次接触渠道”维的数字ID。 此ID的查找可在营销渠道管理器中找到。 | tinyint，无符号 |
| `va_instance_event` | 标记以标识营销渠道实例。 由“营销渠道上次联系实例”量度使用。 | tinyint，无符号 |
| `va_new_engagement` | 标记以标识营销渠道的新参与。 由“新参与”量度使用。 | tinyint，无符号 |
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
| `videoqoebitrateaverageevar` | 视频质量平均比特率 | varchar(255) |
| `videoqoebitratechangecountevar` | 视频质量更改计数 | varchar(255) |
| `videoqoebuffercountevar` | 视频质量缓冲区计数 | varchar(255) |
| `videoqoebuffertimeevar` | 视频品质：缓冲时间 | varchar(255) |
| `videoqoedroppedframecountevar` | 视频质量下降的帧数 | varchar(255) |
| `videoqoeerrorcountevar` | 视频质量错误计数 | varchar(255) |
| `videoqoeextneralerrors` | 视频品质：外部错误 | text |
| `videoqoeplayersdkerrors` | 视频品质：SDK 错误 | text |
| `videoqoetimetostartevar` | 视频质量到开始 | varchar(255) |
| `videoseason` | 视频季 | varchar(255) |
| `videosegment` | 视频区段 | varchar(255) |
| `videoshow` | 视频表演 | varchar(255) |
| `videoshowtype` | 视频表演类型 | varchar(255) |
| `videostreamtype` | 视频流类型 | varchar(255) |
| `visid_high` | 与visid_low结合使用以唯一标识访问。 | bigint，无符号 |
| `visid_low` | 与visid_high结合使用以唯一标识访问。 | bigint，无符号 |
| `visid_new` | 用于标识点击是否包含新生成的访客ID的标记。 | char(1) |
| `visid_timestamp` | 如果访客ID是新生成的，则提供生成访客ID的时间戳（在Unix时间）。 | int |
| `visid_type` | 数字 ID，表示用于标识访客的方法。<br>0：自定义访客 ID <br>1：IP 和用户代理回退 <br>2：HTTP Mobile 订阅者标头 <br>3：旧版 Cookie 值 (s_vi) <br>4：回退 Cookie 值 (s_fid) <br>5：Identity 服务 | tinyint，无符号 |
| `visit_keywords` | 在“搜索关键字”维度中使用的变量。此列使用非标准字符限制来适应 Adobe 使用的后端逻辑。 | varchar(244) |
| `visit_num` | “访问次数”维中使用的变量。 开始数为1，每访客每次新访问开始数都会增加。 | int，无符号 |
| `visit_page_num` | 在“命中深度”维中使用的变量。 用户生成的每次点击都增加1。 重置每次访问。 | int，无符号 |
| `visit_ref_domain` | 基于visit_推荐人列。 访问的第一个引用域。 | varchar(100) |
| `visit_ref_type` | 表示访问第一个推荐人的推荐人类型的数字ID。 使用推荐人类型。tsv查找表。 | tinyint，无符号 |
| `visit_referrer` | 访问的第一推荐人. | varchar(255) |
| `visit_search_engine` | 访问的第一个搜索引擎的数字ID。 使用search_engines.tsv查找表。 | smallint，无符号 |
| `visit_start_page_url` | 访问的第一个URL。 | varchar(255) |
| `visit_start_pagename` | 访问的第一个页面名称。 | varchar(100) |
| `visit_start_time_gmt` | 访问首次点击的时间戳（在Unix时间中）。 | int |
| `weekly_visitor` | 确定点击是否为新的每周访客的标记。 | tinyint，无符号 |
| `yearly_visitor` | 用于确定点击是否为新的年度访客的标记。 | tinyint，无符号 |
| `zip` | 用于填充邮政编码维。 | varchar(50) |

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
