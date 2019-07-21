---
title: 分析维度兼容性
seo-title: 与Analysis Workspace、Reports& Analytics兼容的分析维度和报告。
description: Analytics维度和报表的参考。
seo-description: Analysis Workspace维度、Reports& Analytics维度、维度、R& A维度、Workspace维度
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# 分析维度兼容性

此引用文章列出了在Reports&amp; Analytics和Analysis Workspace、仅限Analysis Workspace中以及仅在Reports&amp; Analytics中支持的维度/报表。

请记住以下事项

* 这些列表并不详尽。每个报表包都可能启用了一组给定的产品变量，也可能未启用。此外，任何给定的报表包都可能启用或禁用了任意数量的自定义变量，或者将这些变量映射到产品变量。此外，我们还忽略了访客属性和分类，因为它们对于每个报表包而言是唯一的。

* There are some cases of overlap, where Analytics tools use different terms for what is essentially the same thing, for example: `browserwidth` and `browserwidthbucketed`.

## 在 Reports &amp; Analytics 和 Analysis Workspace 中均受支持的维度

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|---|---|
| 目标分析 | targetraw |
| 受众 ID | mcaudiences |
| 浏览器 | browser |
| 浏览器类型 | browsertype |
| 类别 | category |
| 城市 | geocity |
| 颜色深度 | colordepth |
| 连接类型 | connectiontype |
| Cookie 支持 | Cookie |
| 国家/地区 | geocountry |
| 客户忠诚度 | customerloyalty |
| 自定义转化变量 | evar1、evar2，etc. |
| 自定义分析变量 | prop1、prop等 |
| 自定义链接 | customlink |
| 首次购买间隔天数 | daysbeforefirstpurchase |
| 上次购买间隔天数 | dayssincelastpurchase |
| 域 | filtereddomain |
| 下载链接 | downloadlink |
| 登录页面 | entrypage |
| 原始登录页面 | entrypageoriginal |
| 退出链接 | exitlink |
| 首个联系渠道 | firsttouchchannel |
| 首个联系渠道详细信息 | firsttouchchanneldetail |
| 启用Java | javaenabled |
| 语言 | language |
| 最近联系渠道 | lasttouchchannel |
| 最近联系渠道详细信息 | lasttouchchanneldetail |
| 列表变量 | listvariables |
| 营销渠道 | marketingchannel |
| 移动设备音频支持 | mobileaudiosupport |
| 移动设备运营商 | mobilecarrier |
| 移动设备颜色深度 | mobilecolordepth |
| 移动设备 cookie 支持 | mobilecookiesupport |
| 移动设备 | mobiledevicename |
| 移动设备类型 | mobiledevicetype |
| 移动设备电子邮件最大长度 | mobileemaillength |
| 移动设备图像支持 | mobileimagesupport |
| 移动设备制造商 | mobilemanufacturer |
| 移动设备操作系统（已弃用） | mobileos |
| 移动设备屏幕高度 | mobilescreenheight |
| 移动设备屏幕大小 | mobilescreensize |
| 移动设备屏幕宽度 | mobilescreenwidth |
| 移动设备浏览器 URL 最大长度 | mobileurllength |
| 移动设备视频支持 | mobilevideosupport |
| 监视器分辨率 | monitorresolution |
| 操作系统 | operatingsystem |
| 原始反向链接域名 | referringdomainoriginal |
| 页面 | page |
| 页面未找到 | pagesnotfound |
| 产品 | product |
| 反向链接 | referrer |
| 反向链接类型 | referrertype |
| 反向链接域 | referringdomain |
| 地区 | georegion |
| 回访频度 | returnfrequency |
| SC-TnT | tntbase |
| 搜索引擎 | searchengine |
| 搜索关键词 | searchenginekeyword |
| 搜索引擎 - 免费 | searchenginenatural |
| 搜索引擎 - 付费 | searchenginepaid |
| 搜索关键词 - 免费 | searchenginenaturalkeyword |
| 搜索关键词 - 付费 | searchenginepaidkeyword |
| 所有搜索页面排名 | searchenginepagerank |
| 服务器 | server |
| 单页面访问量 | singlepagevisits |
| 网站区域 | sitesections |
| 每次访问逗留时间 - 粒度 | sitetime |
| 跟踪代码 | campaign |
| 美国 DMA | geodma |
| 美国各州 | state |
| 发生事件之前逗留的时间 | timeprior |
| 每次访问逗留时间 - 分段统计 | timespent |
| 访问深度 | pathlength |
| 访问量 | visitnumber |
| 邮政编码 | zip |

