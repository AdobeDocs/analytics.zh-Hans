---
title: currencyCode 变量是什么以及怎样使用它？
description: 对于电子商务网站，设置页面交易的货币。
translation-type: ht
source-git-commit: 4d0d5ca99049e48fcf1f248f78ecef94534b6815
workflow-type: ht
source-wordcount: '830'
ht-degree: 100%

---


# currencyCode

对于商业网站，收入和货币是 Analytics 的重要组成部分。很多网站（尤其是跨多个国家/地区的网站）都会使用多种不同的货币。使用 `currencyCode` 变量可确保按正确的币种计算收入。

如果未定义 `currencyCode` 但定义了货币值，则会将 [`products`](../page-vars/products.md) 变量和货币事件视为与报表包中使用的货币相同。要了解报表包中使用的货币，请参阅管理员用户指南中的[常规帐户设置](/help/admin/admin/general-acct-settings-admin.md)。

如果 `currencyCode` 已定义并且与报表包中使用的货币相一致，则无需进行货币换算。

如果 `currencyCode` 已定义并且与报表包中使用的货币不同，则 Adobe 会根据当天的汇率进行货币换算。Adobe 与 [XE](https://xe.com) 合作，共同开展每日的货币换算工作。数据收集服务器中存储的所有值最终都将以报表包中使用的货币进行存储。

>[!IMPORTANT]
>
>如果 `currencyCode` 包含无效值，则整个点击都会被丢弃，从而导致数据丢失。如果要在实施中使用此变量，请确保正确定义此变量。

此变量不会在点击之间保留。确保在涉及收入或货币事件的每个页面上定义此变量。

## Adobe Experience Platform Launch 中的“货币代码”

“货币代码”是在配置 Adobe Analytics 扩展时显示在[!UICONTROL 常规]折叠面板中的一个字段。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的[!UICONTROL 配置]按钮。
4. 展开[!UICONTROL 常规]折叠面板，这会显示[!UICONTROL 货币代码]字段。

您可以使用预设货币代码或自定义货币代码。如果使用自定义货币代码，请确保该代码有效。

## Adobe Experience Platform Mobile SDK 中的货币代码

货币代码通过 Adobe Analytics 扩展中的上下文数据变量传递到 Adobe Experience Platform Mobile SDK。

1. 在 `trackState` 或 `trackAction` 期间在上下文数据变量中设置货币代码。
2. 在 Adobe Analytics 管理控制台中为报表包创建处理规则。设置规则以覆盖货币代码变量。
3. 将货币代码传递给 `trackState` 或 `trackAction` 调用中的 `products` 变量。

您可以使用预设货币代码或自定义货币代码。如果使用自定义货币代码，请确保该代码有效。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.currencyCode

`s.currencyCode` 变量是一个字符串，其中包含由 3 个大写字母构成的表示页面上所用货币的代码。

```js
s.currencyCode = "USD";
```

以下货币代码有效：

| 货币代码 | 货币说明 |
| --- | --- |
| `AED` | 阿联酋迪拉姆 |
| `AFA` | 阿富汗阿富汗尼 |
| `ALL` | 阿尔巴尼亚列克 |
| `AMD` | 亚美尼亚德拉姆 |
| `ANG` | 荷属安的列斯盾 |
| `AOA` | 安哥拉宽扎 |
| `ARS` | 阿根廷比索 |
| `AUD` | 澳大利亚元 |
| `AWG` | 阿鲁巴盾 |
| `AZM` | 阿塞拜疆马纳特 |
| `BAM` | 波黑可兑换马克 |
| `BBD` | 巴巴多斯元 |
| `BDT` | 孟加拉塔卡 |
| `BGN` | 保加利亚列弗 |
| `BHD` | 巴林第纳尔 |
| `BIF` | 布隆迪法郎 |
| `BMD` | 百慕大元 |
| `BND` | 文莱元 |
| `BOB` | 玻利维亚玻利瓦诺 |
| `BRL` | 巴西雷亚尔 |
| `BSD` | 巴哈马元 |
| `BTN` | 不丹努尔特鲁姆 |
| `BWP` | 博茨瓦纳普拉 |
| `BYR` | 白俄罗斯卢比 |
| `BZD` | 伯利兹元 |
| `CAD` | 加拿大元 |
| `CDF` | 刚果（金）法郎 |
| `CHF` | 瑞士法郎 |
| `CLP` | 智利比索 |
| `CNY` | 中国人民币 |
| `COP` | 哥伦比亚比索 |
| `CRC` | 哥斯达黎加克郎 |
| `CSD` | 塞尔维亚第纳尔 |
| `CUP` | 古巴比索 |
| `CVE` | 佛得角埃斯库多 |
| `CYP` | 塞浦路斯镑 |
| `CZK` | 捷克共和国克郎 |
| `DJF` | 吉布提法郎 |
| `DKK` | 丹麦克郎 |
| `DOP` | 多米尼加共和国比索 |
| `DZD` | 阿尔及利亚第纳尔 |
| `EEK` | 爱沙尼亚克伦尼 |
| `EGP` | 埃及镑 |
| `ERN` | 厄立特里亚 |
| `ETB` | 埃塞俄比亚比尔 |
| `EUR` | 欧元 |
| `FJD` | 斐济元 |
| `FKP` | 福克兰岛镑 |
| `GBP` | 英镑 |
| `GEL` | 格鲁吉亚拉里 |
| `GGP` | 根西岛镑 |
| `GHC` | 加纳塞地 |
| `GIP` | 直布罗陀镑 |
| `GMD` | 冈比亚达拉西 |
| `GNF` | 几内亚法郎 |
| `GTQ` | 危地马拉格查尔 |
| `GYD` | 圭亚那元 |
| `HKD` | 港元 |
| `HNL` | 洪都拉斯伦皮拉 |
| `HRK` | 克罗地亚库纳 |
| `HTG` | 海地古德 |
| `HUF` | 匈牙利福林 |
| `IDR` | 印度尼西亚卢比 |
| `ILS` | 以色列新舍客勒 |
| `IMP` | 马恩岛镑 |
| `INR` | 印度卢比 |
| `IQD` | 伊拉克第纳尔 |
| `IRR` | 伊朗里亚尔 |
| `ISK` | 冰岛克朗 |
| `JEP` | 泽西镑 |
| `JMD` | 牙买加元 |
| `JOD` | 约旦第纳尔 |
| `JPY` | 日元 |
| `KES` | 肯尼亚先令 |
| `KGS` | 吉尔吉斯索姆 |
| `KHR` | 柬埔寨瑞尔 |
| `KMF` | 科摩罗法郎 |
| `KPW` | 朝鲜圆 |
| `KRW` | 韩元 |
| `KWD` | 科威特第纳尔 |
| `KYD` | 开曼岛元 |
| `KZT` | 哈萨克坦吉 |
| `LAK` | 老挝基普 |
| `LBP` | 黎巴嫩镑 |
| `LKR` | 斯里兰卡卢比 |
| `LRD` | 利比里亚元 |
| `LSL` | 莱索托马洛蒂 |
| `LTL` | 立陶宛利泰 |
| `LVL` | 拉脱维亚拉图 |
| `LYD` | 利比亚第纳尔 |
| `MAD` | 摩洛哥迪拉姆 |
| `MDL` | 摩尔多瓦列伊 |
| `MGA` | 马达加斯加阿里亚里 |
| `MKD` | 马其顿代纳尔 |
| `MMK` | 缅甸元 |
| `MNT` | 蒙古图格里克 |
| `MOP` | 澳门元 |
| `MRO` | 毛里塔尼亚乌吉亚 |
| `MTL` | 马尔他里拉 |
| `MUR` | 毛里求斯卢比 |
| `MVR` | 马尔代夫卢非亚 |
| `MWK` | 马拉维克瓦查 |
| `MXN` | 墨西哥比索 |
| `MYR` | 马来西亚林吉特 |
| `MZM` | 莫桑比克梅蒂卡尔 |
| `NAD` | 纳米比亚元 |
| `NGN` | 尼日利亚奈拉 |
| `NIO` | 尼加拉瓜科多巴 |
| `NOK` | 挪威克郎 |
| `NPR` | 尼泊尔卢比 |
| `NZD` | 新西兰元 |
| `OMR` | 阿曼里亚尔 |
| `PAB` | 巴拿马巴波亚 |
| `PEN` | 秘鲁新索尔 |
| `PGK` | 巴布亚新几内亚基那 |
| `PHP` | 菲律宾比索 |
| `PKR` | 巴基斯坦卢比 |
| `PLN` | 波兰兹罗提 |
| `PYG` | 巴拉圭瓜拉尼 |
| `QAR` | 卡塔尔里亚尔 |
| `ROL` | 罗马尼亚列伊 |
| `RUR` | 俄罗斯卢比 |
| `RWF` | 卢旺达法郎 |
| `SAR` | 沙特阿拉伯里亚尔 |
| `SBD` | 所罗门群岛元 |
| `SCR` | 塞舌尔卢比 |
| `SDD` | 苏丹第纳尔 |
| `SEK` | 瑞典克朗 |
| `SGD` | 新加坡元 |
| `SHP` | 圣赫勒拿镑 |
| `SIT` | 斯洛文尼亚托拉尔 |
| `SKK` | 斯洛伐克克朗 |
| `SLL` | 塞拉利昂利昂 |
| `SOS` | 索马里先令 |
| `SPL` | 塞波加路易吉尼 |
| `SRD` | 苏里南元 |
| `SRG` | 苏里南盾 |
| `STD` | 圣多美和普林西比多布拉 |
| `SVC` | 萨尔瓦多科朗 |
| `SYP` | 叙利亚镑 |
| `SZL` | 斯威士兰埃马兰吉尼 |
| `THB` | 泰铢 |
| `TJS` | 塔吉克斯坦索莫尼 |
| `TMM` | 土库曼斯坦马纳特 |
| `TND` | 突尼斯第纳尔 |
| `TOP` | 汤加邦加 |
| `TRL` | 土耳其里拉 |
| `TTD` | 特立尼达和多巴哥元 |
| `TVD` | 图瓦卢元 |
| `TWD` | 台湾新台币 |
| `TZS` | 坦桑尼亚先令 |
| `UAH` | 乌克兰格里夫纳 |
| `UGX` | 乌干达先令 |
| `USD` | 美国美元 |
| `UYU` | 乌拉圭比索 |
| `UZS` | 乌孜别克斯坦苏姆 |
| `VEB` | 委内瑞拉玻利瓦尔 |
| `VND` | 越南盾 |
| `VUV` | 瓦努阿图瓦图 |
| `WST` | 萨摩亚塔拉 |
| `XAF` | 非洲金融共同体法郎 BEACO |
| `XAG` | 银盎司 |
| `XAU` | 黄金盎司 |
| `XCD` | 东加勒比元 |
| `XDR` | 国际货币基金组织特别提款权 |
| `XOF` | 非洲金融共同体法郎 BEACO |
| `XPD` | 钯金盎司 |
| `XPF` | 太平洋法郎 |
| `XPT` | 白金盎司 |
| `YER` | 也门里亚尔 |
| `ZAR` | 南非兰特 |
| `ZMK` | 赞比亚克瓦查 |
| `ZWD` | 津巴布韦元 |
