---
title: AppMeasurement for JavaScript 发行说明
description: AppMeasurement for JavaScript 的发行说明汇总。
feature: Appmeasurement Implementation
exl-id: 80b935f0-3ec5-4ffa-9858-f83ae9a6b763
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/iszRZIB8QN3ihEcNWcOHyO1rVGMuKpt6YTkrquuKfWs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 2885
ht-degree: 53%

---

# AppMeasurement for JavaScript 发行说明

>[!IMPORTANT]
>
>自2025年3月起，将不再更新本文。 您可以从[GitHub](https://github.com/adobe/appmeasurement/releases)查看并下载最新版本的AppMeasurement的发行说明。


## 版本 2.27.0

发行日期：**2024年8月12日**

* 如果已启用`writeSecureCookies`，则现在使用`secure`标志写入`s_ac` Cookie。
* 修复了嵌入式库时的初始化错误。
* 修复了`localStorage`或`sessionStorage`被禁用的错误。
* 如果已启用`collectHighEntropyUserAgentHints`，则链接跟踪调用(`tl`)现在包含高熵用户代理提示。

## 版本 2.26.0

发行日期：**2024年3月4日**

* AppMeasurement会自动识别并利用国家/地区代码顶级域的根域，以前需要特定Cookie域配置。 由于这种自动识别，更新可能会产生影响。 有关详细信息，请参阅[`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md)。
* 该分发版本包括Identity Service Library 5.5.0和Data Integration Library 9.6。

## 版本 2.25.0

发行日期：**2023年9月12日**

* 添加了可选方法[`bufferRequests()`](vars/functions/bufferrequests.md)，以便在浏览器不支持信标API或页面卸载时取消请求时提高捕获请求的可靠性。
* 添加了保护功能，以防止对单个跟踪请求进行多个跟踪后回调。

## 版本 2.24.0

发行日期：**2023年7月18日**

* 添加了可选配置变量[`decodeLinkParameters`](vars/config-vars/decodelinkparameters.md)，用于对包含双字节编码字符的链接URL进行解码。
* 为具有错误的高熵用户代理客户端提示API的浏览器添加了其他错误处理。
* 更改了POST Content-Type标头，默认使用`x-www-form-urlencoded`。

## 版本 2.23.0

发布日期：**2022 年 9 月 23 日**

* AppMeasurement 现在支持收集 Chromium 浏览器（Google Chrome 和 Microsoft Edge）用来提供设备信息的高熵用户代理客户端提示。 您可以通过Tags配置客户端提示或使用[`collectHighEntropyUserAgentHints`](vars/config-vars/collecthighentropyuseragenthints.md)配置变量。 默认情况下，将禁用高熵提示的收集。 详细了解 User-Agent [客户端提示](/help/technotes/client-hints.md)。

## 版本 2.22.4

发行日期：**2022 年 1 月 18 日**

* 链接跟踪调用 `s.tl()` 现在验证传递给它的对象是否包含 `string` 类型的 `href` 属性。 如果它不是`string`，则它将正常地忽略`href`特性而不是失败。 当您将`svg`对象传递给链接跟踪调用时，可能会发生这种情况。

## 版本 2.22.3

发行日期：**2021 年 10 月 11 日**

* 更新了文件中指向文档的链接。

## 版本 2.22.2

发行日期：**2021 年 9 月 7 日**

* 此更新促使在跟踪链接时始终包含 `opt.dmp` 和 `opt.sell`。 有关详细信息，请参阅管理员用户指南中的[隐私报表](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md)。

## 版本 2.22.1

发行日期：**2021 年 8 月 17 日**

* 使用选择退出的客户可能已发现在跟踪链接时未遵循服务器端转发选择退出参数。 此版本中的修复会导致在跟踪链接时发送选择退出标志（如果有）。

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

* 已将受众管理模块更新至 DIL 9.4。 (AN-209341)

## 版本 2.18.0

发行日期：**2020 年 2 月 13 日**

* 现在，AppMeasurement 可以通过设置 [`writeSecureCookies`](vars/config-vars/writesecurecookies.md) 变量强制 Cookie 包含“安全”属性。 此变量的要求是安全地服务于整个客户端网站 (HTTPS)。 (AN-204604)

## 版本 2.17.0

发行日期：**2019 年 8 月 23 日**

* 增加了对百度查询字符串重新排序的支持。 (AN-182483)
* 修复了导致等待选择加入时已排队点击中的访客值过期的问题。 (AN-184391)

## 版本 2.16.0

发行日期：**2019 年 8 月 15 日**

* 在 [!UICONTROL AppMeasurement] 中针对退出链接实施了 `sendBeacon` 支持。 如果点击使用 `sendBeacon` 并卸载页面，则仍然会完成请求。 这对退出链接非常有用，因为点击很可能会到达数据收集服务器。 (AN-175142)
* 即使 OptIn 设置发生更改，ECID/fid 值现在也会在首次点击时缓存。 (AN-175142)
* 已将受众管理模块更新至 DIL 9.3。 (AN-182704)
* 显示了 `s.ActivityMap.trackScrollReach` 中用于打开或关闭滚动覆盖范围跟踪的开关。 (AN-182754)
* 升级了 AppMeasurement 以使用访客 ID 服务 4.4.0。 (AN-182912)

## 版本 2.15.0

发行日期：**2019 年 7 月 15 日**

* 为 ActivityMap 扩展添加了 Activity Map 滚动范围跟踪 (AN-172949)
* 向 AppMeasurement 中添加了 DIL 9.2 (AN-182472)

## 版本 2.14.0

发行日期：**2019 年 5 月 21 日**

* 修复了当多个命中等待处理时，管理跟踪器参数状态的问题。 (AN-176931、AN-176629、DTM-12758)
* 更新了 AppMeasurement 以包含 Visitor.js 4.3.0 (AN-180049)

## 版本 2.13.0

发行日期：**2019 年 4 月 10 日**

* 修复了很多报告的 clearVars 问题。 在跟踪器准备就绪之前发送点击时，会出现问题。 在跟踪器准备就绪时，库可以设置已被清除或更改的变量。 (AN-176931、AN-176629、DTM-12758)

## 版本 2.12.0

发行日期：**2019 年 2 月 22 日**

* 已将受众管理模块更新至 DIL 9.1。 (AN-175255)
* GTM安全策略不允许Activity Map模块。 (AN-174679)
* 改进了 AppMeasurement，支持未在“选择加入”中身份标识服务时选择退出。 (AN-175259)

## 版本 2.11.0

发行日期：**2019 年 2 月 11 日**

* 在 AppMeasurement 中添加了对新的 Adobe“选择加入”服务功能的支持。 (AN-163546)
* 添加了对在会话存储上存储链接跟踪数据的支持。 (AN-162272)
* 为音频分析添加了对媒体流类型的支持。 (AN-173265)

## 版本 2.10.0

发行日期：**2018 年 9 月 20 日**

此版本可确保AppMeasurement库为所有连接类型正确提交Cookie。

* AppMeasurement会在POST期间阻止Cookie传输。 (AN-165538)
* 删除对XDomainRequest的支持。 (AN-165733)
* 将AppMeasurement默认Cookie生命周期从5年减少到2年。 (AN-158572)
* 从代码管理器中删除“媒体模块”( AppMeasurement) (AN-166590)

## 版本 2.9.0

发行日期：**2018 年 5 月 24 日**

>[!NOTE]
>
>使用Experience Cloud ID服务的客户需要安装访客API 3.0或更高版本。 Adobe 建议，每当更新关联的代码库（`at.js` 等）时，请升级至访客 API 的最新版本。`AppMeasurement.js`

* 更新了AppMeasurement以使用更新的访客界面来获取请求ID。 (AN-151483)
* 修复了在关闭链接跟踪后链接跟踪Cookie不断被写入的问题。 (AN-156332)
* 修复了 `registerPreTrackCallback` 和 `registerPostTrackCallback` 在调用多次后中断回调函数签名的问题。 (AN-158566)

## 版本 2.8.2

发行日期：**2018 年 4 月 12 日**

* 更新AppMeasurement以使用更新的访客界面来获取请求ID。 (AN-151483)
* 一旦链接跟踪关闭，链接跟踪Cookie会不断被写入。 (AN-156332)
* 将AppMeasurement默认Cookie生命周期从5年减少到2年。 (AN-158572)

## 版本 2.8.1

发行日期：**2018 年 3 月 29 日**

重新捆绑 Visitor API 3.1.0 (AN-159524)，该版本包含热修复程序：（CORE-11390、CORE-10634）

## 版本 2.8.0

发行日期：**2018 年 3 月 15 日**

重新捆绑 Visitor API 3.1.0 (AN-159524)，该版本包含热修复程序：（CORE-11390、CORE-10634）

* 将VAPI v3.1与AppMeasurement v2.8捆绑在一起。 (AN-158353)
* 重构构建数据收集端点以促进共享。 (AN-156647)
* 将请求的往返计时量度添加到AppMeasurement。 (AN-158343)

## 版本 2.7.0

发行日期：**2018 年 1 月 18 日**

* 停止对IE 6到9的支持
* 包括Visitor API v3.0.0
* 添加了DIL v7.00

## 版本 2.6.0

发行日期：**2017 年 11 月 9 日**

修复了在调用s_gl时，AppMeasurement库并非总是设置正确的帐户组合的问题。 (AN-152153)

## 版本 2.5.0

发行日期：**2017 年 9 月 21 日**

* 包括`dil.js` 6.12（Audience Manager模块）
* 添加了 Visitor API 2.5.0。

## 版本 2.4.0

发行日期：**2017 年 8 月 17 日**

* 包括dil.js v6.11
* 包含 Visitor API 2.4.0

## 版本 2.3.0

发行日期：**2017 年 7 月 20 日**

* 修复了 `s.Util.getQueryParam` 捕获 `#` 的错误
* 添加了 6.10 版的 `dil.js` (AN-145701)

## 版本 2.2.0

发布日期：**2017 年 6 月 8 日**

* 添加了对多个AppMeasurement实例化订单的支持。 (AN-138237)
* 包括2.2.0版本的访客API。 (AN-144042)

## 版本 2.1.0

发行日期：**2017 年 4 月 20 日**

* 包含最新版本的 `dil.js` (AN-140396)
* 为覆盖页面引荐的 `adobe_mc_ref` 参数添加支持。 (AN-131920)
* 重新包含访客API 2.1.0。 (AN-140873)
* 添加了 `mcorgid` 参数。 (AN-139586)
* 添加了cp (customerPerspective)参数。 (AN-140897)

## 版本 2.0.0

发行日期：**2017 年 3 月 9 日**

* 已移至需要版本号更新为2.0.0的新构建过程。 (AN-137878)
* 将mboxMCSDID处理移动到进行跟踪调用的正确部分位置。 (AN-138483)

## 版本 1.8.0

发行日期：**2017 年 1 月 19 日**

* 包含VisitorAPI 2.0.0
* 重新排序函数调用和检查，以便在中止检查完成后使用SDID。 (AN-134364)
* 添加了 `s.registerPreTrackCallback` 和 `s.registerPostTrackCallback` 挂钩。 (AN-134567)

## 版本 1.7.0

更新日期：**2016 年 11 月 11 日**

* 包含 Visitor API 1.10.1.
* 使用Demdex Integration Library (DIL) 6.6更新Audience Manager模块。 (AN-132065)
* 包括 Visitor API 1.9.0。 (AN-132072)
* 使用AppMeasurement 6.5和额外配置更新DIL Audience Manager模块(AN-129411)
* 包括 Visitor API 1.8.0 (AN-129887)

## 版本 1.6.4

更新日期：**2016 年 8 月 18 日**

* 更新了AppMeasurement以读写AMCV Cookie。 (AN-127098)
* 包括 Visitor API 1.7.0。

>[!NOTE]
>
>另请参阅以下JavaScript版本1.6.3发行说明，其中包括Experience Cloud ID服务的更新要求。

## 版本 1.6.3

更新日期：**2016 年 8 月 4 日**

* 修复了AppMeasurement过早终止请求连接的问题。 (AN-126448)

>[!IMPORTANT]
>
>版本1.6.0的Experience Cloud ID服务&#x200B;*要求* AppMeasurement for JavaScript版本1.6.3或更高版本。 如果您要升级到版本 1.6.0 的 Experience Cloud ID 服务，请确保您使用的是 AppMeasurement 1.6.3 或更高版本。

## 版本 1.6.2

发行日期：**2016 年 7 月 21 日**

* 包括 Visitor API 1.6.0。
* 修复了导致AppMeasurement在访客API中调用错误的模糊处理方法的问题。 (AN-126006)
* 修复了导致JavaScript错误：“属性仅在v:image上有效”的问题。 (AN-124009)

## 版本 1.6.1

发布日期：**2016 年 6 月 16 日**

* 包括 Visitor API 1.5.7。
* 修复了在 Firefox 中处理链接点击次数跟踪时无法触发完整事件的问题。

## 版本 1.6

发行日期：**2016 年 4 月 21 日**

* AppMeasurement Activity Map模块已集成在AppMeasurement标准模块中，以便您只需引用一个`.js`文件。 此外，默认情况下会激活Activity Map跟踪。 (AN-112689)
* 修复了AppMeasurement中查询字符串变量顺序存在的截断问题，以便&#x200B;*`pageURLRest`*&#x200B;位于最后。 (AN-114647)

## 版本 1.5.4

发行日期：**2016 年 3 月 17 日**

* 包括 Visitor API 1.5.4
* 支持 Visitor API 1.5.4+ 选择退出

## 版本 1.5.3

发行日期：**2016 年 1 月 21 日**

* 修复了在POST用于跟踪调用时对Audience Manager模块的处理。 (AN-115381)
* 已将页面URL (“ — g”)的其余部分移动到跟踪请求查询字符串的末尾。 (AN-114647)

## 版本 1.5.2

发行日期：**2015 年 11 月 5 日**

* 包括 Visitor API 1.5.3。
* 修复了对IE 11的URL截断2047检测(AN-114914)

## 版本 1.5.1

发行日期：**2015 年 9 月 17 日**

* 包括 Visitor API 1.5.2
* 更新了Audience Manager模块，以使用Adobe Audience Manager DIL 6.2 — 从VisitorAPI.js获取客户ID，并在事件调用中将它们传递到Adobe Audience Manager。 (AN-104978)

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
* 更新了AudienceManagement模块以使用DIL版本6.0。

>[!NOTE]
>
>**已知问题**：在访客API/AppMeasurement Audience Manager模块集成中，将有两个在IE6-9中发出的目标发布iFrame请求： `//fast.<subdomain>.demdex.net/dest5.html`和`//fast.<subdomain>.demdex.net/dest4.html`。 如在其他浏览器中所看到的，正确的行为是仅加载 `//fast.<subdomain>.demdex.net/dest5.html`。

## 版本 1.4.4

发行日期：**2015 年 4 月 16 日**

* 您现在可以包含具有生命周期量度的自定义上下文数据变量。
* 现在，`trackBeacon` 和 `clearCurrentBeacon` 调用在 PhoneGap 中可用。
* 进行了小修复，以便在 `trackLight` 调用之后清除轻量级服务器调用轮廓 ID。

## 版本 1.4.3

发行日期：**2015 年 2 月 19 日**

* 将所有延迟跟踪调用的处理方式保持一致，以修复延迟期间的备份变量问题，例如已单击的对象。
* 首次跟踪调用后更改为不执行自动反向链接跟踪，以便第2次、第3次（依此类推）跟踪调用（通常为链接跟踪）在&#x200B;*`s.referrer`*&#x200B;于首次跟踪调用之前被手动设置时，不会将反向链接计算两次。
* 更新了分发 zip 文件以包括 Visitor API 1.3.5。

## 版本 1.4.2

发行日期：**2015 年 1 月 15 日**

* 修复了WebKit预渲染处理的处理，以防止跟踪未查看的预渲染页面。
* 更新了分发 zip 文件以包括 Visitor API 1.3.4 和更新的 **[!UICONTROL AudienceManagement]** 模块（包括 DIL 版本 5.5）。

## 版本 1.4.1

发行日期：**2014 年 9 月 18 日**

* 增加了 `tagContainerMarker` 变量，该变量允许实施指定最多 4 个字符和一个附加短划线字符分界符一起附加在版本字符串的后面。 这被用于动态标签管理。

  ```js
  // JavaScript
  s.tagContainerMarker = "D1.0";
  
  // Data Collection request
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
  ```

  这4个字符限制为URL文件路径中允许的字符，例如字母数字和句点。

* 在用H代码双重标记的页面上，修复了在启用强制链接跟踪（Webkit浏览器的默认设置）时使用自动链接跟踪（下载和退出）期间可能会发生的循环。 此外，还围绕自动链接跟踪添加了一项通用保护机制，以防止出现类似的循环。 此安全保护将对&#x200B;*same*&#x200B;对象的重复点击的自动链接跟踪限制为每10秒一次。 这种保护措施仅适用于自动链接跟踪，因此不限制手动链接跟踪(s.tl)调用。 对不同对象的点击也不受此保护措施的影响，并将进行跟踪。
* 修复了在需要延迟时对已单击对象的处理。
* 修复了在访客API尚不具有所需的值的情况下，从链接onclick函数调用s.t时导致页面查看次数加倍的问题。
* HTTP POST支持。

  >[!IMPORTANT]
  >
  >若要让Analytics调用使用`POST`方法，而不是AppMeasurement中的`GET`方法（一种用于解决IE中[截断URL](/help/implement/js/troubleshooting.md)的方法），您必须对CX Enterprise使用最新的访客ID服务实施。

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

* 修复了在处理访客API字段（例如，旧版Analytics访客ID）的已完成和正在等待标记时，会产生错误的问题。
* 支持访客 ID 服务 1.3 中的新增功能。

## 版本 1.3.1

发行日期：**2014 年 5 月 22 日**

* AppMeasurement for JavaScript `s_gi`函数无法正确查找使用H代码`s_gi`创建的实例。 请注意，该问题仅会影响一些双标记实施，在这些实施中，AppMeasurement for JavaScript和H代码位于同一页面上，但却在单独实例中，而且`s_gi`被报表包用来查找实例。

## 版本 1.3

发行日期：**2014 年 4 月 17 日**

* 支持[CX Enterprise Visitor ID服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。

## 版本 1.2.4

发行日期：**2014 年 3 月 13 日**

* 心率视频的错误修复。

## 版本 1.2.3

发行日期：**2014 年 2 月 20 日**

* 心率视频的错误修复。

## 版本 1.2.2

发行日期：**2014 年 2 月 6 日**

* 修复了Audience Manager DIL模块存在的兼容性问题。 Audience Manager客户还必须更新到4.8版本的DIL模块。

## 版本 1.2.1

发行日期：**2013 年 11 月 15 日**

* 修复了用于心率视频测量的页面事件。

## 版本 1.2

发行日期：**2013 年 11 月 14 日**

* 添加了对[心率视频测量](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-overview)的支持。
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
* 修复了阻止层次结构变量在AppMeasurement对象中设置的问题。

## 版本 1.0.2

发行日期：**2013 年 7 月 18 日**

* 散列/片段现在被自动链接跟踪忽略。 此前由于整个 `href` 以 `.pdf` 结束，因此自动对下面的 URL 进行了跟踪：

  ```js
  <a href="index.htm#anchor.pdf">Test Link</a>
  ```

  现在散列/片段被忽略，因此，只有当文件名以匹配的扩展名结束时，才会跟踪该链接。

## 版本 1.0.1

发行日期：**2013 年 5 月 23 日**

代码管理器中现在提供了新的JavaScript AppMeasurement库。 此库提供了与 `s_code.js` 相同的核心功能，但它更轻快，更适合在移动网站和桌面网站上使用。

* 比H.25代码快3到7倍。
* 未压缩的数据仅为21k，而采用gzipped压缩的数据为8k（H.25代码的未压缩数据为33k，采用gzipped的数据为13k）。
* 本机支持获取查询参数、读取和写入Cookie以及执行高级链接跟踪。
* 小而快，足以与移动站点一起使用；并且足够强大，足以在整个桌面Web上使用，允许您在所有Web环境中利用单个库。
