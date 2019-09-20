---
description: AppMeasurement for JavaScript 的发行说明汇总。
seo-description: AppMeasurement for JavaScript 的发行说明汇总。
seo-title: AppMeasurement for JavaScript
solution: Analytics
subtopic: 发行说明
title: AppMeasurement for JavaScript
topic: 开发人员和实施
uuid: 1440013d-d266-4dce-9807-8b9adac73315
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# AppMeasurement for JavaScript{#appmeasurement-for-javascript}

Cumulative release notes for [!DNL AppMeasurement] for JavaScript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

The latest version of each library can be downloaded in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.

## 版本2.17.0

发行日期：**201 年 8 月 23 日**

| 功能/修复 | 描述 |
| -----------| ---------- |
| 添加了百度支持 | 增加了对百度查询字符串重新排序的支持。 |
| 修复了“未定义”错误地 | 修复了导致等待选择加入时已排队点击中的访客值过期的问题。 |

## 版本 2.16.0

发行日期：**2019 年 8 月 15 日**

| 功能 | 描述 |
| -----------| ---------- |
| `sendBeacon` 支持退出链接 | 在 [!UICONTROL AppMeasurement] 中针对退出链接实施了 `sendBeacon` 支持。这将改进退出链接跟踪，并且可能会增加流量。`SendBeacon` 不会在页面的上下文中执行，而是在浏览器的上下文中执行。 也就是说，如果页面卸载 `sendBeacon`时，请求仍将完成。 这对退出链接非常有用，因为它将使退出链接请求完成的可能性大得多。 |
| ECID/fid 值 | 即使 OptIn 设置发生更改，ECID/fid 值现在也会在首次点击时缓存。 |
| DIL 9.3 | 已将受众管理模块更新至 DIL 9.3。 |
| 滚动覆盖范围跟踪 | s.ActivityMap.trackScrollReach 中用于打开或关闭滚动覆盖范围跟踪的公开开关。 |
| 访客 ID 服务 4.4.0 | 升级了 AppMeasurement 以使用访客 ID 服务 4.4.0。 |

## 版本 2.15.0

发行日期：**2019 年 7 月 15 日**

* 向Activity map扩展添加了ActivityMap滚动范围跟踪(AN-172949)
* 将DIL 9.2添加到AppMeasurement(AN-182472)

## 版本 2.14.0

发行日期：**2019 年 5 月 21 日**

* 修复了当多个命中等待处理时，管理跟踪器参数状态的问题。(AN-176931、AN-176629、DTM-12758)
* 更新了 AppMeasurement 以包含 Visitor.js 4.3.0 (AN-180049)

## 版本 2.13.0

发行日期：**2019 年 4 月 10 日**

修复了clearVars中报告的许多问题。 当在跟踪器准备就绪之前发送点击时，会出现问题。 当跟踪器准备就绪时，库可以设置已清除或更改的变量。 (AN-176931、AN-176629、DTM-12758).

## 版本 2.12.0

Release Date: **02/22/2019**

* 已将受众管理模块更新至 DIL 9.1。(AN-175255)
* GTM 安全策略不允许使用 Activity Map 模块。(AN-174679)
* 改进了AppMeasurement，以在身份服务未在选择加入时遵守选择退出。 (AN-175259)

## 版本 2.11.0

Release Date: **02/11/2019**

* 在 AppMeasurement 中添加了对新的 Adobe“选择加入”服务功能的支持。(AN-163546)
* 添加了对在会话存储中存储链接跟踪数据的支持。(AN-162272)
* 为音频分析添加了对媒体流类型的支持。(AN-173265)

## 版本 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Release Date: **09/20/2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] 会在 POST 期间阻止 Cookie 传输。(AN-165538)
* 对 XDomainRequest 的拖放支持。(AN-165733)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## 版本 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

发行日期：**2018 年 5 月 24 日**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. Adobe 建议，每当更新关联的代码库（[!DNL at.js] 等）时，请升级至访客 API 的最新版本。[!DNL AppMeasurement.js]

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483)
* 修复了在关闭链接跟踪后，链接跟踪 Cookie 仍继续写入的问题。(AN-156332)
* 修复了 `registerPreTrackCallback` 和 `registerPostTrackCallback` 在调用多次后中断回调函数签名的问题。(AN-158566)

## 版本 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

