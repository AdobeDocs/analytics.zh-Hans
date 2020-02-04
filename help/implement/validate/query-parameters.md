---
title: 数据收集查询参数
description: 列出图像请求中使用的所有查询字符串参数。
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# 数据收集查询参数

下表列出了Adobe在图像请求中使用的所有查询字符串参数。 在使用包分析器进行调试时、在硬编码图 [像请求时或在使用动态变量时](packet-monitor.md)，都可以使用此信息 [](../other/hardcoded.md)[](../vars/page-vars/dynamic-variables.md)。

| 参数 | 分析实施变量 | 描述 |
| --- | --- | --- |
| `aamlh` | 无 | Audience manager位置提示。用于Experience Cloud共享配置文件集成。 |
| `aamb` | 无 | Audience Manager Blob。用于Experience Cloud共享配置文件集成。 |
| `aid` | 无 | Analytics 访客 ID. |
| `AQB` | 无 | 指示图像请求查询字符串的开头。 |
| `AQE` | 无 | 指示图像请求的结束，这意味着该请求没有被截断。 |
| `bh` | 无 | 浏览器高度（以像素为单位）。 用于浏览器高度维。 |
| `bw` | 无 | 浏览器宽度（以像素为单位）。 用于浏览器宽度尺寸。 |
| `c` | 无 | 颜色质量（以位为单位）。 用于“颜色深度”尺寸。 |
| `c.` | `contextData` | 指示上下文数据变量的开头。 从不包含值。 |
| `.c` | `contextData` | 指示上下文数据变量的结尾。 从不包含值。 |
| `c1` - `c75` | `prop1` - `prop75` | 自定义流量变量. |
| `cc` | `currencyCode` | 点击中使用的货币类型。 |
| `cdp` | `cookieDomainPeriods` | 域中的句点数。 用于帮助正确存储Cookie。 |
| `ce` | `charSet` | 图像请求的字符编码. |
| `cl` | `cookieLifetime` | 访客 Cookie 的生命周期。 |
| `ch` | `channel` | 在“站点区域”维中使用。 |
| `cp` | 无 | 在“命中类型”维中使用。 |
| `ct` | 无 | 用于连接类型维。 |
| `D` | `dynamicVariablePrefix` | 表示动态变量的用途。 |
| `ev` | `events` | 查询字符串 `events` 的短记。 |
| `events` | `events` | 页面上事件列表，以逗号分隔。 |
| `g` | `pageURL` | 页面的当前 URL，最多 255 字节。 |
| `-g` | `pageURL` | 大于255字节的URL被拆分。 前255个字节显示在参数 `g` 中，其余所有字节都显示在参数 `-g` 中。 |
| `gn` | `pageName` | 查询字符串 `pageName` 的短记。 |
| `gt` | `pageType` | 查询字符串 `pageType` 的短记。 |
| `h1` - `h5` | `hier1` - `hier5` | 层次结构变量. |
| `hp` | 无 | 已不再使用。在Adobe Analytics的先前版本中，确定当前URL是否是浏览器的主页。 |
| `j` | 无 | 浏览器中安装的JavaScript版本。 |
| `k` | 无 | 用于Cookie支持维。 |
| `l1` - `l3` | `list1` - `list3` | 列出变量。 |
| `mid` | 无 | Experience cloud访客ID。 |
| `ndh` | 无 | 指示图像请求是否来自AppMeasurement的标记。 |
| `ns` | `visitorNameSpace` | 帮助确定设置Cookie的位置。 |
| `oid` | `objectID` | 最后一页的对象标识符。 在Activity map中使用。 |
| `ot` | 无 | 最后一页的对象名称。 在Activity map的早期版本中使用。 |
| `p` | 无 | 已不再使用。浏览器中使用的插件列表。 |
| `pageName` | `pageName` | 用于页面维。 |
| `pageType` | `pageType` | 在“找不到页面”维中使用。 |
| `pccr` | 无 | 仅为新访客设置，始终设置为 `true`。 防止无限重定向。 |
| `pe` | `linkType` | 确定自定义链接的类型。 |
| `pev1` | 无 | 发生自定义链接的URL。 |
| `pev2` | 无 | 自定义链接易记名称. |
| `pev3` | 无 | 已不再使用。跟踪视频报告先前版本中的里程碑。 |
| `pf` | 无 | 平台标志；仅供Adobe使用。 请勿更改。 |
| `pid` | 无 | 最后一页的页面标识符。 在Activity map的早期版本中使用。 |
| `pidt` | 无 | 最后一页的页面标识符类型。 在Activity map的早期版本中使用。 |
| `pl` | `products` | 查询字符串 `products` 的短记。 |
| `products` | `products` | 产品变量. |
| `purchaseID` | `purchaseID` | 用于消除重复购买。 |
| `r` | `referrer` | 点击的引用URL。 |
| `s` | 无 | 用于“监视器分辨率”维。 屏幕分辨率，以 `width x height`下： |
| `server` | `server` | 服务器维度。 |
| `sv` | `server` | 查询字符串 `server` 的短记。 |
| `state` | `state` | 状态维。 |
| `t` | 无 | 点击的生成日期／时间。 使用格式 `dd/mm/yyyy hh:mm:ss w o`。<br>- `dd/mm/yyyy hh:mm:ss` is date/time in JavaScript. 月份 `0` 是1月份，月份是 `11` 12月份。<br>- `w` 是每周的某天。 `0` 周日，周 `6` 六。<br>-是 `o` 以分钟为单位的负GMT偏移。 例如， `420` 是GMT-7。 |
| `ts` | `timestamp` | 使用点击设置的自定义时间戳。 通常用于离线跟踪。 |
| `v` | 无 | 用于“启用Java”维。 |
| `v0` | `campaign` | 跟踪代码维。 |
| `v1` - `v250` | `evar1` - `eVar250` | 自定义转换维度。 |
| `vid` | `visitorID` | 访客 ID 变量. |
| `vmk` | `vmk` | 已不再使用。帮助从第三方迁移到第一方Cookie。 |
| `vvp` | `variableProvider` | 用于数据连接器。 |
| `xact` | `transactionID` | 与数据源一起使用，将数据链接在一起。 |
| `zip` | `zip` | 用于邮政编码维度。 |
