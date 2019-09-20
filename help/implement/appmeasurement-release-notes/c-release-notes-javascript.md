---
description: 旧版 JavaScript H 代码的发行说明汇总。
seo-description: 旧版 JavaScript H 代码的发行说明汇总。
seo-title: JavaScript H 代码 - 旧版
solution: Analytics
subtopic: 发行说明
title: JavaScript H 代码 - 旧版
topic: 开发人员和实施
uuid: 4586b250-0f1b-45b8-829c-18dc1201956f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# JavaScript H 代码 - 旧版{#javascript-h-code-legacy}

旧版 JavaScript H 代码的发行说明汇总。

>[!NOTE]
>
>To find the current library version, use [DigitalPulse Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=debugger_about).

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## H.27.5 - Update {#section_DB9535C7EC4A4DDE9BA56B6C02BE8327}

发行日期：**2016 年 6 月 16 日**

包括 Visitor API 1.5.7.

## H.25.5 - Update {#section_B10151D7718F4568AE523BE1553FCCB7}

发行日期：**2016 年 5 月 19 日**

包括 Visitor API 1.5.5。

## H.27.5 - Update {#section_AD73ECD5CDAB4E158B509BA7B4B8CC1F}

发行日期：**2015 年 11 月 5 日**

* 包括 Visitor API 1.5.3。

## H.27.5 - Update {#section_8A94D8A74A39486AAE248A22D661A261}

发行日期：**2015 年 9 月 17 日**

* 包括 Visitor API 1.5.2。

## H.27.5 - Update {#section_62D1787F90FB4730B5F0C79EC1EF84B1}

发行日期：**2015 年 8 月 20 日**

* 包括 Visitor API 1.5.1.

## H.27.5 - Update {#section_F58AF8B7FAE9470ABCBF2AAD9E7AF881}

发行日期：**2015 年 6 月 18 日**

* 包括 Visitor API 1.5。

## H.27.5 - Update {#section_B3E310AFF909480BAD59A7F87D298348}

发行日期：**2015 年 5 月 21 日**

* 包括 Visitor API 1.4

## H.27.5 - Update {#section_E7006FC903064376A85D3EC2AC1D2544}

发行日期：**2015 年 4 月 16 日**

* Added Integrate module to s_code.js in legacy [!DNL AppMeasurement] for [!DNL JavaScript] H.X ZIP file. (AN-101001)

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

发行日期：**2015 年 2 月 19 日**

* 包括 Visitor API 1.3.5。
* 首次跟踪调用后更改为不执行自动反向链接跟踪，以便第 2 次、第 3 次（依此类推）跟踪调用在&#x200B;*`s.referrer`*&#x200B;于首次跟踪调用之前被手动设置时，不会将反向链接计算两次。(AN-92647)

## H.27.4 - Update {#section_ED38D59E83B4417180877F7C10BE4582}

发行日期：**2015 年 1 月 15 日**

* 更新了分发 zip 文件以包括访客 API 1.3.4。

发行日期：**2014 年 9 月 18 日**

* 增加了 `tagContainerMarker` 变量，该变量允许实施指定最多 4 个字符和一个附加短划线字符分界符一起附加在版本字符串的后面。这被用于动态标签管理。

```js
  //  
<keyword>
  JavaScript 
</keyword> 
  s.tagContainerMarker = "D1.0"; 
    
  // Data Collection request 
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
```

## H.27.3 {#section_B38C61EE3BEA49CAA7A664395C85E4CF}

发行日期：**2014 年 8 月 21 日**

* 执行了某些内部更改以支持即将推出的功能。

## H.27.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

发行日期：**2014 年 6 月 19 日**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* 支持访客 ID 服务 1.3 中的新增功能。

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

发行日期：**2014 年 6 月 11 日**

* Fixed an issue in the [!DNL Analytics] for [!DNL Target] integration that caused some hits to incorrectly be merged.

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

发行日期：**2014 年 5 月 22 日**

