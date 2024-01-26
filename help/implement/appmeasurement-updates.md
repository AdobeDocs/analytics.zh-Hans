---
title: AppMeasurement for JavaScript 发行说明
description: AppMeasurement for JavaScript 的发行说明汇总。
feature: Appmeasurement Implementation
exl-id: 80b935f0-3ec5-4ffa-9858-f83ae9a6b763
role: Admin, Developer, Leader, User
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '2618'
ht-degree: 89%

---

# AppMeasurement for JavaScript 发行说明

AppMeasurement for JavaScript 的发行说明汇总。

<!-- https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log -->

您可以从以下位置下载最新版本的AppMeasurement： [GitHub](https://github.com/adobe/appmeasurement/releases).

## 版本 2.25.0

发行日期： **2023年9月12日**

* 添加了可选方法 [`bufferRequests()`](vars/functions/bufferrequests.md) 用于在浏览器不支持信标API或页面卸载时取消请求时提高捕获请求的可靠性。
* 添加了保护功能，以防止对单个跟踪请求进行多个跟踪后回调。

## 版本 2.24.0

发行日期： **2023年7月18日**

* 添加了可选配置变量 [`decodeLinkParameters`](vars/config-vars/decodelinkparameters.md) 用于对包含双字节编码字符的链接URL进行解码。
* 为具有错误的高熵用户代理客户端提示API的浏览器添加了其他错误处理。
* 更改了要使用的POST内容类型标头 `x-www-form-urlencoded` 默认情况下。

## 版本 2.23.0

发布日期：**2022 年 9 月 23 日**

* AppMeasurement 现在支持收集 Chromium 浏览器（Google Chrome 和 Microsoft Edge）用来提供设备信息的高熵用户代理客户端提示。您可以通过标记配置客户端提示或使用 [`collectHighEntropyUserAgentHints`](vars/config-vars/collecthighentropyuseragenthints.md) 配置变量。 默认情况下，将禁用高熵提示的收集。 详细了解 User-Agent [客户端提示](/help/technotes/client-hints.md)。

## 版本 2.22.4

发行日期：**2022 年 1 月 18 日**

* 链接跟踪调用 `s.tl()` 现在验证传递给它的对象是否包含 `string` 类型的 `href` 属性。如果它不是 `string`，则会正常地忽略 `href` 属性而不是失败。 当您通过时，可能会发生这种情况 `svg` 对象进行链接跟踪调用。

## 版本 2.22.3

发行日期：**2021 年 10 月 11 日**

* 更新了文件中指向文档的链接。

## 版本 2.22.2

发行日期：**2021 年 9 月 7 日**

* 此更新促使在跟踪链接时始终包含 `opt.dmp` 和 `opt.sell`。请参阅 [隐私报表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) 有关更多信息，请参阅管理员用户指南。

## 版本 2.22.1

发行日期：**2021 年 8 月 17 日**

* 使用选择退出的客户可能已发现在跟踪链接时未遵循服务器端转发选择退出参数。此版本中的修复会导致在跟踪链接时发送选择退出标志（如果有）。

## 版本 2.22.0

发行日期：**2020 年 8 月 4 日**

* 修复了由于用户选择退出偏好设置而未发送首次点击时缺少的反向链接。

## 版本 2.21.0

发行日期：**2020 年 6 月 24 日**

* 修复了 Activity Map linkExclusions 过滤器没有始终应用于 Firefox 的问题。

## 版本 2.20.0

发行日期：**2020 年 3 月 5 日**

* 通过更新 Internet Explorer 检测以禁止 JSLint 警告，修复了一个安全相关的问题。

## 版本 2.19.0

发行日期：**2020 年 2 月 21 日**

* 已将受众管理模块更新至 DIL 9.4。(AN-209341)

## 版本 2.18.0

发行日期：**2020 年 2 月 13 日**

* 现在，AppMeasurement 可以通过设置 [`writeSecureCookies`](vars/config-vars/writesecurecookies.md) 变量强制 Cookie 包含“安全”属性。此变量的要求是安全地服务于整个客户端网站 (HTTPS)。(AN-204604)

## 版本 2.17.0

发行日期：**2019 年 8 月 23 日**

* 增加了对百度查询字符串重新排序的支持。(AN-182483)
* 修复了导致等待选择加入时已排队点击中的访客值过期的问题。(AN-184391)

## 版本 2.16.0

发行日期：**2019 年 8 月 15 日**

* 在 [!UICONTROL AppMeasurement] 中针对退出链接实施了 `sendBeacon` 支持。如果点击使用 `sendBeacon` 并卸载页面，则仍然会完成请求。这对退出链接非常有用，因为点击很可能会到达数据收集服务器。(AN-175142)
* 即使 OptIn 设置发生更改，ECID/fid 值现在也会在首次点击时缓存。(AN-175142)
* 已将受众管理模块更新至 DIL 9.3。(AN-182704)
* 显示了 `s.ActivityMap.trackScrollReach` 中用于打开或关闭滚动覆盖范围跟踪的开关。(AN-182754)
* 升级了 AppMeasurement 以使用访客 ID 服务 4.4.0。(AN-182912)

## 版本 2.15.0

发行日期：**2019 年 7 月 15 日**

* 为 ActivityMap 扩展添加了 Activity Map 滚动范围跟踪 (AN-172949)
* 向 AppMeasurement 中添加了 DIL 9.2 (AN-182472)

## 版本 2.14.0

发行日期：**2019 年 5 月 21 日**

* 修复了当多个命中等待处理时，管理跟踪器参数状态的问题。(AN-176931、AN-176629、DTM-12758)
* 更新了 AppMeasurement 以包含 Visitor.js 4.3.0 (AN-180049)

## 版本 2.13.0

发行日期：**2019 年 4 月 10 日**

* 修复了很多报告的 clearVars 问题。在跟踪器准备就绪之前发送点击时，会出现问题。在跟踪器准备就绪时，库可以设置已被清除或更改的变量。(AN-176931、AN-176629、DTM-12758)

## 版本 2.12.0

发行日期：**2019 年 2 月 22 日**

* 已将受众管理模块更新至 DIL 9.1。(AN-175255)
* GTM 安全策略不允许使用 Activity Map 模块。(AN-174679)
* 改进了 AppMeasurement，支持当 Identity Service 未在“选择加入”中获得批准时选择退出。(AN-175259)

## 版本 2.11.0

发行日期：**2019 年 2 月 11 日**

* 在 AppMeasurement 中添加了对新的 Adobe“选择加入”服务功能的支持。(AN-163546)
* 添加了对在会话存储中存储链接跟踪数据的支持。(AN-162272)
* 为音频分析添加了对媒体流类型的支持。(AN-173265)

## 版本 2.10.0

发行日期：**2018 年 9 月 20 日**

此版本可确保 [!DNL AppMeasurement] 库为所有连接类型正确提交 Cookie。

* [!DNL AppMeasurement] 会在 POST 期间阻止 Cookie 传输。(AN-165538)
* 对 XDomainRequest 的拖放支持。(AN-165733)
* 将 [!DNL AppMeasurement] 默认 Cookie 生命周期从 5 年减少到 2 年。(AN-158572)
* 从“代码管理器”删除了“媒体模块”([!DNL AppMeasurement]) (AN-166590)

## 版本 2.9.0

发行日期：**2018 年 5 月 24 日**

>[!NOTE]
>
>使用 [!DNL Experience Cloud] ID 服务的客户需要安装访客 API 3.0 或更高版本。Adobe 建议，每当更新关联的代码库（[!DNL at.js] 等）时，请升级至访客 API 的最新版本。[!DNL AppMeasurement.js]

* 更新了 [!DNL AppMeasurement] 以使用更新的访客界面来获取请求 ID。(AN-151483)
* 修复了在关闭链接跟踪后，链接跟踪 Cookie 仍继续写入的问题。(AN-156332)
* 修复了 `registerPreTrackCallback` 和 `registerPostTrackCallback` 在调用多次后中断回调函数签名的问题。(AN-158566)

## 版本 2.8.2

发行日期：**2018 年 4 月 12 日**

* 更新 [!DNL AppMeasurement] 以使用更新的访客界面来获取请求 ID。(AN-151483)
* 关闭链接跟踪后，链接跟踪 Cookie 将继续写入。(AN-156332)
* 将 [!DNL AppMeasurement] 默认 Cookie 生命周期从 5 年减少到 2 年。(AN-158572)

## 版本 2.8.1

发行日期：**2018 年 3 月 29 日**

重新捆绑 Visitor API 3.1.0 (AN-159524)，该版本包含热修复程序：（CORE-11390、CORE-10634）

## 版本 2.8.0

发行日期：**2018 年 3 月 15 日**

重新捆绑 Visitor API 3.1.0 (AN-159524)，该版本包含热修复程序：（CORE-11390、CORE-10634）

* 将 VAPI 版本 3.1 与 [!DNL AppMeasurement] 版本 2.8 捆绑在一起。(AN-158353)
* 重新构建数据收集端点以方便共享。(AN-156647)
* 将请求往返计时量度添加到 [!DNL AppMeasurement]。(AN-158343)

## 版本 2.7.0

发行日期：**2018 年 1 月 18 日**

* 不再支持 IE 6 至 9
* 包括访客 API 3.0.0 版
* 包括 DIL 7.00 版

## 版本 2.6.0

发行日期：**2017 年 11 月 9 日**

修复在调用 s_gl 时 [!DNL AppMeasurement] 库并非总是设置正确的帐户组合的问题。(AN-152153)

## 版本 2.5.0

发行日期：**2017 年 9 月 21 日**

* 添加了 [!DNL dil.js 6.12]（[!DNL Audience Manager] 模块）
* 添加了 Visitor API 2.5.0。

## 版本 2.4.0

发行日期：**2017 年 8 月 17 日**

* 包含 dil.js v6.11
* 包含 Visitor API 2.4.0

## 版本 2.3.0

发行日期：**2017 年 7 月 20 日**

* 修复了 `s.Util.getQueryParam` 捕获 `#` 的错误
* 添加了 6.10 版的 `dil.js` (AN-145701)

## 版本 2.2.0

发布日期：**2017 年 6 月 8 日**

* 添加了对多个 [!DNL AppMeasurement] 实例化订单的支持。(AN-138237)
* 包括 Visitor API 版本 2.2.0。(AN-144042)

## 版本 2.1.0

发行日期：**2017 年 4 月 20 日**

* 包含最新版本的 `dil.js` (AN-140396)
* 为覆盖页面引荐的 `adobe_mc_ref` 参数添加支持。(AN-131920)
* 重新包含 Visitor API 2.1.0。(AN-140873)
* 添加了 `mcorgid` 参数。(AN-139586)
* 添加 cp (customerPerspective) 参数。(AN-140897)

## 版本 2.0.0

发行日期：**2017 年 3 月 9 日**

* 已移动到需要将版本号更新为 2.0.0 的新生成流程。(AN-137878)
* 已将 mboxMCSDID 处理移动到执行跟踪调用的正确区域位置。(AN-138483)

## 版本 1.8.0

发行日期：**2017 年 1 月 19 日**

* 包含 Visitor API 2.0.0
* 重新排序了功能调用和检查，确保在完成中止检查后使用 SDID。(AN-134364)
* 添加了 `s.registerPreTrackCallback` 和 `s.registerPostTrackCallback` 挂钩。(AN-134567)

## 版本 1.7.0

更新日期：**2016 年 11 月 11 日**

* 包含 Visitor API 1.10.1.
* 使用 Demdex Integration Library (DIL) 6.6 更新 [!DNL Audience Manager] 模块。(AN-132065)
* 包括 Visitor API 1.9.0。(AN-132072)
* 通过 DIL 6.5 和额外配置更新 [!DNL AppMeasurement] [!DNL Audience Manager] 模块 (AN-129411)
* 包括 Visitor API 1.8.0 (AN-129887)

## 版本 1.6.4

更新日期：**2016 年 8 月 18 日**

* 更新了 [!DNL AppMeasurement] 以读写 AMCV cookie。(AN-127098)
* 包括 Visitor API 1.7.0。

>[!NOTE]
>
>另请参阅下面的 [!DNL JavaScript] 版本 1.6.3 发行说明，其中包括 Marketing Cloud ID 服务的更新要求。

## 版本 1.6.3

更新日期：**2016 年 8 月 4 日**

* 修复了 [!DNL AppMeasurement] 过早终止请求连接的问题。(AN-126448)

>[!IMPORTANT]
>
>版本 1.6.0 的 [!DNL Experience Cloud] ID 服务&#x200B;*要求* [!DNL AppMeasurement] for [!DNL JavaScript] 版本 1.6.3 或更高版本。如果您要升级到版本 1.6.0 的 Experience Cloud ID 服务，请确保您使用的是 AppMeasurement 1.6.3 或更高版本。

## 版本 1.6.2

发行日期：**2016 年 7 月 21 日**

* 包括 Visitor API 1.6.0。
* 修复了导致 [!DNL AppMeasurement] 在访客 API 中调用错误的模糊处理方法的问题。(AN-126006)
* 修复了导致 [!DNL JavaScript] 错误：“属性仅在 v:image 上有效”的问题。(AN-124009)

## 版本 1.6.1

发布日期：**2016 年 6 月 16 日**

* 包括 Visitor API 1.5.7。
* 修复了在 Firefox 中处理链接点击次数跟踪时无法触发完整事件的问题。

## 版本 1.6

发行日期：**2016 年 4 月 21 日**

* [!DNL AppMeasurement] Activity Map 模块已集成在 [!DNL AppMeasurement] 标准模块中，因此，您只需引用一个 [!DNL .js] 文件。此外，默认情况下会激活 Activity Map 跟踪。(AN-112689)
* 修复了 [!DNL AppMeasurement] 中的查询字符串变量顺序存在的截断问题，以便 *`pageURLRest`* 位于最后。(AN-114647)

## 版本 1.5.4

发行日期：**2016 年 3 月 17 日**

* 包括 Visitor API 1.5.4
* 支持 Visitor API 1.5.4+ 选择退出

## 版本 1.5.3

发行日期：**2016 年 1 月 21 日**

* 修复了在 POST 用于跟踪调用时对 [!DNL Audience Manager] 模块的处理。(AN-115381)
* 将页面 URL 的其余部分（“-g”）移到跟踪请求查询字符串的末尾。(AN-114647)

## 版本 1.5.2

发行日期：**2015 年 11 月 5 日**

* 包括 Visitor API 1.5.3。
* 修复了 URL 截断 2047 的 IE11 检测 (AN-114914)

## 版本 1.5.1

发行日期：**2015 年 9 月 17 日**

* 包括 Visitor API 1.5.2
* 已更新 [!DNL Audience Manager] 模块以使用Adobe Audience ManagerDIL6.2 — 从VisitorAPI.js获取Customer ID，并在事件调用中将它们传递到Adobe Audience Manager。 (AN-104978)

## 版本 1.5

发行日期：**2015 年 6 月 18 日**

* 支持访客 API 1.5，它使用 *`getCustomerIDs`* 方法收集客户 ID 和已验证的状态，并通过数据收集请求发送 ID。
* 修复了在 **[!UICONTROL AudienceManagement]** 模块 (DIL 6.1) 中创建重复的目标 iframe 的问题。
* 修复了 1.4.5 版中描述的已知问题。

## 版本 1.4.5

发行日期：**2015 年 5 月 21 日**

* 从iOS SDK 4.5版开始，新增的iOS扩展允许您从Apple Watch应用程序、“今天”小组件、照片编辑小组件和所有其他iOS扩展应用程序中收集使用数据。
* 从Android SDK 4.5版开始，新增的Android扩展允许您从Android可穿戴应用程序中收集数据。
* 包括 Visitor API 1.4。
* 更新了 AudienceManagement 模块，以便使用 DIL 版本 6.0。

>[!NOTE]
>
>**已知问题**：在访客 API/[!DNL AppMeasurement] [!DNL Audience Manager] 模块集成中，将有两个在 IE6-9 中发出的目标发布 iFrame 请求：`//fast.<subdomain>.demdex.net/dest5.html` 和 `//fast.<subdomain>.demdex.net/dest4.html`。如在其他浏览器中所看到的，正确的行为是仅加载 `//fast.<subdomain>.demdex.net/dest5.html`。

## 版本 1.4.4

发行日期：**2015 年 4 月 16 日**

* 您现在可以包含具有生命周期量度的自定义上下文数据变量。
* 现在，`trackBeacon` 和 `clearCurrentBeacon` 调用在 PhoneGap 中可用。
* 进行了小修复，以便在 `trackLight` 调用之后清除轻量级服务器调用配置文件 ID。

## 版本 1.4.3

发行日期：**2015 年 2 月 19 日**

* 保持所有延迟跟踪调用的处理连贯一致，这可以修复延迟期间已备份变量（例如，已单击的对象）的问题。
* 首次跟踪调用后更改为不执行自动反向链接跟踪，以便第2次、第3次（依此类推）跟踪调用（通常为链接跟踪）在以下情况下不会将反向链接计算两次： *`s.referrer`* 于首次跟踪调用之前被手动设置时，不会将反向链接计算两次。
* 更新了分发 zip 文件以包括 Visitor API 1.3.5。

## 版本 1.4.2

发行日期：**2015 年 1 月 15 日**

* 修复了 WebKit 预渲染处理阻止跟踪未查看的预渲染页面的问题。
* 更新了分发 zip 文件以包括 Visitor API 1.3.4 和更新的 **[!UICONTROL AudienceManagement]** 模块（包括 DIL 版本 5.5）。

## 版本 1.4.1

发行日期：**2014 年 9 月 18 日**

* 增加了 `tagContainerMarker` 变量，该变量允许实施指定最多 4 个字符和一个附加短划线字符分界符一起附加在版本字符串的后面。这被用于动态标签管理。

  ```js
  // JavaScript
  s.tagContainerMarker = "D1.0";
  
  // Data Collection request
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
  ```

  这 4 个字符仅限于在 URL 文件路径中允许使用的字符，例如字母数字和句点。

* 在具有双标签和 H 代码的页面上，修复了在启用强制链接跟踪（在 Webkit 浏览器中默认启用）时在自动链接跟踪过程中（下载和退出）可能出现的循环。此外，在自动链接跟踪过程中增加了一般防护措施，防止出现相同的循环。该防护措施将&#x200B;*相同*&#x200B;对象的重复单击的自动链接跟踪频率限制为每 10 秒钟一次。该防护措施仅适用于自动链接跟踪，因此手动链接跟踪 (s.tl) 调用不受限制。另外，单击不同的对象不受该防护措施的影响，将会对此进行跟踪。
* 修复了需要延迟时处理单击的对象的问题。
* 修复了如果访客 API 尚未具有所需的值，从链接 onclick 函数调用 s.t 时导致双页面视图计数的问题。
* HTTP POST 支持。

  >[!IMPORTANT]
  >
  > 对于在 [!DNL Analytics] 中使用 POST 方法而不是 GET 方法（一种用于解决 [!DNL AppMeasurement]IE 中的截断 URL[ 的方法）的 ](https://helpx.adobe.com/cn/analytics/kb/shortening-image-request-urls.html) 调用，您必须对 Experience Cloud 使用最新的访客 ID 服务实施。

## 版本 1.4

发行日期：**2014 年 8 月 21 日**

* 已删除对浏览器插件的跟踪（`p` 查询参数），因为这些插件在版本 15 中不再报告。
* 下载 zip 文件中添加了 **[!UICONTROL AudienceManagement]** 模块。
* 添加了对其他 eVar (76-250) 和事件 (101-1000) 的支持。

>[!NOTE]
>
>H 代码不支持这些附加的 eVar 和事件。

## 版本 1.3.2

发行日期：**2014 年 6 月 19 日**

* 修复了在处理访客 API 字段（例如，原有 [!DNL Analytics] 访客 ID）的已完成和正在等待标记时，会产生错误的问题。
* 支持访客 ID 服务 1.3 中的新增功能。

## 版本 1.3.1

发行日期：**2014 年 5 月 22 日**

* [!DNL AppMeasurement] for [!DNL JavaScript]`s_gi` 函数无法正确查找使用 H 代码 `s_gi` 创建的实例。请注意，该问题仅会影响一些双标记实施，在这些实施中，[!DNL AppMeasurement] for [!DNL JavaScript] 和 H 代码位于同一页面上，但却在单独实例中，而且 `s_gi` 被报告包用来查找实例。

## 版本 1.3

发行日期：**2014 年 4 月 17 日**

* 支持 [Experience Cloud 访客 ID 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。

## 版本 1.2.4

发行日期：**2014 年 3 月 13 日**

* 心率视频的错误修复。

## 版本 1.2.3

发行日期：**2014 年 2 月 20 日**

* 心率视频的错误修复。

## 版本 1.2.2

发行日期：**2014 年 2 月 6 日**

* 修复了 [!DNL Audience Manager] DIL 模块存在的兼容性问题。[!DNL Audience Manager] 客户还必须更新到 4.8 版本的 DIL 模块。

## 版本 1.2.1

发行日期：**2013 年 11 月 15 日**

* 修复了用于心率视频测量的页面事件。

## 版本 1.2

发行日期：**2013 年 11 月 14 日**

* 添加了对[心率视频测量](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hans)的支持。
* 添加了 `VisitorAPI.js` 以支持[访客 ID 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。

## 版本 1.1.1

* 对于以“opera:”开始的链接，链接跟踪调用不能从 Opera 浏览器发送（“opera:”类似于其他浏览器中的“about:”和“chrome:”）。
* 向所有图像对象增加了 `alt=""` 以遵守通信和视频接入法案。

## 版本 1.1

发行日期：**2013 年 9 月 18 日**

* 修复了对在 `head` 标签中置入库和页面代码的支持。
* 添加了缺失的模块 `onLoad` 支持。

## 版本 1.0.3

发行日期：**2013 年 8 月 15 日**

* 增加了对通过 Adobe 标签管理进行部署的支持。
* 修复了阻止层次结构变量在 [!DNL AppMeasurement] 对象上设置的问题。

## 版本 1.0.2

发行日期：**2013 年 7 月 18 日**

* 散列/片段现在被自动链接跟踪忽略。此前由于整个 `href` 以 `.pdf` 结束，因此自动对下面的 URL 进行了跟踪：

  ```js
  <a href="index.htm#anchor.pdf">Test Link</a>
  ```

  现在散列/片段被忽略，因此，只有当文件名以匹配的扩展名结束时，才会跟踪该链接。

## 版本 1.0.1

发行日期：**2013 年 5 月 23 日**

代码管理器目前提供了新的 [!DNL JavaScript] [!DNL AppMeasurement] 库。此库提供了与 [!DNL s_code.js] 相同的核心功能，但它更轻快，更适合在移动网站和桌面网站上使用。

* 比 H.25 代码快 3 至 7 倍。
* 未压缩时仅为 21k，压缩后为 8k（H.25 代码未压缩时为 33k，压缩后为 13k）。
* 本地支持获取查询参数、读取 cookie，以及执行高级链接跟踪。
* 小巧、快速的特点非常适合用于移动网站，而强健的功能又适合在完整的桌面网站上使用，从而使您可以在所有 Web 环境中使用单个库。