发行日期：**2018 年 4 月 12 日**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483)
* 关闭链接跟踪后，链接跟踪 Cookie 将继续写入。(AN-156332)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## 版本 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

发行日期：**2018 年 3 月 29 日**

重新捆绑 Visitor API 3.1.0 (AN-159524)，该版本包含热修复程序：（CORE-11390、CORE-10634）

## 版本 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

发行日期：**2018 年 3 月 15 日**

重新捆绑 Visitor API 3.1.0 (AN-159524)，该版本包含热修复程序：（CORE-11390、CORE-10634）

* Bundle VAPI v3.1 with [!DNL AppMeasurement] v2.8. (AN-158353)
* 重新构建数据收集端点以方便共享。(AN-156647)
* 将请求往返计时量度添加到 [!DNL AppMeasurement]. (AN-158343)

## 版本 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

发行日期：**2018 年 1 月 18 日**

* 不再支持 IE 6 至 9
* 包括访客 API 3.0.0 版
* 包括 DIL 7.00 版

## 版本 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

发行日期：**2017 年 11 月 9 日**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## 版本 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

发行日期：**2017 年 9 月 21 日**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module)

* 添加了 Visitor API 2.5.0。

## 版本 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

发行日期：**2017 年 8 月 17 日**

* 包含 dil.js v6.11
* 包含 Visitor API 2.4.0

## 版本 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

发行日期：**2017 年 7 月 20 日**

* 修复了 [!DNL s.Util.getQueryParam] 捕获 # 的问题
* Added v6.10 of [!DNL dil.js] (AN-145701)

## 版本 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

发行日期：**2017 年 6 月 8 日**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237)
* 包括 Visitor API 版本 2.2.0。(AN-144042)

## 版本 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* 包含最新版本的 [!DNL dil.js] (AN-140396)
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920)
* 重新包含 Visitor API 2.1.0。(AN-140873)
* Added `mcorgid` parameter. (AN-139586)
* 添加 cp (customerPerspective) 参数。(AN-140897)

## 版本 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

发行日期：**2017 年 3 月 9 日**

* 已移动到需要将版本号更新为 2.0.0 的新生成流程。(AN-137878)
* 已将 mboxMCSDID 处理移动到执行跟踪调用的正确区域位置。(AN-138483)

## 版本 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

发行日期：**2017 年 1 月 19 日**

* 包含 Visitor API 2.0.0
* 重新排序了功能调用和检查，确保在完成中止检查后使用 SDID。(AN-134364)
* 新增了以下跟踪前和跟踪后调用挂钩。(AN-134567)

   * s.registerPreTrackCallback
   * s.registerPostTrackCallback
   这些函数的参数是：“callback”（一个函数）以及“callback”函数包含的参数。例如：

   ```
   s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
       console.log("pre track callback"); 
       console.dir(requestUrl); // Request URL 
       console.dir(a); // param1 
       console.dir(b); // param2 
       console.dir(c); // param3 
   }, "param1", "param2", "param3");
   ```

   注册 callback 时，可通过 `requestUrl` 以及传递的任何参数来调用 callback。根据用来注册 callback 的方法，调用操作可以在跟踪调用之前或跟踪调用之后发生无法保证调用这些 callback 的顺序。当创建了最终跟踪 URL 后，将调用在 pre 函数中注册的 callback。如果是成功的跟踪调用，则调用 post callback（若跟踪调用失败，则不调用这些函数）。`registerPreTrackCallback` 中注册的任何 callback 都不会影响跟踪调用。此外，不建议在任何已注册的 callback 中调用任何跟踪方法，因为这可能会导致无限循环。

## 版本 1.7.0 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

更新日期：**2016 年 11 月 10 日**

* 包含 Visitor API 1.10.1.

## 版本 1.7.0 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

更新日期：**2016 年 10 月 20 日**

* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065)
* 包括 Visitor API 1.9.0。(AN-132072)

## 版本 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

更新日期：**2016 年 9 月 15 日**

* Update [!DNL AppMeasurement] [!DNL Audience Manager] Module with DIL 6.5 and Additional Configurations (AN-129411)

* 包括 Visitor API 1.8.0 (AN-129887)

## 版本 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

更新日期：**2016 年 8 月 18 日**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098)
* 包括 Visitor API 1.7.0.

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Experience Cloud ID service.