## 仅在 Analysis Workspace 中受支持的维度

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| 上午/下午 | timepartampm |
| 浏览器高度 - 分段统计 | browserheightbucketed |
| 浏览器宽度 - 分段统计 | browserwidthbucketed |
| 日 | daterangeday |
| 日期 | timepartdayofmonth |
| 每周时间 | dayofweek |
| 每周时间 | timepartdayofweek |
| 每年的某一天 | timepartdayofyear |
| 上次访问间隔天数 | dayssincelastvisit |
| 登录自定义分析 | entryprops |
| 登录列表变量 | entrylistvariables |
| 登录服务器 | entryserver |
| 登录网站区域 | entrysitesections |
| 退出点自定义分析 | exitprops |
| 退出点列表变量 | exitlistvariables |
| 退出页面 | exitpage |
| 退出服务器 | exitserver |
| 退出网站区域 | exitsitesections |
| 点击深度 | hitdepth |
| 点击类型 | hittype |
| 小时 | daterangehour |
| 每天时间 | timeparthourofday |
| 营销渠道详细信息 | marketingchanneldetail |
| 分钟 | daterangeminute |
| 移动设备书签最大长度 | mobilebookmarklength |
| 移动设备数 | mobiledevicenumber |
| 移动设备 DRM | mobiledrm |
| 移动设备信息服务 | mobileinformationservices |
| 移动设备 Java VM | mobilejavavm |
| 移动设备邮件修饰 | mobilemaildecoration |
| 移动设备网络协议 | mobilenetprotocols |
| 移动设备按键通话 | mobilepushtotalk |
| 月 | daterangemonth |
| 月份 | timepartmonthofyear |
| 操作系统类型 | operatingsystemgroup |
| 付费搜索 | paidsearch |
| 永久 Cookie 支持 | persistentcookie |
| 季度 | daterangequarter |
| 季度 | timepartquarterofyear |
| 调查 | surveybase |
| 页面逗留时间 - 分段统计 | averagepagetime |
| 页面逗留时间 - 粒度 | pagetimeseconds |
| 跟踪选择退出的原因 | optoutreason |
| 工作日/周末 | timepartweekdayweekend |
| 周 | daterangeweek |
| 年 | daterangeyear |

## 仅在 Analysis Workspace 中受支持的内容感知维度

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| Activity Map XY | clickmapxy |
| 媒体会话 ID | videosessionid |
| Nielsen 访问方法 | nielsenaccmethod |
| Nielsen 应用程序 ID | nielsenappid |
| Nielsen 渠道资产 | nielsenchannelasset |
| Nielsen 内容类型 | nielsencontenttype |

## 仅在 Reports &amp; Analytics 中受支持的维度

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| 浏览器高度 | browserheight |
| 浏览器宽度 | browserwidth |
| 每日独特客户 | dailyuniquecustomers |
| JavaScript | javascriptsupport |
| JavaScript 版本 | javascriptversion |
| 每月独特客户 | monthlyuniquecustomers |
| 每季独特客户 | quarterlyuniquecustomers |
| 时区 | timezone |
| 顶级域名 | topleveldomain |
| 访客所在州 | legacystate |
| 每周独特客户 | weeklyuniquecustomers |
| 每年独特客户 | yearlyuniquecustomers |

## Reports &amp; Analytics 中的预配置报表

Reports &amp; Analytics 中包含多个预配置报表，如果此类报表未映射到某个特定的维度，那么就会使用一系列维度。下面列出了这些报表：

