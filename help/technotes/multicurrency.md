---
description: 介绍如何定义目标货币代码以使多货币支持正常工作。
title: 多货币支持
topic: null
uuid: null
translation-type: ht
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# 多货币支持

本文档介绍如何为多货币支持定义目标货币代码。

目标货币代码可在以下三个级别中定义：

## 页面级别

您可以在页面级别为目标货币设置 JavaScript 变量。网站所有者使用三字母 ISO 4217 货币代码（如本文档下面所列）来设置此变量。如果未在此级别设置 [currencyCode](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/vars/config-vars/currencycode.html) 变量，则默认货币将与报表包中指定的货币相同。如果页面级别的变量与报表包中指定的变量冲突，则将优先使用报表包中的变量。


## 报表包级别

[创建报表包](https://docs.adobe.com/content/help/zh-Hans/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)时将指定&#x200B;**基本货币**。这是货币的默认设置，优先于在页面级别设置的货币代码。因此，如果某报表包内有接受美元、欧元和英镑的订单，且报表包的默认货币代码设置为“美元”，则报告后端数据库会将所有交易额都折算为美元。

市场营销报告使用以图像请求发出的汇率将页面级别的货币值折算为默认的报表包货币值。报表包将使用“美元”作为默认货币。


## 报表级别

用户可设置用户登录会话的默认报告货币。可通过任何&#x200B;**转化报表**&#x200B;中的“显示选项”链接来设置。市场营销报告使用以报表运行时的汇率将报表包货币值折算为报表指定的货币值。

## 支持的货币代码 (ISO 4217)

Analytics 当前支持以下货币格式进行折算交易：


“AFA”阿富汗尼 (AFA)

“AFN”阿富汗尼 (AFN)

“ALL”阿尔巴尼亚勒克 (ALL)

“DZD”阿尔及利亚第纳尔 (DZD)

“AOA”安哥拉宽扎 (AOA)

“ARS”阿根廷比索 (ARS)

“AMD”亚美尼亚德拉姆 (AMD)

“AWG”阿鲁巴岛荷兰盾 (AWG)

“AUD”澳元 (AUD)

“AZM”阿塞拜疆马纳特 (AZM)

“AZN”阿塞拜疆新马纳特 (AZN)

“BSD”巴哈马元 (BSD)

“BHD”巴林第纳尔 (BHD)

“BDT”孟加拉国塔卡 (BDT)

“BBD”巴巴多斯元 (BBD)

“BYR”白俄罗斯卢布 (BYR)

“BZD”伯利兹元 (BZD)

“BMD”百慕大元 （BMD）

“BTN”不丹努尔特鲁姆 (BTN)

“BOB”玻利维亚币 (BOB)

“BAM”波斯尼亚可兑换马卡尔 (BAM）

“BWP”博茨瓦纳普拉 (BWP)

“BRL”巴西雷亚尔 (BRL)

“BND”文莱元 (BND)

“BGN”保加利亚列弗 (BGN)

“BIF”布隆迪法郎 (BIF)

“KHR”柬埔寨瑞尔 (KHR)

“CAD”加拿大元 (CAD)

“CVE”佛得角埃斯库多 (CVE)

“KYD” 开曼岛元 (KYD)

“CLP”智利比索 (CLP)

“CNY”中国人民币 (CNY)

“COP”哥伦比亚比索 (COP)

“XOF”非洲金融共同体法郎 BCEAO (XOF)

“XAF”非洲金融共同体法郎 BEAC (XAF)

“KMF”科摩罗法郎 (KMF)

“XPF”太平洋法郎 (XPF)

“CDF”刚果/金沙萨法郎 (CDF)

“CRC”哥斯达黎加科朗 (CRC)

“HRK”克罗地亚库纳 (HRK)

“CUC”古巴可兑换比索 (CUC)

“CUP 古巴比索 (CUP)

“CYP”塞浦路斯镑 (CYP)

“CZK”捷克共和国克朗 (CZK)

“DKK”丹麦克朗 (DKK)

“DJF”吉布提法郎 (DJF)

“DOP”多米尼加比索 (DOP)

“XCD”东加勒比元 (XCD)

“EGP”埃及镑 (EGP)

“SVC”萨尔瓦多科朗 (SVC)

“ERN”厄立特里亚纳克法 (ERN)

“XBT”ERR (XBT)

“EEK”爱沙尼亚克朗 (EEK)

“ETB”埃塞俄比亚比尔 (ETB)

“EUR”欧元 (EUR)

“FKP”福克兰群岛镑 (FKP)

“FJD”斐济元 (FJD)

“GMD”冈比亚达拉西 (GMD)

“GEL”格鲁吉亚拉里 (GEL)

“GHC”加纳塞地 (GHC)

“GHS”加纳塞地 (GHS)

“GIP”直布罗陀镑 (GIP)

“XAU”金盎司 (XAU)

“GTQ”危地马拉格查尔 (GTQ)

“GGP”根西岛镑 (GGP)

“GNF”几内亚法郎 (GNF)

“GYD”圭亚那元 (GYD)

“HTG”海地古德 (HTG)

“HNL”洪都拉斯伦皮拉 (HNL)

“HKD”港币 (HKD)

“HUF”匈牙利福林 (HUF)

“ISK”冰岛克朗 (ISK)

“INR”印度卢比 (INR)

“IDR”印度尼西亚卢比 (IDR)

“XDR”国际货币基金组织特别提款权 (XDR)

“IRR”伊朗里亚尔 (IRR)

“IQD”伊拉克第纳尔 (IQD)

“IMP”曼岛磅 (IMP)

“ILS”以色列新谢克尔 (ILS)

“JMD”牙买加元 (JMD)

“JPY”日元 (JPY)

“JEP”泽西岛镑 (JEP)

“JOD”约旦第纳尔 (JOD)

“KZT”哈萨克斯坦坚戈 (KZT)

“KES”肯尼亚先令 (KES)

“KWD”科威特第纳尔 (KWD)

“KGS”吉尔吉斯斯坦索姆 (KGS)

“LAK”老挝基普 (LAK)

“LVL”拉脱维亚拉提 (LVL)

“LBP”黎巴嫩镑 (LBP)

“LSL”巴索托洛蒂 (LSL)

“LRD”利比里亚元 (LRD)

“LYD”利比亚第纳尔 (LYD)

“LTL”立陶宛立特 (LTL)

“MOP”澳门元 (MOP)

“MKD”马其顿第纳尔 (MKD)

“MGA”马达加斯加阿里亚里 (MGA)

“MWK”马拉维克瓦查 (MWK)

“MYR”马来西亚林吉特 (MYR)

“MVR”马尔地夫拉菲亚 (MVR)

“MTL”马耳他里拉 (MTL)

“MRO”毛里塔尼亚乌吉亚 (MRO)

“MUR”毛里求斯卢比 (MUR)

“MXN”墨西哥比索 (MXN)

“MDL”摩尔多瓦列伊 (MDL)

“MNT”蒙古图格里克 (MNT)

“MAD”摩洛哥迪拉姆 (MAD)

“MZN”莫桑比克梅蒂卡尔 (MZN)

“MZM”莫桑比克梅蒂卡尔 (MZM)

“MMK”缅甸元 (MMK)

“NAD”纳米比亚元 (NAD)

“NPR”尼泊尔卢比 (NPR)

“ANG”荷兰盾 (ANG)

“NZD”新西兰元 (NZD)

“NIO”尼加拉瓜科多巴 (NIO)

“NGN”尼日利亚奈拉 (NGN)

“KPW”朝鲜圆 (KPW)

“NOK”挪威克朗 (NOK)

“OMR”阿曼里亚尔 (OMR)

“PKR”巴基斯坦卢比 (PKR)

“XPD”钯盎司 (XPD)

“PAB”巴拿马巴波亚 (PAB)

“PGK”巴布亚新几内亚基那 (PGK)

“PYG”巴拉圭瓜拉尼 (PYG)

“PEN”秘鲁索尔 (PEN)

“PHP”菲律宾比索 (PHP)

“XPT”铂盎司 (XPT)

“PLN”波兰兹罗提 (PLN)

“QAR”卡塔尔里亚尔 (QAR)

“ROL”罗马尼亚列伊 (ROL)

“RON”罗马尼亚新列伊 (RON)

“RUB”俄罗斯卢布 (RUB)

“RUR”俄罗斯卢布 (RUR)

“RWF”卢旺达法郎 (RWF)

“SHP”圣赫勒拿磅 (SHP)

“WST”萨摩亚塔拉 (WST)

“STD”圣多美和普林西比多布拉 (STD)

“SAR”沙特阿拉伯里亚尔 (SAR)

“SPL”塞波加大公国货币 (SPL)

“RSD”塞尔维亚第纳尔 (RSD)

“CSD”塞尔维亚第纳尔 (CSD)

“SCR”塞舌尔卢比 (SCR)

“SLL”塞拉利昂利昂 (SLL)

“XAG”银盎司 (XAG)

“SGD”新加坡元 (SGD)

“SKK”斯洛伐克克朗 (SKK)

“SIT”斯洛文尼亚托拉尔 (SIT)

“SBD”所罗门群岛元 (SBD)

“SOS”索马里先令 (SOS)

“ZAR”南非兰特 (ZAR)

“KRW”韩元 (KRW)

“LKR”斯里兰卡卢比 (LKR)

“SDD”苏丹第纳尔 (SDD）

“SDG”苏丹镑 (SDG)

“SRD”苏里南元 (SRD)

“SRG”苏里南盾 (SRG)

“SZL”斯威士兰里兰吉尼 (SZL)

“SEK”瑞典克朗 (SEK)

“CHF”瑞士法郎 (CHF)

“SYP”叙利亚镑 (SYP)

“TWD”新台币 (TWD）

“TJS”塔吉克斯坦索莫尼 (TJS)

“TZS”坦桑尼亚先令 (TZS)

“THB”泰铢 (THB)

“TOP”汤加潘加 (TOP)

“TTD”特立尼达和多巴哥元 (TTD)

“TND”突尼斯第纳尔 (TND)

“TRY”土耳其里拉 (TRY)

“TRL”土耳其里拉 (TRL)

“TMM”土库曼斯坦马纳特 (TMM)

“TMT”土库曼斯坦新马纳特 (TMT)

“TVD”图瓦卢元 (TVD)

“UGX”乌干达先令 (UGX)

“UAH”乌克兰格里夫纳 (UAH)

“AED”阿联酋迪拉姆 (AED）

“GBP”英镑 (GBP)

“USD”选定美元 (USD)

“UYU”乌拉圭比索 (UYU)

“UZS”乌兹别克斯坦索姆 (UZS)

“VUV”瓦努阿图瓦图 (VUV)

“VEB”委内瑞拉玻利瓦尔 (VEB)

“VEF”委内瑞拉玻利瓦尔 (VEF)

“VND”越南盾 (VND)

“YER”也门里亚尔 (YER)

“ZMK”赞比亚克瓦查 (ZMK)

“ZMW”赞比亚克瓦查 (ZMW)

“ZWD”津巴布韦元 (ZWD)


## AppMeasurement.js 示例

可以在 AppMeasurement.js 文件中全局定义 `currencyCode` 变量。在此文件中定义 currencyCode 变量可确保所有的货币交易都使用统一的货币代码。以下示例将欧元指定为 AppMeasurement.js 文件 `CONFIG SECTION` 中的 `currencyCode` 变量。报表会将所有购买事件都解释为“欧元”交易。

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

有关编辑 AppMeasurement.js 文件的更多信息，请参阅[将代码插入 AppMeasurement.js 文件](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)。

## 其它实施注意事项

* 请记住，虽然不同页面上货币代码可以不同，但是在指定页面请求上定义的所有兑换行项目必须使用同一货币（例如，您不能在同一页面视图上定义欧元、英镑和美元）。如果不想进行任何货币折算，应将 currencyCode 值保留为空。这会导致发送的值在不进行折算的情况下直接传递到报表。

* 设置无效的 currencyCode（“支持的货币代码”列表上没有的任何值）会导致排除整个点击，并且不会为该交易收集任何数据。在生产中设置 `currencyCode` 之前，请使用测试报表包来验证是否收集数据以及货币折算是否正确。

* 必须修改未使用句点 (.) 作为分隔符的货币，以使用句点而不是典型的分隔符。例如，必须将使用逗号 (,) 的瑞典克朗修改为使用句点。如果 Analytics 使用逗号来分隔值，将无法准确传递数据。句点可准确地将值传递到报表。
