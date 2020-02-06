---
description: 介绍如何定义目标货币代码，以便提供多货币支持。
title: 多货币支持
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# 多货币支持

本文档介绍如何为多货币支持定义目标货币代码。

目标货币代码在以下三个级别中定义：

## 页面级别

您可以在页面级别为目标货币设置JavaScript变量。 站点所有者使用相应的三字母ISO 4217货币代码设置此变量（如本文档下面所列）。 如果 [currencyCode变量未在此级别设置](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/currencycode.html) ，则默认货币将与报表包中指定的货币相同。 如果页面级别的变量与报表包中指定的变量冲突，则报表包中的变量将优先。


## 报告套件级别

创建 **报表包时** ，将指 [定基本货币](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)。 这是货币的默认设置，优先于在页面级别设置的货币代码。 因此，如果报表包的订单接受美元、欧元和英镑，并且报表包的默认货币代码设置为“美元”，则报表后端数据库将所有交易转换为美元。

市场营销报告使用图像请求发出时的汇率将页面级别的货币值折算为默认报表包货币值。 报表包使用“美元”作为默认货币。


## 报告级别

用户可以为用户登录会话设置默认报告的货币。 可通过任何&#x200B;**转化报表**&#x200B;中的“显示选项”链接来设置。市场营销报告使用运行报告时的汇率将报告包货币值折算为报告指定的货币值。

## 支持的货币代码(ISO 4217)

Analytics当前支持以下货币格式进行转换交易：


阿富汗阿富汗阿富汗(AFA)

阿富汗阿富汗阿富汗（阿富汗）

&quot;全&quot;阿尔巴尼亚莱克（全）

“DZD”阿尔及利亚第纳尔(DZD)

安哥拉宽扎(AOA)

&quot;ARS&quot;阿根廷比索(ARS)

&quot;AMD&quot;亚美尼亚德拉姆(AMD)

阿鲁巴盾(AWG)

澳元（澳元）

阿塞拜疆马纳茨(AZM)

&quot;AZN&quot;阿塞拜疆新马纳茨(AZN)

“BSD”巴哈马元(BSD)

&quot;BHD&quot;巴林第纳尔(BHD)

孟加拉塔卡

巴巴多斯元

白俄罗斯卢布

伯利兹元

百慕大元

&quot;BTN&quot;不丹努尔特鲁姆(BTN)

玻利维亚诺

波——黑可转换马卡(BAM)

博茨瓦纳普拉斯

巴西雷亚尔（巴西雷亚尔）

文莱元（文莱元）

保加利亚列弗(BGN)

布隆迪法郎(BIF)

柬埔寨里尔斯

加拿大元

“CVE”佛得角埃斯库多斯(CVE)

开曼群岛元

“CLP”智利比索(CLP)

人民币

&quot;COP&quot;哥伦比亚比索(COP)

非洲金融共同体法郎BCEAO（非洲金融共同体法郎）

非洲金融共同体法郎BEAC（非洲金融共同体）

科摩罗法郎(KMF)

&quot;XPF&quot;太平洋法郎(XPF)

&quot;CDF&quot;刚果／金沙萨法郎(CDF)

哥斯达黎加科朗

克罗地亚库纳(HRK)

古巴可兑换比索

古巴比索（杯）

塞浦路斯镑

捷克共和国克朗

丹麦克朗(DKK)

吉布提法郎(DJF)

多米尼加比索(DOP)

东加勒比元

埃及镑

&quot;SVC&quot;萨尔瓦多科隆(SVC)

&quot;ERN&quot;厄立特里亚纳克法(ERN)

“XBT”ERR(XBT)

《EEK》爱沙尼亚·克罗尼(EEK)

埃塞俄比亚比尔

欧元（欧元）

福克兰群岛镑

斐济元（斐济元）

冈比亚达拉西(GMD)

&quot;GEL&quot; Georgia Lari(GEL)

加纳塞迪斯

加纳塞地（全球统一制度）

直布罗陀镑

XAU金盎司(XAU)

《格查尔》危地马拉格查尔（格查尔）

格恩西镑

&quot;GNF&quot;几内亚法郎(GNF)

圭亚那元（圭亚那元）

“HTG”海地古德(HTG)

洪都拉斯伦皮拉(HNL)

“港元”港元

匈牙利福林

冰岛克朗(ISK)

印度卢比（印度卢比）

“IDR”印度尼西亚盾(IDR)

XDR国际货币基金特别提款权(XDR)

“IRR”伊朗里亚尔(IRR)

“IDR”伊拉克第纳尔(IDR)

&quot;IMP&quot;马恩岛(IMP)

“ILS”以色列新谢克尔(ILS)

牙买加元

“JPY”日元(JPY)

JEP泽西镑(JEP)

“JOD”约旦第纳尔(JOD)

&quot;KZT&quot;哈萨克斯坦腾格(KZT)

肯尼亚先令(KES)

&quot;KWD&quot;科威特第纳尔(KWD)

&quot;KGS&quot;吉尔吉斯斯坦索姆(KGS)

“LAK”老挝基普(LAK)

拉脱维亚拉提(LVL)

黎巴嫩镑