* 书签 URL 长度
* 浏览器
* 浏览器类型
* 促销活动转化漏斗
* 购物车转化漏斗
* 城市
* 进入页面点击数
* 国家/地区
* 交叉销售
* 自定义事件漏斗
* 修饰邮件支持
* 设备号传输（打开/关闭）
* 域名
* DRM
* 登录页面
* 退出页面
* 流失
* 完整路径
* ICities
* 信息服务
* Java 版本
* 语言
* 最长路径
* 媒体并行查看者
* 媒体时段
* 媒体详细信息
* 媒体概览
* 显示器分辨率
* 网络协议
* Netscape 插件
* 下一页面
* 下一页面流量
* 操作系统
* 操作系统类型
* 页面深度
* 页面概要
* PathFinder
* 上一页面流量
* 上一页面
* PTT
* 产品转化漏斗
* 购买转化漏斗
* 反向链接域名
* 地区
* 重新载入
* 搜索引擎 - 全部
* 搜索引擎 - 免费
* 搜索引擎 - 付费
* 搜索关键词 - 全部
* 搜索关键词 - 免费
* 搜索关键词 - 付费
* Target 活动详细信息
* 页面逗留时间
* 时区
* 顶级域名
* 美国 DMA
* 美国各州
* 访问量
* 访客主页

## 在 Reports &amp; Analytics 和 Analysis Workspace 中均受支持的内容感知维度

### 视频（媒体分析）

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| 内容 | video |
| 内容区段 | videosegment |
| 内容类型 | videocontenttype |
| 广告播放器名称 | videoadplayername |
| 面板中的广告位置 | videoadinpod |
| 丢帧 | videoqoedroppedframecountevar |
| 错误 | videoqoeerrorcountevar |
| 平均比特率 | videoqoebitrateaverageevar |
| 比特率更改 | videoqoebitratechangecountevar |
| 缓冲总持续时间 | videoqoebuffertimeevar |
| 缓冲事件 | videoqoebuffercountevar |
| 开始时间 | videoqoetimetostartevar |
| 广告面板 | videoadpod |
| 媒体路径 | videopath |
| 广告 | videoad |
| 内容播放器名称 | videoplayername |
| 内容渠道 | videochannel |
| 章节 | videochapter |
| 内容名称（变量） | videoname |
| 内容时长（变量） | videolength |
| 广告名称（变量） | videoadname |
| 广告长度（变量） | videoadlength |
| 节目 | videoshow |
| 季 | videoseason |
| 剧集 | videoepisode |
| 网络 | videonetwork |
| 节目类型 | videoshowtype |
| 广告加载次数 | videoadload |
| MVPD | videomvpd |
| 播出时段 | videodaypart |
| 广告商 | videoadadvertiser |
| 促销活动 ID | videoadcampaign |
| 流派 | videogenre |
| 流类型 | videostreamtype |
| 播放器 SDK 错误 ID | videoqoeplayersdkerrors |
| 外部错误 ID | videoqoeextneralerrors |
| 媒体馈送类型 | videofeedtype |
| 登录媒体路径 | entryvideopath |
| 退出媒体路径 | exitvideopath |
| 登录流派 | entryvideogenre |
| 退出流派 | exitvideogenre |
| 登录播放器 SDK 错误 ID | entryvideoqoeplayersdkerrors |
| 退出播放器 SDK 错误 ID | exitvideoqoeplayersdkerrors |
| 登录外部错误 ID | entryvideoqoeextneralerrors |
| 退出外部错误 ID | exitvideoqoeextneralerrors |

### Adobe Social

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| 术语 | socialterm |
| 社交平台/属性 | socialcontentprovider |
| 作者 | socialauthor |
| 语言 | sociallanguage |
| 纬度/经度 | sociallatlong |
| 资产跟踪代码 | socialassettrackingcode |
| 拥有的社交属性 | socialaccountandappids |
| 拥有的帖子 ID | socialownedpostids |
| 拥有的社交定义 | socialinteractiontype |
| 拥有的属性 ID | socialownedpropertyid |
| 拥有的属性和应用程序 | socialownedpropertypropertyvsapp |
| 拥有的属性名称 | socialownedpropertyname |
| 拥有的定义属性和帖子 | socialowneddefinitionpropertyvspost |
| 拥有的定义分析类型 | socialowneddefinitioninsighttype |
| 拥有的定义分析值 | socialowneddefinitioninsightvalue |
| 拥有的定义量度 | socialowneddefinitionmetric |
| 资产 | socialmediaid |