## 版本 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

更新日期：**2016 年 8 月 4 日**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Experience Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Experience Cloud ID service, please make sure you are using [!DNL AppMeasurement] code verison 1.6.3 or higher.

## 版本 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

发行日期：**2016 年 7 月 21 日**

* 包括 Visitor API 1.6.0。
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006)
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa. 
</note>

 -->

## 版本 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

发行日期：**2016 年 6 月 16 日**

包括 Visitor API 1.5.7.

## 版本 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

发行日期：**2016 年 5 月 19 日**

[!DNL JavaScript] 版本1.5.6

* 包括 Visitor API 1.5.6
* 修复了在 Firefox 中处理链接点击次数跟踪时无法触发完整事件的问题。

## 版本 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

发行日期：**2016 年 4 月 21 日**

* The [!DNL AppMeasurement] [!DNL Activity Map] module has been integrated in the [!DNL AppMeasurement] standard module, so that you only have to reference one [!DNL .js] file. Additionally, [!DNL Activity Map] tracking is activated by default. (AN-112689)

* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## 版本 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

发行日期：**2016 年 3 月 17 日**

* 包括 Visitor API 1.5.4
* 支持 Visitor API 1.5.4+ 选择退出

## 版本 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

发行日期：**2016 年 1 月 21 日**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381)
* 将页面 URL 的其余部分（“-g”）移到跟踪请求查询字符串的末尾。(AN-114647)

## 版本 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

发行日期：**2015 年 11 月 5 日**

* 包括 Visitor API 1.5.3。
* 修复了 URL 截断 2047 的 IE11 检测 (AN-114914)

## 版本 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

发行日期：**2015 年 9 月 17 日**

* 包括 Visitor API 1.5.2

## 版本 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

发行日期：**2015 年 8 月 29 日**

* 包括 Visitor API 1.5.1.

## 版本 1.5.1 {#section_3C9637EDB058479184731067897E857C}

发行日期：**2015 年 7 月 16 日**

* Updated [!DNL Audience Manager] module to use AAM DIL 6.2 - getCustomer IDs from VisitorAPI.js and pass them in /event call to AAM. (AN-104978)

## 版本 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

发行日期：**2015 年 6 月 18 日**

* 支持 Visitor API 1.5，它使用&#x200B;*`getCustomerIDs`*&#x200B;方法收集客户 ID 和经过验证的状态，并且通过数据收集请求来发送 ID。
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1)
* 修复了 1.4.5 版中描述的已知问题。

## 版本 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

发行日期：**2015 年 5 月 21 日**

<table id="table_E0F3EF51FED44420AC97ACF0684554D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 功能 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> iOS 扩展</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> iOS </span> SDK version 4.5, a new <span class="keyword"> iOS </span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS </span> extension apps. </p> <p>请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external">iOS 扩展实施</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Android Wearable 扩展</span> </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> Android </span> SDK version 4.5, a new <span class="keyword"> Android </span> extension lets you collect data from your <span class="keyword"> Android </span> Wearable app. </p> <p>请参阅 <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external">Android Wearable 扩展</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

* 包括 Visitor API 1.4.
* 更新了 AudienceManagement 模块，以便使用 DIL 版本 6.0。

**已知问题**

在访客API/模块集 [!DNL AppMeasurement][!DNL Audience Manager] 成中，将有两个目标发布在IE6-9中发出的iFrame请求： `//fast.<subdomain>.demdex.net/dest5.html` 和 `//fast.<subdomain>.demdex.net/dest4.html`。 如在其他浏览器中所看到的，正确的行为是仅加载 `//fast.<subdomain>.demdex.net/dest5.html`.

## 版本 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

发行日期：**2015 年 4 月 16 日**

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> 功能 </th> 
   <th colname="2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> 具有生命周期量度的自定义数据 </p> </td> 
   <td colname="2"> <p>您现在可以包含具有生命周期量度的自定义上下文数据变量。 </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap </span> </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon </code> and <code> clearCurrentBeacon </code> calls are now available in <span class="keyword"> PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

进行了较小修复，以便在 `trackLight` 调用之后清除轻量级服务器调用配置文件 ID。

## 版本 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

发行日期：**2015 年 2 月 19 日**