莱索托马洛蒂(LSL)

利比里亚元

“LYD”利比亚第纳尔(LYD)

《立陶宛立泰》

澳门元

马其顿第纳尔

马达加斯加阿里亚里

马拉维克瓦查斯(MWK)

马来西亚林吉特(MYR)

马尔地夫鲁菲亚(MVR)

&#39;MTL&#39;马耳他里拉(MTL)

毛里塔尼亚乌吉亚(MRO)

毛里求斯卢比(MUR)

“MXN”墨西哥比索(MXN)

摩尔多瓦列伊（列伊）

蒙古图格里克（图格里克）

摩洛哥迪拉姆(MAD)

莫桑比克美提卡(MZN)

莫桑比克美提卡(MZM)

缅甸缅元

纳米比亚元(NAD)

尼泊尔卢比(NPR)

荷属安的列斯盾(ANG)

新西兰元

尼加拉瓜科多巴(NIO)

尼日利亚奈拉斯(NGN)

朝鲜元(KPW)

“NOK”挪威克朗(NOK)

阿曼里亚尔(OMR)

巴基斯坦卢比(PKR)

XPD钯盎司(XPD)

&quot;PAB&quot;巴拿马巴尔博(PAB)

巴布亚新几内亚基那

巴拉圭瓜拉尼语(PYG)

秘鲁新索尔(PEN)

“PHP”菲律宾比索(PHP)

“XPT”铂金盎司(XPT)

波兰兹罗提(PLN)

卡塔尔里亚尔

罗尔罗州雷（罗尔州）

罗恩罗马尼亚新列伊

“卢布”俄罗斯卢布（卢布）

俄罗斯卢布

卢旺达法郎(RWF)

圣赫勒拿镑

“WST”萨摩亚塔拉(WST)

圣多美和普林西比多布拉(STD)

沙特阿拉伯里亚尔

“SPL”塞波加·卢伊吉尼(SPL)

塞尔维亚第纳尔

“CSD”塞尔维亚第纳尔(CSD)

塞舌尔卢比(SCR)

塞拉利昂利昂(SLL)

&quot;XAG&quot;银盎司(XAG)

新加坡元(SGD)

“SKK”斯洛伐克克朗(SKK)

斯洛文尼亚托拉尔(SIT)

所罗门群岛元

&quot;SOS&quot;索马里先令(SOS)

南非兰特(ZAR)

“韩圆”韩元（韩圆）

斯里兰卡卢比(LKR)

“SDD”苏丹第纳尔

“SDG”苏丹镑(SDG)

苏里南元

苏里南盾

《斯威士兰里兰吉尼》(SZL)

“瑞典克朗”(SEK)

瑞士法郎(CHF)

叙利亚镑

新台币（新台币）

塔吉克索莫尼(TJS)

坦桑尼亚先令

泰铢（泰铢）

“TOP”汤加潘加(TOP)

特立尼达和多巴哥元

“TND”突尼斯第纳尔(TND)

土耳其里拉（试用）

土耳其利拉

《土库曼斯坦马纳特》(TMM)

土库曼斯坦新马纳茨

图瓦卢元(TVD)

“UGX”乌干达先令(UGX)

乌克兰格里夫尼亚(UAH)

阿联酋迪拉姆(AED)

英镑（英镑）

&quot;美元&quot;选定美元（美元）

乌拉圭比索(UYU)

乌兹别克斯坦苏姆(UZS)

瓦努阿图瓦图(VUV)

委内瑞拉玻利瓦尔

委内瑞拉玻利瓦雷斯富尔特斯(VEF)

越南盾(VND)

“YER”也门里亚尔(YER)

赞比亚克瓦查(ZMK)

赞比亚克瓦查(ZMW)

“ZWD”津巴布韦元(ZWD)


## AppMeasurement.js示例

可 `currencyCode` 以在AppMeasurement.js文件中全局定义变量。 在此文件中定义currencyCode变量可确保所有货币事务都使用统一的货币代码。 以下示例将欧元指定 `currencyCode` 为AppMeasurement.js文 `CONFIG SECTION` 件中的变量。 所有购买事件都将被解释为“欧元”交易。

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

有关编辑AppMeasurement.js文件的详细信息，请参 [阅将代码插入AppMeasurement.js文件](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)。

## 其它实施注意事项

* 请记住，虽然货币代码可以在页面之间更改，但给定页面请求上定义的所有折换行项目必须使用相同的货币（例如，您不能在同一页面视图中定义欧元、英镑和美元）。 如果不想进行任何货币兑换，应将currencyCode值留空。 这会导致发送的值直接传递到不进行转换的报表。

* 设置无效的currencyCode（“支持的货币代码”列表上没有的任何值）会导致排除整个点击，并且不会为该事务收集数据。 在生产 `currencyCode` 中进行设置之前，请使用测试报告套件来验证已收集的数据以及货币换算是否正确。

* 必须修改未使用句点 (.) 作为分隔符的货币，以使用句点而不是典型的分隔符。例如，必须将使用逗号 (,) 的瑞典克朗修改为使用句点。分析使用逗号分隔值，数据将无法正确传递。 该期间将正确地将值传递给报表。
