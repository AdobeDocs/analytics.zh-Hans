---
description: 在不使用 JavaScript 的情况下部署 Analytics 时还有其他的要求和配置。
keywords: Analytics 实施;区分大小写;编码查询参数;无效字符;安全图像请求;最大变量长度;反向链接;URL;缓存;命名空间
seo-description: 在不使用 JavaScript 的情况下部署 Analytics 时还有其他的要求和配置。
seo-title: 不使用 JavaScript 指南进行实施
solution: Analytics
title: 不使用 JavaScript 指南进行实施
topic: 开发人员和实施
uuid: c672dd63-1c74-4f66-8992-9257c5a75e36
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 不使用 JavaScript 指南进行实施

在不使用 JavaScript 的情况下部署 Analytics 时还有其他的要求和配置。

您可以查看示例代码以进一步了解实施。以下信息简要介绍了其他要求和配置：

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**区分大小写**

参数名称（`pageName`、`purchaseID` 等）区分大小写，且不会正确记录数据，除非它们按[查询参数](../../../implement/js-implementation/data-collection/query-parameters.md)中的表中所指定的方式显示。

**编码查询参数**

每个查询字符串参数的值必须经过 URL 编码。URL 编码将查询字符串中出现的非法字符（如空格字符）转化为以 `%` 开头的编码字符。例如，空格字符会被转化为 `%20`.

此功能的 JavaScript 版称为转义（解码称为取消转义）。Microsoft IIS 版本 5.0 也包括用于编码查询字符串的转义和取消转义功能。其他 Web 服务器脚本语言也提供了编码/解码工具。

**最大变量长度**

每个变量都有一个最大长度。应为 [Analytics 变量](../../../implement/js-implementation/c-variables/sc-variables.md). 如果超出变量的最大长度，则在 Analytics 中存储和显示时，会导致该变量的值被截断。

**无效字符**

字符代码高于十进制 128 的字符无效，因为非打印字符代码低于 128。HTML 格式设置（“&lt;h1&gt;”）也无效，因为它们是商标、注册商标和版权符号。

**安全 (&lt;https:&gt;) 与非安全 (&lt;http:&gt;) 图像请求**

在通过 https（安全协议）访问的页面上，图像请求的 URL 部分发生了更改，以适应数据收集服务器的不同设置。

下面信息说明了用于安全和非安全图像请求的不同 URL。

* 上述 URL 中的 `*` 表示数据中心特定的 URL，由 Adobe 顾问提供给您。Adobe 使用多个数据中心，必须实施为贵组织分配的正确 URL。使用管理控制台通过公司帐户下载的任何代码都自动提供了正确的数据中心。外部来源提供的代码可能需要进行更正才能指向正确的数据中心。
* 对于使用多个报表包的客户，报表包仅列在目录部分，而不是 URL 的域名部分，如下所示。
* 上述 URL 中的 `*` 表示数据中心特定的 URL，由 Adobe 顾问提供给您。Adobe 使用多个数据中心，必须实施为贵组织分配的正确 URL。

**URL 和反向链接 URL**

可以从服务器的 `g=` 和 `r=` 变量中填充 URL 和反向链接 URL。请使用请求 ServerVariables (`HTTP\_REFERRER`)、请求 ServerVariables `(URL) (IIS/ASP)` 或您服务器/脚本技术的相应变量。反向链接 URL `( r=)` 对于跟踪反向链接 URL、域、搜索引擎和搜索词非常重要。

如果未使用 pageName，则必须唯一填充当前 URL 字段。如果既未填充 pageName，又未填充当前 URL `(g=)`，则该记录无效，不会进行处理。要处理记录，至少需要填充 URL 字段。

**缓存影响**

浏览器或访客与提供内容的网站之间的服务器可能会缓存 HTML 和其他网页。除非采用“cache-busting”技术，否则缓存会导致页面查看次数和其他事件计数不准确。

Adobe 的标准 JavaScript 包括一个动态更改图像请求的方法，可避免页面和图形缓存，得到准确的页面查看计数。

但在创建服务器端图像请求时，不会发生这种随机处理。在使用服务器端图像请求时，在某些情况下不会计算页面重新载入和缓存的页面（浏览器缓存中或代理服务器中）。

按照定义不会缓存 SSL (`https:`) 页面，因而此警告仅适用于非安全 (`http:`) 页面。此外，具有参数 (`https://www.samplesite.com/page.asp?parameter=1`) 的页面或使用特定文件扩展名（`.asp`、`.jsp`、等等）的页面也不会进行缓存。

下面的示例还列举了一个极小的 JavaScript 解决方案，它主要收集服务器端的图像请求，并跟踪浏览器中的随机数。此方法克服了在通过 https: 协议访问的静态 HTML 页面上遇到的缓存问题。

**nameSpace 变量**

非 JavaScript 实施需要使用 nameSpace 查询字符串参数。

示例：ns=nameSpace

请联系 Adobe 顾问或客户经理以获取贵组织的 nameSpace 值。