* 保持所有延迟跟踪调用的处理连贯一致，这可以修复延迟期间已备份变量（例如，已单击的对象）的问题。
* 首次跟踪调用后更改为不执行自动反向链接跟踪，以便第 2 次、第 3 次（依此类推）跟踪调用在&#x200B;*`s.referrer`*&#x200B;于首次跟踪调用之前被手动设置时，不会将反向链接计算两次。
* 更新了分发 zip 文件以包括 Visitor API 1.3.5。

## 版本 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

发行日期：**2015 年 1 月 15 日**

* 修复了 WebKit 预渲染处理阻止跟踪未查看的预渲染页面的问题。
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

## 版本 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

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
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) implementation for Experience Cloud.

## 版本 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

发行日期：**2014 年 8 月 21 日**

* 已删除对浏览器插件的跟踪（`p` 查询参数），因为这些插件在版本 15 中不再报告。
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.

添加了对[其他 eVar](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=evars_events) (76-250) 和事件 (101-1000) 的支持。

>[!NOTE]
>
>H-Code不支持其他eVar和事件。

[!DNL JavaScript]

## 版本 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

发行日期：**2014 年 6 月 19 日**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* 支持访客 ID 服务 1.3 中的新增功能。

## 版本 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

发行日期：**2014 年 5 月 22 日**

* [!DNL AppMeasurement] for函 [!DNL JavaScript] 数未正 `s_gi` 确查找使用H代码创建的实例 `s_gi`。 Note that this issue only impacted some dual tagging implementations where [!DNL AppMeasurement] for [!DNL JavaScript] and H code were on the same page with separate instances, and `s_gi` was being used to find instances by report suite.

## 版本 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

发行日期：**2014 年 4 月 17 日**

* 支持 [Experience Cloud访客ID服务](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

## 版本 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

发行日期：**2014 年 3 月 13 日**

* 心率视频的错误修复。

## 版本 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

发行日期：**2014 年 2 月 20 日**

* 心率视频的错误修复。

## 版本 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

发行日期：**2014 年 2 月 6 日**

* Fixed a compatibility issue with the [!DNL Audience Manager] DIL module. [!DNL Audience Manager] 客户还必须更新到 4.8 版本的 DIL 模块。

## 版本 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

发行日期：**2013 年 11 月 15 日**

* 修复了用于[心率视频测量](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)的页面事件。

## 版本 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

发行日期：**2013 年 11 月 14 日**

* 添加了对[心率视频测量](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)的支持。
* [!DNL VisitorAPI.js]添加了 ，以便支持[访客 ID 服务](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#)。

## 版本 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* 对于以“opera:”开始的链接，链接跟踪调用不能从 Opera 浏览器发送（“opera:”类似于其他浏览器中的“about:”和“chrome:”）。
* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## 版本 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

发行日期：**2013 年 9 月 18 日**

* 修复了对在 `head` 标签中置入库和页面代码的支持。
* Added missing module `onLoad` support.

## 版本 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

发行日期：**2013 年 8 月 15 日**

* 增加了对通过 Adobe 标签管理进行部署的支持。
* Fixed an issue that prevented hierarchy variables from being set on the [!DNL AppMeasurement] object.

## 版本 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

发行日期：**2013 年 7 月 18 日**

* 散列/片段现在被自动链接跟踪忽略。Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   现在散列/片段被忽略，因此，只有当文件名以匹配的扩展名结束时，才会跟踪该链接。

## 版本 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

发行日期：**2013 年 5 月 23 日**

A new [!DNL JavaScript] [!DNL AppMeasurement] library is now available in Code Manager. 此库提供了与 [!DNL s_code.js] 相同的核心功能，但它更轻快，更适合在移动网站和桌面网站上使用。

* 比 H.25 代码快 3 至 7 倍。
* 未压缩时仅为 21k，压缩后为 8k（H.25 代码未压缩时为 33k，压缩后为 13k）。
* 本地支持获取查询参数、读取 cookie，以及执行高级链接跟踪。
* 小巧、快速的特点非常适合用于移动网站，而强健的功能又适合在完整的桌面网站上使用，从而使您可以在所有 Web 环境中使用单个库。

请参阅 实施指南中的 [Javascript AppMeasurement](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=appmeasure_mjs)。[!DNL Analytics]

>[!NOTE]
>
>此新版本不支持某些插件。 有关详细信息，请参阅[插件支持](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=plugins_support)。
