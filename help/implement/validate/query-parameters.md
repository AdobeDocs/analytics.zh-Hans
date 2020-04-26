---
title: 数据收集查询参数
description: 列出了图像请求中使用的所有查询字符串参数。
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# 数据收集查询参数

下表列出了 Adobe 在图像请求中使用的所有查询字符串参数。在以下情况下可使用此信息：使用[数据包分析程序](packet-monitor.md)进行调试时、[对图像请求进行硬编码时](../other/hardcoded.md)，或者当使用[动态变量](../vars/page-vars/dynamic-variables.md)时。

| 参数 | Analytics 实施变量 | 描述 |
| --- | --- | --- |
| `aamlh` | 无 | Audience Manager 位置提示。用于 Experience Cloud 共享配置文件集成。 |
| `aamb` | 无 | Audience Manager Blob。用于 Experience Cloud 共享配置文件集成。 |
| `aid` | 无 | Analytics 访客 ID。 |
| `AQB` | 无 | 指示图像请求查询字符串的开头。 |
| `AQE` | 无 | 指示图像请求的结尾，这表明该请求未被截断。 |
| `bh` | 无 | 浏览器高度（像素）。在“浏览器高度”维度中使用。 |
| `bw` | 无 | 浏览器宽度（像素）在“浏览器宽度”维度中使用。 |
| `c` | 无 | 颜色质量（位）在“颜色深度”维度中使用。 |
| `c.` | `contextData` | 指示上下文数据变量的开头。从不包含值。 |
| `.c` | `contextData` | 指示上下文数据变量的结尾。从不包含值。 |
| `c1` - `c75` | `prop1` - `prop75` | 自定义流量变量。 |
| `cc` | `currencyCode` | 点击中使用的货币类型。 |
| `cdp` | `cookieDomainPeriods` | 域中的句点数。用于帮助正确存储 Cookie。 |
| `ce` | `charSet` | 图像请求的字符编码。 |
| `cl` | `cookieLifetime` | 访客 Cookie 的生命周期。 |
| `ch` | `channel` | 在“网站区域”维度中使用。 |
| `cp` | 无 | 在“点击类型”维度中使用。 |
| `ct` | 无 | 在“连接类型”维度中使用。 |
| `D` | `dynamicVariablePrefix` | 指示要用作动态变量的参数。 |
| `ev` | `events` | `events` 查询字符串的简写形式。 |
| `events` | `events` | 以逗号分隔的页面事件列表。 |
| `g` | `pageURL` | 页面的当前 URL，最多 255 字节。 |
| `-g` | `pageURL` | 长度超过 255 字节的 URL 将被拆分。前 255 个字节显示在 `g` 参数中，其余所有字节都显示在 `-g` 参数中。 |
| `gn` | `pageName` | `pageName` 查询字符串的简写形式。 |
| `gt` | `pageType` | `pageType` 查询字符串的简写形式。 |
| `h1` - `h5` | `hier1` - `hier5` | 层次结构变量. |
| `hp` | 无 | 已不再使用。在早期版本的 Adobe Analytics 中，用于确定当前 URL 是否是浏览器的主页。 |
| `j` | 无 | 浏览器中安装的 JavaScript 版本。 |
| `k` | 无 | 在“Cookie 支持”维度中使用。 |
| `l1` - `l3` | `list1` - `list3` | 列表变量。 |
| `mid` | 无 | Experience Cloud 访客 ID。 |
| `ndh` | 无 | 指示图像请求是否来自 AppMeasurement 的标记。 |
| `ns` | `visitorNameSpace` | 帮助确定 Cookie 的设置位置。 |
| `oid` | `objectID` | 最后一页的对象标识符。在 Activity Map 中使用。 |
| `ot` | 无 | 最后一页的对象名称。在 Activity Map 早期版本中使用。 |
| `p` | 无 | 已不再使用。浏览器中使用的插件的列表。 |
| `pageName` | `pageName` | 在“页面”维度中使用。 |
| `pageType` | `pageType` | 在“找不到页面”维度中使用。 |
| `pccr` | 无 | 仅为新访客设置，并始终设置为 `true`。防止无限重定向。 |
| `pe` | `linkType` | 确定自定义链接的类型。 |
| `pev1` | 无 | 自定义链接的 URL。 |
| `pev2` | 无 | 自定义链接友好名称。 |
| `pev3` | 无 | 已不再使用。在早期版本的视频报告中，用于跟踪里程碑。 |
| `pf` | 无 | 平台标志；仅供 Adobe 使用。请勿更改。 |
| `pid` | 无 | 最后一页的页面标识符。在 Activity Map 早期版本中使用。 |
| `pidt` | 无 | 最后一页的页面标识符类型。在 Activity Map 早期版本中使用。 |
| `pl` | `products` | `products` 查询字符串的简写形式。 |
| `products` | `products` | 产品变量。 |
| `purchaseID` | `purchaseID` | 用于去除重复购买。 |
| `r` | `referrer` | 点击的反向链接 URL。 |
| `s` | 无 | 在“显示器分辨率”维度中使用。屏幕分辨率（以 `width x height` 为单位）。 |
| `server` | `server` | “服务器”维度。 |
| `sv` | `server` | `server` 查询字符串的简写形式。 |
| `state` | `state` | “状态”维度。 |
| `t` | 无 | 点击的生成日期/时间。采用 `dd/mm/yyyy hh:mm:ss w o` 格式。<br> - `dd/mm/yyyy hh:mm:ss` 是 JavaScript 中的日期/时间格式。月份 `0` 是指 1 月份，而月份 `11` 是指 12 月份。<br> - `w` 是一周中的第几天。`0` 表示星期日，而 `6` 表示星期六。<br> - `o` 是以分钟为单位的负 GMT 偏移。例如，`420` 表示 GMT-7。 |
| `ts` | `timestamp` | 为点击设置的自定义时间戳。通常用于离线跟踪。 |
| `v` | 无 | 在“已启用 Java”维度中使用。 |
| `v0` | `campaign` | “跟踪代码”维度。 |
| `v1` - `v250` | `evar1` - `eVar250` | 自定义转化维度。 |
| `vid` | `visitorID` | 访客 ID 变量。 |
| `vmk` | `vmk` | 已不再使用。帮助从第三方迁移到第一方 Cookie。 |
| `vvp` | `variableProvider` | 用于 Data Connectors。 |
| `xact` | `transactionID` | 与数据源一起使用，将数据链接在一起。 |
| `zip` | `zip` | 在“邮政编码”维度中使用。 |
