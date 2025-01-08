---
title: Analytics 维度兼容性
description: Analytics 维度和报表的参考。
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: fd26afc166ada6b1bc1890cbcf1406345c275765
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 60%

---

# Analytics 维度兼容性

此页面列出了各自Analytics功能中支持的[维度](overview.md)。

>[!NOTE]
>
>此列表中删除了自定义变量名称、分类和访客属性。这些维度项目特定于单个报表包。

## Analysis Workspace支持的Dimension

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|---|---|
| Analytics for Target | `targetraw` |
| 受众 ID | `mcaudiences` |
| [浏览器](browser.md) | `browser` |
| [浏览器类型](browser-type.md) | `browsertype` |
| [类别](category.md) | `category` |
| [城市](cities.md) | `geocity` |
| [颜色深度](color-depth.md) | `colordepth` |
| [连接类型](connection-type.md) | `connectiontype` |
| [Cookie支持](cookie-support.md) | `cookie` |
| [国家/地区](countries.md) | `geocountry` |
| [客户忠诚度](customer-loyalty.md) | `customerloyalty` |
| [自定义转化变量](evar.md) | `evar1`、`evar2` 等。 |
| [Custom Insight Var](prop.md) | `prop1`、`prop2` 等。 |
| [自定义链接](custom-link.md) | `customlink` |
| [首次购买间隔天数](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [上次购买间隔天数](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [域](domain.md) | `filtereddomain` |
| [下载链接](download-link.md) | `downloadlink` |
| [登录页面](entry-dimensions.md) | `entrypage` |
| [原始登入页面](entry-dimensions.md) | `entrypageoriginal` |
| [退出链接](exit-link.md) | `exitlink` |
| [首次联系渠道](first-touch-channel.md) | `firsttouchchannel` |
| [首次联系渠道详细信息](first-touch-detail.md) | `firsttouchchanneldetail` |
| [已启用 Java](java-enabled.md) | `javaenabled` |
| [语言](language.md) | `language` |
| [最近联系渠道](last-touch-channel.md) | `lasttouchchannel` |
| [最近联系渠道详细信息](last-touch-detail.md) | `lasttouchchanneldetail` |
| 列表变量 | `listvariables` |
| [营销渠道](marketing-channel.md) | `marketingchannel` |
| [移动音频支持](mobile-dimensions.md) | `mobileaudiosupport` |
| [移动设备运营商](mobile-dimensions.md) | `mobilecarrier` |
| [移动设备颜色深度](mobile-dimensions.md) | `mobilecolordepth` |
| [移动设备Cookie支持](mobile-dimensions.md) | `mobilecookiesupport` |
| [移动设备](mobile-dimensions.md) | `mobiledevicename` |
| [移动设备类型](mobile-dimensions.md) | `mobiledevicetype` |
| [移动设备电子邮件最大长度](mobile-dimensions.md) | `mobileemaillength` |
| [移动设备图像支持](mobile-dimensions.md) | `mobileimagesupport` |
| [移动设备制造商](mobile-dimensions.md) | `mobilemanufacturer` |
| [移动设备操作系统（已弃用）](mobile-dimensions.md) | `mobileos` |
| [移动设备屏幕高度](mobile-dimensions.md) | `mobilescreenheight` |
| [移动设备屏幕大小](mobile-dimensions.md) | `mobilescreensize` |
| [移动设备屏幕宽度](mobile-dimensions.md) | `mobilescreenwidth` |
| [移动设备最大浏览器URL长度](mobile-dimensions.md) | `mobileurllength` |
| [移动设备视频支持](mobile-dimensions.md) | `mobilevideosupport` |
| [监视器分辨率](monitor-resolution.md) | `monitorresolution` |
| [操作系统](operating-systems.md) | `operatingsystem` |
| [原始反向链接域](original-referring-domain.md) | `referringdomainoriginal` |
| [页面](page.md) | `page` |
| [页面未找到](pages-not-found.md) | `pagesnotfound` |
| [产品](product.md) | `product` |
| [反向链接](referrer.md) | `referrer` |
| [反向链接类型](referrer-type.md) | `referrertype` |
| [反向链接域](referring-domain.md) | `referringdomain` |
| [地区](regions.md) | `georegion` |
| [回访频度](return-frequency.md) | `returnfrequency` |
| SC-TnT | `tntbase` |
| [搜索引擎](search-engine.md) | `searchengine` |
| [搜索关键词](search-keyword.md) | `searchenginekeyword` |
| [搜索引擎 — 免费](search-engine.md) | `searchenginenatural` |
| [搜索引擎 — 付费](search-engine.md) | `searchenginepaid` |
| [搜索关键词 — 免费](search-keyword.md) | `searchenginenaturalkeyword` |
| [搜索关键词 — 付费](search-keyword.md) | `searchenginepaidkeyword` |
| [所有搜索页面排名](all-search-page-rank.md) | `searchenginepagerank` |
| [服务器](server.md) | `server` |
| [单页面访问量](single-page-visits.md) | `singlepagevisits` |
| [网站区域](site-section.md) | `sitesections` |
| 每次访问逗留时间[ — 粒度](time-spent-per-visit.md) | `sitetime` |
| [跟踪代码](tracking-code.md) | `campaign` |
| [美国 DMA](us-dma.md) | `geodma` |
| [美国各州](us-states.md) | `state` |
| [发生事件之前逗留的时间](time-prior-to-event.md) | `timeprior` |
| [每次访问逗留时间 — 分段统计](time-spent-per-visit.md) | `timespent` |
| [访问深度](visit-depth.md) | `pathlength` |
| [访问量](visit-number.md) | `visitnumber` |
| [邮政编码](zip-code.md) | `zip` |
| [上午/下午](am-pm.md) | `timepartampm` |
| [浏览器高度 — 分段统计](browser-height.md) | `browserheightbucketed` |
| [浏览器宽度 — 分段统计](browser-width.md) | `browserwidthbucketed` |
| [日](day.md) | `daterangeday` |
| [日期](day-of-month.md) | `timepartdayofmonth` |
| [每周时间](day-of-week.md) | `dayofweek` |
| [每周时间](day-of-week.md) | `timepartdayofweek` |
| [每年的某一天](day-of-year.md) | `timepartdayofyear` |
| [上次访问间隔天数](days-since-last-visit.md) | `dayssincelastvisit` |
| [进入自定义分析](entry-dimensions.md) | `entryprops` |
| [条目列表变量](entry-dimensions.md) | `entrylistvariables` |
| [条目服务器](entry-dimensions.md) | `entryserver` |
| [登录网站区域](entry-dimensions.md) | `entrysitesections` |
| [退出自定义分析](exit-dimensions.md) | `exitprops` |
| [退出列表变量](exit-dimensions.md) | `exitlistvariables` |
| [退出页面](exit-dimensions.md) | `exitpage` |
| [退出服务器](exit-dimensions.md) | `exitserver` |
| [退出网站区域](exit-dimensions.md) | `exitsitesections` |
| [点击深度](hit-depth.md) | `hitdepth` |
| [点击类型](hit-type.md) | `hittype` |
| [小时](hour.md) | `daterangehour` |
| [小时](hour-of-day.md) | `timeparthourofday` |
| [营销渠道详细信息](marketing-detail.md) | `marketingchanneldetail` |
| [分钟](minute.md) | `daterangeminute` |
| [移动设备最大书签长度](mobile-dimensions.md) | `mobilebookmarklength` |
| [移动设备号码](mobile-dimensions.md) | `mobiledevicenumber` |
| [移动设备DRM](mobile-dimensions.md) | `mobiledrm` |
| [Mobile Information Services](mobile-dimensions.md) | `mobileinformationservices` |
| [移动Java虚拟机](mobile-dimensions.md) | `mobilejavavm` |
| [移动设备邮件修饰](mobile-dimensions.md) | `mobilemaildecoration` |
| [移动网络协议](mobile-dimensions.md) | `mobilenetprotocols` |
| [移动一键通](mobile-dimensions.md) | `mobilepushtotalk` |
| [月](month.md) | `daterangemonth` |
| [月份](month-of-year.md) | `timepartmonthofyear` |
| [操作系统类型](operating-system-types.md) | `operatingsystemgroup` |
| [付费搜索](paid-search.md) | `paidsearch` |
| [永久性Cookie支持](persistent-cookie-support.md) | `persistentcookie` |
| [季度](quarter.md) | `daterangequarter` |
| [季度](quarter-of-year.md) | `timepartquarterofyear` |
| 调查 | `surveybase` |
| [页面逗留时间 — 分段统计](time-spent-on-page.md) | `averagepagetime` |
| [页面逗留时间 — 粒度](time-spent-on-page.md) | `pagetimeseconds` |
| [跟踪选择退出的原因](tracking-opt-out-reason.md) | `optoutreason` |
| [工作日/周末](weekday-weekend.md) | `timepartweekdayweekend` |
| [周](week.md) | `daterangeweek` |
| [年](year.md) | `daterangeyear` |

## 仅在 Analysis Workspace 中受支持的内容感知维度

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| 媒体会话 ID | `videosessionid` |
| Nielsen 访问方法 | `nielsenaccmethod` |
| Nielsen 应用程序 ID | `nielsenappid` |
| Nielsen 渠道资产 | `nielsenchannelasset` |
| Nielsen 内容类型 | `nielsencontenttype` |

## Analysis Workspace支持的内容感知维度

### 视频（流媒体收藏集）

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| [内容](sm-core.md) | `video` |
| [内容区段](sm-core.md) | `videosegment` |
| [内容类型](sm-core.md) | `videocontenttype` |
| [广告播放器名称](sm-ads.md) | `videoadplayername` |
| [面板中的广告位置](sm-ads.md) | `videoadinpod` |
| [丢帧](sm-quality.md) | `videoqoedroppedframecountevar` |
| [错误](sm-quality.md) | `videoqoeerrorcountevar` |
| [平均比特率](sm-quality.md) | `videoqoebitrateaverageevar` |
| [比特率更改](sm-quality.md) | `videoqoebitratechangecountevar` |
| [缓冲总持续时间](sm-quality.md) | `videoqoebuffertimeevar` |
| [缓冲事件](sm-quality.md) | `videoqoebuffercountevar` |
| [开始时间](sm-quality.md) | `videoqoetimetostartevar` |
| [广告面板](sm-ads.md) | `videoadpod` |
| [媒体路径](sm-core.md) | `videopath` |
| [广告](sm-ads.md) | `videoad` |
| [内容播放器名称](sm-core.md) | `videoplayername` |
| [内容渠道](sm-core.md) | `videochannel` |
| [章节](sm-chapters.md) | `videochapter` |
| [内容名称（变量）](sm-core.md) | `videoname` |
| [内容时长（变量）](sm-core.md) | `videolength` |
| [广告名称（变量）](sm-ads.md) | `videoadname` |
| [广告长度（变量）](sm-ads.md) | `videoadlength` |
| [在“客户获取链接”页面上显示](sm-video-metadata.md) | `videoshow` |
| [季](sm-video-metadata.md) | `videoseason` |
| [剧集](sm-video-metadata.md) | `videoepisode` |
| [网络](sm-video-metadata.md) | `videonetwork` |
| [显示类型](sm-video-metadata.md) | `videoshowtype` |
| [广告加载](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [播出时段](sm-video-metadata.md) | `videodaypart` |
| [广告商](sm-ads.md) | `videoadadvertiser` |
| [营销活动 ID](sm-ads.md) | `videoadcampaign` |
| [流派](sm-video-metadata.md) | `videogenre` |
| [流类型](sm-core.md) | `videostreamtype` |
| [播放器 SDK 错误 ID](sm-quality.md) | `videoqoeplayersdkerrors` |
| [外部错误 ID](sm-quality.md) | `videoqoeextneralerrors` |
| [媒体馈送类型](sm-video-metadata.md) | `videofeedtype` |
| [进入媒体路径](entry-dimensions.md) | `entryvideopath` |
| [退出媒体路径](exit-dimensions.md) | `exitvideopath` |
| [条目流派](entry-dimensions.md) | `entryvideogenre` |
| [退出流派](exit-dimensions.md) | `exitvideogenre` |
| [进入播放器SDK错误ID](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [退出播放器SDK错误ID](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [进入外部错误ID](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [退出外部错误ID](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

Adobe Social退休了。

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| 术语 | `socialterm` |
| 社交平台/属性 | `socialcontentprovider` |
| 作者 | `socialauthor` |
| 语言 | `sociallanguage` |
| 纬度/经度 | `sociallatlong` |
| 资产跟踪代码 | `socialassettrackingcode` |
| 拥有的社交属性 | `socialaccountandappids` |
| 拥有的帖子 ID | `socialownedpostids` |
| 拥有的社交定义 | `socialinteractiontype` |
| 拥有的属性 ID | `socialownedpropertyid` |
| 拥有的属性和应用程序 | `socialownedpropertypropertyvsapp` |
| 拥有的属性名称 | `socialownedpropertyname` |
| 拥有的定义属性和帖子 | `socialowneddefinitionpropertyvspost` |
| 拥有的定义分析类型 | `socialowneddefinitioninsighttype` |
| 拥有的定义分析值 | `socialowneddefinitioninsightvalue` |
| 拥有的定义指标 | `socialowneddefinitionmetric` |
| 资产 | `socialmediaid` |

### Mobile SDK

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| [首次启动日期](lifecycle-dimensions.md) | `mobileinstalldate` |
| [应用程序ID](lifecycle-dimensions.md) | `mobileappid` |
| [启动次数](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [首次使用后间隔天数](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [上次使用后间隔天数](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [小时(SDK)](lifecycle-dimensions.md) | `mobilehourofday` |
| [每周时间(SDK)](lifecycle-dimensions.md) | `mobiledayofweek` |
| [操作系统(SDK)](lifecycle-dimensions.md) | `mobileosenvironment` |
| [上次升级后间隔天数](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [上次升级后启动次数](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [设备名称(SDK)](lifecycle-dimensions.md) | `mobiledevice` |
| [操作系统版本(SDK)](lifecycle-dimensions.md) | `mobileosversion` |
| [信标Major](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [次要信标](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [信标UUID](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [邻近地区信标](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [位置（精确到 10 千米）](lifecycle-dimensions.md) | `latlon1` |
| [位置（精确到 100 米）](lifecycle-dimensions.md) | `latlon23` |
| [位置（精确到 1 米）](lifecycle-dimensions.md) | `latlon45` |
| [目标点名称](lifecycle-dimensions.md) | `pointofinterest` |
| [与目标点中心的距离](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [位置准确度](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [放置类别](lifecycle-dimensions.md) | `mobileplacecategory` |
| [地标ID](lifecycle-dimensions.md) | `mobileplaceid` |
| [登录信标Major](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [退出信标Major](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [登录信标Minor](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [退出信标Minor](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [登录信标UUID](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [退出信标UUID](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [登录信标Proximity](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [退出信标Proximity](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| AMO ID | `amo_cid` |

### Activity Map

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| [Activity Map链接（按地区）](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Activity Map地区](activity-map-region.md) | `clickmapregion` |
| [Activity Map链接](activity-map-link.md) | `clickmaplink` |
| [Activity Map页面](activity-map-page.md) | `clickmappage` |

### Nielsen 集成

有关如何实施此集成的更多信息，请参阅Adobe Exchange上的[Nielsen扩展](https://exchange.adobe.com/apps/ec/101361)。

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| Nielsen 广告模型 | `nielsenadmodel` |
| Nielsen 区段 C | `nielsensegmentc` |
| Nielsen 区段 B | `nielsensegmentb` |
| Nielsen 区段 A | `nielsensegmenta` |
| Nielsen 内容 ID | `nielsencontentid` |
| Nielsen资产/计划 | `nielsenasset` |
| Nielsen VCID | `nielsenvcid` |
| Nielsen 选择退出 | `nielsenoptout` |
| Nielsen 客户 ID + VCID | `nielsenclientidvcid` |
| Nielsen 客户 ID | `nielsenclientid` |
| 登录 Nielsen 选择退出 | `entrynielsenoptout` |
| 退出 Nielsen 选择退出 | `exitnielsenoptout` |
| 登录 Nielsen 客户端 ID + VCID | `entrynielsenclientidvcid` |
| 退出 Nielsen 的客户 ID + VCID | `exitnielsenclientidvcid` |
| 登录 Nielsen 客户端 ID | `entrynielsenclientid` |
| 退出 Nielsen 的客户 ID | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| 资产 ID | `aemassetid` |
| 资产来源 | `aemassetsource` |
| 点击的资产 ID | `aemclickedassetid` |
| 登录资产 ID | `entryaemassetid` |
| 退出的资产 ID | `exitaemassetid` |

### Adobe Campaign

| 维度名称（在 Analytics UI 中可见） | 维度 ID（用于 API 请求） |
|--- |--- |
| Adobe Campaign 执行的提交 ID | `ac_delivery_internal_name` |