* 支持 [Experience Cloud访客ID服务](https://marketing.adobe.com/resources/help/en_US/mcvid/)。
* 支持 [Analytics 与 Target 的集成](https://marketing.adobe.com/resources/help/en_US/target/a4t/)。

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

发行日期：**2013 年 10 月 17 日**

* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

发行日期：**2013 年 7 月 18 日**

* 散列/片段现在被自动链接跟踪忽略。Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

现在散列/片段被忽略，因此，只有当文件名以匹配的扩展名结束时，才会跟踪该链接。

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

发行日期：**2013 年 4 月 29 日**

* `useForcedLinkTracking`使用自定义链接代码的手动链接跟踪[中描述的 ](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_manuallinktrackcustomlink) 选项现在可以应用到 Firefox 20+（以前，它只能应用到 WebKit 浏览器）。

* 现在，每个实例生成的图像对象 ID 都是唯一的。这可以防止多个实例位于同一页面时出现冲突。

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

发行日期：**2013 年 4 月 19 日**

* Fixed an issue in forced link tr [!DNL Windows]acking that caused a [!DNL JavaScript] error on some [!DNL Android] 2.2 Devices.

* 在 Media Player 上的视频自动跟踪中，修复了导致播放时间无法正确跟踪的清理问题。

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

发行日期：**2013 年 2 月**

* Changed automatic exit link tracking to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

* 使得受 `useForcedLinkTracking` 影响的点击事件的范围更加精确。自动强制链接跟踪仅适用于：

   * `<A>` 和标 `<AREA>` 记

   * 标记必须具有 `HREF` 属性
   * The `HREF` can't start with `#`, `about:`, or `javascript:`

   * The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`)

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

发行日期：**2013 年 1 月**

* 为了支持 Adobe 数据收集服务器中扩展的“页面 URL”字段，已添加对发送大于 255 字节 URL 的支持。Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. 这有助于在浏览器截断的情况下防止长 URL 优先于其他数据，但仍然启用对长 URL 的捕获功能。

* Fixed handling URL decoding for strings that are encoded with a mixed use of `escape` and `encodeURIComponent`.

* 已修复 WebKit 浏览器中页面上首次服务器调用超时情况下链接跟踪失败的问题。
* 添加了新的备用访客识别方法。请参阅[识别独特访客](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors)。
* Added a new `abort` flag that can be set inside `doPlugins`. 将此标记设置为 true 会导致 [!DNL AppMeasurement] 库不继续进行跟踪呼叫。中止标记已通过每个跟踪呼叫进行重置，因此，如果还需要中止后续跟踪呼叫，则需要在 `doPlugins` 内重新设置标记。

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

这可让您将用于确认您不希望跟踪的活动的逻辑集中在一起，如一些自定义链接或显示广告中的外部链接。

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

发行日期：**2012 年 10 月**

* Added support for reporting an additional version number in the [!DNL JavaScript] version report. 以前该版本限于 2 个字符（例如 1.8）。现在添加了对 3 个字符版本号（例如 1.8.5）的支持。
* Fixed an issue with [!DNL Tag Manager] that prevented repeated values in Dependant Code blocks from being sent.

## H.25.1 {#section_680CE31CFA9945978F42612B684DB831}

发行日期：**2012 年 9 月**

* 对以下字符的强制 URL 编码：

```
  ~ 
  ! 
  * 
  ( 
  ) 
  '
```

This resolves issues with un-escaped characters being stored in the [!DNL ClickMap] `s_sq` cookie.

* 修复了可能导致在使用自定义 `media.monitor` 方法（跟踪媒体关闭事件）时未发送视频完成事件的问题。

```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

发行日期：**2012 年 7 月**

进行更新以确保成功完成对 WebKit 浏览器（Safari 和 Chrome）的链接跟踪。进行此更新之后，系统会成功跟踪被自动跟踪的下载和退出链接（由 `s.trackDownloadLinks` 和 `s.trackExternalLinks` 确定）。If you are tracking custom links using manual [!DNL JavaScript] calls, you need to modify how these calls are made.

例如，通常使用与以下类似的代码跟踪退出和下载链接：

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

Firefox 和 Internet Explorer 会执行跟踪链接调用并打开新页面。但是，打开新页面时，WebKit 浏览器可能会取消执行跟踪链接调用。因此，在使用 WebKit 浏览器时通常无法完成跟踪链接调用。

为了解决此问题，H.25 包含一种可强制 WebKit 浏览器等待跟踪链接调用完成的重载跟踪链接方法 (`s.tl`)。这一新方法执行跟踪链接调用之后会处理导航事件，而非使用默认浏览器操作。该重载方法需要一个名为 `doneAction` 的额外参数来指定完成链接跟踪调用时要执行的操作。

若要使用这一新方法，请使用额外的 `s.tl` 参数更新对 `doneAction` 的调用，如下所示：

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

完成跟踪调用后，在 `doneAction` 生成默认浏览器行为的镜像并打开 `href` 属性指定的 URL 时传递“navigate”。

下表汇总了配置变量以及为支持此功能而对 H.25 所做的更新。

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>变量 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>useForcedLinkTracking </p> </td> 
   <td colname="col2"> <p>此标记用于禁用 WebKit 浏览器的强制链接跟踪。对于 WebKit 浏览器，默认将启用强制链接跟踪，而其他浏览器则会忽略该功能。 </p> <p> <b>默认值</b> </p> <p> <code> true </code> </p> <p> <b>示例</b> </p> 
    <code class="syntax javascript">
      s.useForcedLinkTracking&amp;nbsp;=&amp;nbsp;false </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forcedLinkTrackingTimeout </p> </td> 
   <td colname="col2"> <p>执行传递给 <code>s.tl</code> 的 <code>doneAction</code> 前，等待跟踪完成的最大毫秒数。此值指定最大等待时间。如果跟踪链接调用在此超时前完成，则立即执行 <code>doneAction</code>。如果您发现跟踪链接调用没有完成，可能需要提高此超时。 </p> <p> <b>默认值</b> </p> <p>250 </p> <p> <b>示例</b> </p> 
    <code class="syntax javascript">
      s.forcedLinkTrackingTimeout&amp;nbsp;=&amp;nbsp;500 </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink (<code>s.tl </code>) </td> 
   <td colname="col2"> <p>跟踪退出、下载和自定义链接。提供一个可选参数，以指定跟踪链接调用在 WebKit 浏览器中完成后要执行的导航操作。 </p> <p> <b>语法</b> </p> 
    <code class="syntax javascript">
      s.tl(linkObject,linkType,linkName,variableOverrides,doneAction) </code> <p> <b>doneAction</b>：（可选）指定跟踪链接调用发送或超时（根据 <code>s.forcedLinkTrackingTimeout</code> 指定的值）后执行的操作。<code>doneAction</code> 可以是字符串 "navigate"，但这会导致该方法将 <code>document.location</code> 设置为 <code>linkObject</code> 的 <code>href</code> 属性。<code>doneAction</code> 还可以是允许进行高级自定义的函数。 </p> <p>If providing a value for <code> onclick </code> in an anchor <code> false </code> event, you must return <code> s.tl </code> after the <code> href </code> call to prevent the default browser navigation. </p> <p> To mirror the default behavior and follow the URL specified by the <code> doneAction </code> attribute, provide a string of 'navigate' as the <code> doneAction </code>. </p> <p>Optionally, you can provide your own function to handle the navigation event by passing this function as the <code>$1</code>. </p> <p> <b>示例</b> </p> 
    <code class="syntax javascript">
      &lt;a&amp;nbsp; href="。."&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,'navigate');return&amp;nbsp;false"&gt;单击此处&lt;/a&gt; </code> &lt;a&amp;nbsp;nbsp; <code class="syntax javascript">&lt;a&amp;a&gt;.tl(this,'o','MyLink',null,function(){if(confirm('Contreed?'))document.location=...});return&amp;nbsp;false"&gt;单击此处&lt;/a&gt; </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

发行日期：**2012 年 4 月**

建议所有客户都使用此更新。

* 增强了使用 Google Chrome Prerender ([https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender)) 预呈现页面时的检测能力。Since Prerender loads and executes [!DNL JavaScript] and other code, this could result in page views being sent before a user clicks to visit your site. The [!DNL JavaScript] library now waits until the user visits your site before sending server calls for these prerendered pages.
* 向 库添加了 `timestamp`[!DNL JavaScript] 变量，客户可以通过与其他 库类似的方式自定义时间戳数据。[!DNL AppMeasurement]

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

发行日期：**2012 年 2 月**

* 修复了对于使用 Javascript `Object.prototype` 覆盖的客户，导致图像请求中包含额外数据的问题。目前在处理上下文数据变量时会跳过所有使用 `Object.prototype` 的情况。
* 修复了在某些情况下导致使用相同的值传递两次 `pe` 查询参数的问题。
* 修复了 中的 [!DNL ClickMap][!DNL JavaScript] 跟踪，忽略对 body 标记的单击，即使当标记具有 `onClick` 事件句柄时也如此。
* 向与简易跟踪调用 (`trackLight`) 一起使用的变量添加了时间戳。

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

发行日期：**2012 年 1 月**

* 使用新方法更新了视频跟踪功能，以便跟踪完成的视频查看。
* Fixed an issue that caused an "Attribute only valid on v:image" [!DNL JavaScript] error for `OnClick` events on VML elements in IE.
* 修复了上下文数据变量未包含在链接服务器调用中（即使已在 `linkTrackVars` 中引用）的错误。上下文数据变量与处理规则结合使用。

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

发行日期：**2011 年 11 月**

* 更新了视频跟踪功能，可以合并同时出现的区段和里程碑的点击量。

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

发行日期：**2011 年 11 月**

* 支持的内部更新 [!DNL Adobe Tag Manager]。

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

发行日期：**2011 年 11 月**

* 支持的内部更新 [!DNL Adobe Tag Manager]。

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

发行日期：**2011 年 10 月**

* Fixed an issue that caused the `linkTrackVars=none` and `linkTrackEvents=none` settings to not apply when using automatic exit link tracking. 这些设置现在可应用于自动退出链接，以便 prop、eVar 和事件不会随退出链接图像请求一起发送。

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

发行日期：**2011 年 9 月**

* 从移动设备上的图像标记中删除了边框属性以符合无线标记语言 (WML) 标准。这可以修复某些移动设备上存在的渲染问题。

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

发行日期：**2011 年 8 月**

修复了视频跟踪中百分比测量的准确度问题。

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

发行日期：**2011 年 7 月**

* 添加了 [!DNL Adobe Tag Manager].

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

发行日期：**2011 年 6 月**

* Fixed an issue that caused [!DNL JavaScript] errors when accessing certain properties of Vector Markup Language (VML) shape elements.
* 超过 255 个字符的反向链接字符串现在通过缩短路径（而非查询字符串）的方式截断。这修复了查询字符串参数被截断因此不被收集的问题。

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

发行日期：**2011 年 5 月**

* 修复了无法发送视频跟踪 (pev3) 变量的问题。
* 修复了 `s_gi` 调用无法使代码兼容 G 和 H 代码的问题。在将 1 作为第二个参数传递给此调用时，该代码现在配置为兼容这两个版本。

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

发行日期：**2011 年 4 月**

* 支持推动服务器端处理规则的 contextData （仅限 v15）。
* 支持简易服务器调用（仅限 v15）。
* 支持将 1 以外的值分配到事件列表中的计数器事件。
* 支持新的跟踪视频方法 - 使用转化 eVar 和事件（目前为测试版）。
* 删除了对 Media.trackWhilePlaying 设置为 false 的支持。该值将总是为 true。
* 添加了 debugTracking 标记以能够和其他平台一样，将请求日志发送到 Firebug 控制台。
* 确保无论使用何种浏览器 "+" 始终由 URL 编码。