### Mobile SDK

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| 首次启动日期 | mobileinstalldate |
| 应用程序 ID | mobileappid |
| 启动次数 | mobilelaunchnumber |
| 首次使用后间隔天数 | mobiledayssincefirstuse |
| 上次使用后间隔天数 | mobiledayssincelastuse |
| 小时 (SDK) | mobilehourofday |
| 每周时间 (SDK) | mobiledayofweek |
| 操作系统 (SDK) | mobileosenvironment |
| 上次升级后间隔天数 | mobiledayssincelastupgrade |
| 上次升级后启动次数 | mobilelaunchessincelastupgrade |
| 设备名称 (SDK) | mobiledevice |
| 操作系统版本 (SDK) | mobileosversion |
| 信标 Major | mobilebeaconmajor |
| 信标 Minor | mobilebeaconminor |
| 信标 UUID | mobilebeaconuuid |
| 信标 Proximity | mobilebeaconproximity |
| 位置（精确到 10 千米） | latlon1 |
| 位置（精确到 100 米） | latlon23 |
| 位置（精确到 1 米） | latlon45 |
| 目标点名称 | pointofinterest |
| 与目标点中心的距离 | pointofinterestdistance |
| 位置准确度 | mobileplaceaccuracy |
| 位置目录 | mobileplacecategory |
| 位置 ID | mobileplaceid |
| 登录信标 Major | entrymobilebeaconmajor |
| 退出信标 Major | exitmobilebeaconmajor |
| 登录信标 Minor | entrymobilebeaconminor |
| 退出信标 Minor | exitmobilebeaconminor |
| 登录信标 UUID | entrymobilebeaconuuid |
| 退出信标 UUID | exitmobilebeaconuuid |
| 登录信标 Proximity | entrymobilebeaconproximity |
| 退出信标 Proximity | exitmobilebeaconproximity |

### Adobe Advertising Cloud(AMO)

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| AMO EF ID | amo_ef_id |
| AMO ID | amo_cid |

### Activity Map

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| 按区域划分的 Activity Map 链接 | clickmaplinkbyregion |
| Activity Map 区域 | clickmapregion |
| Activity Map 链接 | clickmaplink |
| Activity Map 页面 | clickmappage |

### Nielsen 集成

有关如何实施此集成的更多信息，请参阅 [Nielsen 合作伙伴](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html)。

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| Nielsen 广告模型 | nielsenadmodel |
| Nielsen 区段 C | nielsensegmentc |
| Nielsen 区段 B | nielsensegmentb |
| Nielsen 区段 A | nielsensegmenta |
| Nielsen 内容 ID | nielsencontentid |
| Nielsen 资产/节目 | nielsenasset |
| Nielsen VCID | nielsenvcid |
| Nielsen 选择退出 | nielsenoptout |
| Nielsen 客户 ID + VCID | nielsenclientidvcid |
| Nielsen 客户 ID | nielsenclientid |
| 登录 Nielsen 选择退出 | entrynielsenoptout |
| 退出 Nielsen 选择退出 | exitnielsenoptout |
| 登录 Nielsen 客户端 ID + VCID | entrynielsenclientidvcid |
| 退出 Nielsen 的客户 ID + VCID | exitnielsenclientidvcid |
| 登录 Nielsen 客户端 ID | entrynielsenclientid |
| 退出 Nielsen 的客户 ID | exitnielsenclientid |

### Adobe Experience Manager (AEM)

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| 资产 ID | aemassetid |
| 资产来源 | aemassetsource |
| 点击的资产 ID | aemclickedassetid |
| 登录资产 ID | entryaemassetid |
| 退出的资产 ID | exitaemassetid |

### Adobe Campaign

| 维度名称(在Analytics UI中可见) | 维度 ID（用于 API 请求） |
|--- |--- |
| Adobe Campaign 执行的提交 ID | ac_delivery_internal_name |
