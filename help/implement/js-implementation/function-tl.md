---
description: 您可以根据 JavaScript AppMeasurement 文件中设置的参数自动跟踪文件下载和退出链接。
keywords: Analytics 实施
seo-description: 您可以根据 JavaScript AppMeasurement 文件中设置的参数自动跟踪文件下载和退出链接。
seo-title: s.tl() 函数 - 链接跟踪
solution: Analytics
subtopic: 链接跟踪
title: s.tl() 函数 - 链接跟踪
topic: 开发人员和实施
uuid: f28f071a-8820-4f74-89cd-fd2333 a21 f22 f22
translation-type: tm+mt
source-git-commit: acaea784c977d7ff438f84faf8af5a3c605e3cf5

---


# s.tl() 函数 - 链接跟踪

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

## s.tl() 函数 - 链接跟踪 {#concept_EA13689CB8EE4F308FC89A1293046D5E}

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

如有需要，可按照下面的说明使用自定义链接代码手动跟踪这些类型的链接。此外，自定义链接代码可用来跟踪可满足多种跟踪和报告需求的通用自定义链接。

## s.tl() 参数引用 {#section_DDF19EE3ACE24EFAB2D65CD4B0D7DBC4}

<!-- Meike, I converted a table within to table to this section. Please check against orginal file -Bob -->

**this**

第一个参数应当始终设置为 this（默认）或 true。该参数引用被点击的对象；当设置为“this”时，它会引用链接的 HREF 属性。

如果在没有HREF属性的对象上实施链接跟踪，应始终将此参数设置为“this”。

因为点击链接通常会将访客带离当前页面，因此，使用 500 毫秒延迟来确保在用户离开页面之前已将图像请求发送至 Adobe。只有在离开页面时才需要使用此延迟，但它通常会在调用 s.tl() 函数时出现。如果要禁用延迟，请在调用 s.tl() 函数时将关键词“true”作为首个参数传递。

**linkType**

`s.tl(this,linkType,linkName, variableOverrides, doneAction)`

linkType 具有三个可能值，具体取决于您要捕获的链接类型。如果链接不是下载或退出链接，则应当选择自定义链接选项。

| 类型 | linkType 值 |
|--- |--- |
| 文件下载 | &#39;d&#39; |
| 退出链接 | &#39;e&#39; |
| 自定义链接 | &#39;o&#39; |

**linkName**

它可以是任何自定义值，其长度最多为 100 个字符。它可确定链接在相应报表中的显示方式。

**variableOverrides**

（可选，若不使用则传递 NULL 值）它允许您更改此单一调用的变量值，这类似于其他 [!DNL AppMeasurement] 库。

**useForcedLinkTracking**

此标记用于禁用某些浏览器的强制链接跟踪。FireFox 20 及更高版本和 WebKit 浏览器均默认启用强制链接跟踪。

默认值= true

示例: `s.useForcedLinkTracking& = false`

**forcedLinkTrackingTimeout**

执行传递给 `s.tl` 的 doneAction 前，等待跟踪完成的最大毫秒数。此值指定最大等待时间。如果跟踪链接调用在此超时期限前完成，则立即执行 doneAction。如果您发现跟踪链接调用没有完成，建议您提高此超时期限。

默认值=250

示例: `s.forcedLinkTrackingTimeout&nbsp;=&nbsp;500`

**doneAction**

一个可选参数，在启用 useForcedLinkTracking 的情况下，可使用该参数指定将在跟踪链接调用完成后执行导航操作。

语法：

`s.tl(linkObject,linkType,linkName,variableOverrides,doneAction)`

 doneAction ：（可选）指定将在跟踪链接调用发送或超时后执行的操作，具体根据以下项指定的值：

`s.forcedLinkTrackingTimeout`

doneAction 变量可以是字符串“navigate”，这会导致该方法将 `document.location` 设置为 linkObject 的 href 属性。doneAction 变量还可以是允许进行高级自定义的函数。

如果为锚记 onclick 事件中的 doneAction 分配值，则必须在 `s.tl` 调用后返回 false，以防止默认的浏览器导航。

要生成默认行为的镜像并导航 href 属性指定的 URL，请提供字符串“navigate”作为 doneAction。

或者，您可以提供自己的函数，并将此函数作为 doneAction 传递来处理导航事件。

示例：

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a> <a href="#" onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

**示例**

在以下示例中，[!UICONTROL s.tl] 函数调用使用默认的 500 毫秒延迟，来确保在离开页面前收集到数据。

```js
s.tl(this,'o','link name');
```

在以下示例中，如果用户不打算离开页面，或只要被点击的对象没有 HREF，即会禁用 500 毫秒延迟。

```js
s.tl(true,'o','link name');
```

最长可延迟 500 毫秒。如果请求的图像在 500 毫秒以内返回，则延迟立即停止。从而允许访客移至下一页面或在本页面执行下一个操作。

以下示例显示如何在 WebKit 浏览器中处理自定义链接：

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a>
```

```js
<a href="#"  onclick="s.tl(this,'o','MyLink',null,  
function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

>[!NOTE]
>
>自定义链接代码的使用通常非常特定于网站和报表需求。您可以在实施自定义链接代码之前，先联系您的 Adobe 顾问或客户关怀以了解可能遇到的各种情况，以及如何根据自己的业务需要最大限度地利用此项功能。

下列示例显示了使用自定义链接代码跟踪链接的基本代码：

```js
<a href="index.html" onClick="s.tl(this,'o','Link Name')">My Page</a>
```

>[!NOTE]
>
>[!UICONTROL s_ gi] 函数必须包含报表包ID作为函数参数。务必将 [!DNL rsid] 切换为您的唯一报表包 ID。

>[!NOTE]
>
>如果未定义链接名称参数，则链接的URL(通过“this”对象确定)用作链接名称。

可将 [!DNL Analytics] 变量定义为自定义链接代码的一部分。

## 自动跟踪退出链接和文件下载 {#concept_DF078C5C1B004695B3B7C4536C99D4B2}

您可根据定义文件下载文件类型和退出链接的参数配置 JavaScript 文件，以自动跟踪文件下载和退出链接。

<!-- 

link_automatic.xml

 -->

控制自动跟踪的参数如下所示：

```js
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

参数*`trackDownloadLinks`* 并 *`trackExternalLinks`* 确定是否启用了自动文件下载和退出链接跟踪功能。When enabled, any link with a file type matching one of the values in *`linkDownloadFileTypes`* is automatically tracked as a file download. Any link with a URL that does not contain one of the values in *`linkInternalFilters`* is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

## Example 1 {#section_504D163608E14B25A8B4CA9D615C6735}

The file types [!DNL jpg] and [!DNL aspx] are not included in *`linkDownloadFileTypes`* above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter *`linkLeaveQueryString`* modifies the logic used to determine exit links. *`linkLeaveQueryString`*如果= false，则只使用链接URL的域、路径和文件部分确定退出链接。*`linkLeaveQueryString`*如果= true，则链接URL的查询字符串部分也用于确定退出链接。

## Example 2 {#section_25660B64E28248A0BC982B2AF5603C0E}

使用下列设置时，以下示例将计为退出链接：

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

## 示例 3 {#section_2A78D05162D640169844A7D1E9799BAA}

使用下列设置时，以下链接不会计为退出链接：

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

>[!NOTE]
>
>单个链接只能作为文件下载或退出链接跟踪，并且文件下载优先。If a link is both an exit link and file download based on the parameters *`linkDownloadFileTypes`* and *`linkInternalFilters`*, it is tracked and reported as a file download and not an exit link. 下表概述了文件下载和退出链接的自动跟踪。

## 使用自定义链接代码的手动链接跟踪 {#concept_7113B5D037BE4622B6934554C6D18F96}

自动跟踪无法满足需要或不适用时，自定义链接代码允许跟踪文件下载、退出链接和自定义链接。

<!-- 

link_manual.xml

 -->

通常可通过向链接添加 [!UICONTROL onClick] 事件处理程序，或向现有例程添加代码等方式，来实施自定义链接代码。可通过几乎所有 JavaScript 事件处理程序或函数来实施。

Link Tracking consists of calling the [!DNL AppMeasurement] for JavaScript function whenever the user performs actions that generate data you want to capture. 此函数 ([!UICONTROL s.tl()]) 既可以在事件处理程序（如 [!UICONTROL onClick] 或 [!UICONTROL onChange]）中直接调用，也可来自单独的函数。此 [!UICONTROL s.tl()] 函数具有五个参数。前三个是必需的：

```js
s.tl(this,linkType,linkName, variableOverrides, doneAction)
```

## FireFox 和 WebKit 浏览器上的自定义链接跟踪 {#section_F2B9A2A3CC1F4BB9A64456BC39FC50B9}

JavaScript H.25 包含一项更新，该更新可确保在 WebKit 浏览器（Safari 和 Chrome）内成功完成链接跟踪。JavaScript H.25 包含一项更新，该更新可确保在 FireFox 20 及更高版本上成功完成链接跟踪。

进行此更新之后，系统会成功跟踪被自动跟踪的下载和退出链接（由 [!DNL s.trackDownloadLinks] 和 [!DNL s.trackExternalLinks] 确定）。如果您要使用手动 JavaScript 调用跟踪自定义链接，则需要修改发出这些调用的方式。例如，通常使用与以下类似的代码跟踪退出和下载链接：

```js
<a href="https://anothersite.com" onclick="s.tl(this,'e','AnotherSite',null)">
```

Internet Explorer 会执行跟踪链接调用并打开新页面。其他浏览器可能会在打开新页面时取消执行跟踪链接调用。这通常会阻止跟踪链接调用的完成。

为了解决此问题，H.25（于 2012 年 7 月发布）新增了一种重载跟踪链接方法 ([!DNL s.tl])，该方法可强制存在此问题的浏览器等待跟踪链接调用完成。这一新方法可执行跟踪链接调用并处理导航事件，而不使用默认浏览器操作。该重载方法需要一个名为 [!UICONTROL doneAction] 的额外参数来指定完成链接跟踪调用时要执行的操作。

若要使用这一新方法，请使用额外的 [!DNL s.tl]doneAction[!UICONTROL  参数更新对 ] 的调用，如下所示：

```js
<a href="https://anothersite.com"  
onclick="s.tl(this,'e','AnotherSite',null,'navigate');return false">
```

跟踪调用完成后，在 [!UICONTROL doneAction] 生成默认浏览器行为的镜像并打开 href 属性指定的 URL 时传递“navigate”。

在 JavaScript H.25.4（2013 年 2 月发布）中，向 `useForcedLinkTracking` 启用时所跟踪的链接添加了以下范围限制。自动强制链接跟踪仅适用于：

* `<A>` 和 `<AREA>` 标签。
* 标记必须具有 `HREF` 属性。
* The `HREF` can&#39;t start with `#`, `about:`, or `javascript:`.
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

## 使用图像请求进行链接跟踪 {#concept_FF31C8D1B3DF483D853BF0A9D637F02F}

通过构建图像请求，无需调用 s.tl() 函数即可跟踪链接。

<!-- 

link_img.xml

 -->

图像请求通过在图像请求 src 参数中添加“pe”参数来进行硬编码，如下所示：

```
pe=[type]
```

Where `[type]` is replaced with the type of link you want to track:

* lnk_d = 下载
* lnk_e = 退出
* lnk_o = 自定义

此外，链接 URL 可通过在 pev1 参数中传递 URL 来指定：

```
pev1=mylink.com
```

链接名称可通过在 pev2 参数中传递名称来指定：

```
pev2=My%20Link
```

例如：

```
<img src="https://collectiondomain.112.2o7.net/b/ss/reportsuite/1/H.25.3--NS/0?pe=lnk_e&pev1=othersite.com&pev2=Offsite%20Link" width="1" height="1" border="0" />
```

## 设置文件下载、退出链接和自定义链接的其它变量 {#concept_8DD06387D5234A52A6E361572FAA2DF6}

Two parameters (  and ) control which [!DNL Analytics] variables are set for file downloads, exit links, and custom links.

<!-- 

link_variables.xml

 -->

默认情况下，它们在 JS 文件中的设置如下所示：

```js
s.linkTrackVars="None"
```

```js
s.linkTrackEvents="None"
```

The*`linkTrackVars`*参数应包括您想要通过每个文件下载、退出链接和自定义链接跟踪的每个变量。*`linkTrackEvents`* 该参数应包括每个文件下载、退出链接和自定义链接要跟踪的每个事件。在出现其中一种链接类型时，将跟踪每个已标识变量的当前值。

例如，若要通过每个文件下载、退出链接和自定义链接跟踪 prop1、eVar1 和 event1，可在全局 JS 文件中使用以下设置：

```js
s.linkTrackVars="prop1,eVar1,events"
```

```js
s.linkTrackEvents="event1"
```

>[!NOTE]
>
>The variable *`pageName`* cannot be set for a file download, exit link, or custom link, because each of the link types is not a page view and does not have an associated page name.

>[!NOTE]
>
>If *`linkTrackVars`* (or *`linkTrackEvents`*) is null (or an empty string), all [!DNL Analytics] variables (or events) that are defined for the current page are tracked. 这极有可能会在无意中夸大每个变量的实例，应予以避免。

## 最佳实践 {#section_DA3CA596792E4BD6B5FFE89BCE0E617D}

The settings for *`linkTrackVars`* and *`linkTrackEvents`* within the JS file affect every file download, exit link, and custom link. 如果变量（或事件）应用至当前页面而非特定的文件下载、退出链接或自定义链接，则会夸大每个变量和事件的实例。

要确保使用自定义链接代码设置正确的变量，Adobe 建议将自定义链接代码中的 *`linkTrackVars`* 在 *`linkTrackEvents`* 自定义链接代码中，如下所示：

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

The values of *`linkTrackVars`* and *`linkTrackEvents`* override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

>[!NOTE]
>
>在以上示例中，prop的值是在自定义链接代码本身中设置的。prop2 的值则来自在页面上设置的变量的当前值。

## 在自定义链接代码中使用函数调用 {#concept_DB662C93B3ED415DB72C80270502BE5D}

由于自定义链接代码的复杂性，您可将代码合并到自包含 JavaScript 函数（在页面上或在链接的 JavaScript 文件中定义），然后在 [!UICONTROL onClick] 处理程序中调用该函数。

<!-- 

link_functions.xml

 -->

For example, you could insert the following two functions in your `AppMeasurement.js` file, just below the `s_doPlugins()` function, and then use them throughout your site:

```js
/* Set Click Interaction values (with timeout - H25 code and higher*/ 

function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction',null,'navigate'); 
}
```

```js
/* Set Click Interaction values (without timeout - pre H25 code*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction'); 
}
```

>[!NOTE]
>
>如果需要，您可以将链接类型和链接名称传递给JavaScript函数的其他参数。

您可以使用类似于以下代码来调用这些函数：

```
<a href=”https://www.your-site.com/some_page.php” onclick=”trackClickInteraction('this.href');”>Link Text</a>
```

## 避免重复链接计数 {#section_9C3F73DE758F4727943439DED110543C}

在自动文件下载或退出链接跟踪通常会捕获链接的情况下，可能会将链接计为两次。

例如，如果您自动跟踪 PDF 下载，以下代码会导致下载计数重复：

```js
function trackDownload(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 s.tl(obj,'d','PDF Document'); 
}
```

为确保不会发生链接重复计数的情况，请使用下列经过修改的 JavaScript 函数：

```js
<script language=JavaScript> 
function linkCode(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 var lt=obj.href!=null?s.lt(obj.href):""; 
 if (lt=="") { s.tl(obj,'d','PDF Document'); } 
}
```

上面代码中的最后两行可修改自定义链接代码的行为，以便只会发生自动跟踪行为，从而消除任何重复计数的可能。

## 使用 useForcedLinkTracking 弹出窗口 {#concept_0AC4BA3A64B84CCB8D9A6021A022D1C3}

When `useForcedLinkTracking` is enabled, [!DNL AppMeasurement] overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. [!DNL AppMeasurement] 可手动执行跟踪链接调用并处理导航事件，而不使用默认浏览器操作。

<!-- 

link_popups.xml

 -->

When tracking some links that open a popup window, the Chrome built-in popup blocker might prevent [!DNL AppMeasurement] from opening a popup window that would normally be allowed. To avoid this, add a `target="_blank"` attribute to calls that open a window:

```
<a href="./popup.html" target="_blank" onClick="<a href="./popup.html" onclick="s.tl(this,'o','popup',null,'navigate');javascript:window.open('./popup.html','popup','width=550,height=450'); 
return false;">
```

这可以按预期跟踪链接并加载弹出窗口。

## URL 链接缩短服务 {#concept_CD792362A8E04448B452BE9A18772024}

URL 链接缩短服务（如 bit.ly）通常不会作为页面查看或反向链接进行跟踪。这些服务会将具有完整 URL 的 301/302 重定向返回到 Web 浏览器，然后由 Web 浏览器向该完整的 URL 发送单独的新请求。将保留原始反向链接，因为循环中不再具有缩短链接，而且请求中不指示使用重定向服务获取 URL。

<!-- 

link_shortener.xml

 -->

由于可用的服务多种多样，我们建议在您的网站上测试正在使用的特定方案，以确定服务所使用的重定向机制。

## doPlugins 中的链接跟踪变量 {#concept_B5AC1D4372AA4A7D8C7871453A4F1215}

为了帮助管理链接跟踪，请在 `doPlugins` 函数运行之前填充以下这些变量。

<!-- 

util_linkhandler.xml

 -->

在 `doPlugins` 内部，您可以使用以下值修改链接跟踪行为。例如，您可以终止跟踪，或向跟踪请求添加其他变量。

<table id="table_55CCF4F2BF474FD3B703C926B896B392"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 影响 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> linkType </td> 
   <td colname="col2"> <p>包含自动确定的链接类型（如果有）。可设置为以下值之一： </p> 
    <ul id="ul_81ACB5D00D774E86AFD22C61AD4D0E2C"> 
     <li id="li_52B6F2B124024DEFB422D1E9E97254C0">d（下载） </li> 
     <li id="li_E842C2E64F034181A364C639C30451FD">e（退出） </li> 
     <li id="li_3263F378CE65407E81B6C5C597CED1E8">o（自定义/其他） </li> 
    </ul> <p>此为图像请求中的 <code>pe</code> 参数。 </p> </td> 
   <td colname="col3"> <p>如果通过 <code>linkURL</code> 或 <code>linkName</code> 设置，则服务器调用将作为下载、自定义或退出链接发送。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkName </td> 
   <td colname="col2"> <p>该名称将在自定义、下载或退出链接报表中显示。从 100 个字符处截断。可设置为任何字符串。 </p> <p>此为图像请求中的 <code>pev2</code> 参数。 </p> </td> 
   <td colname="col3"> <p> 如果通过 <code>linkType</code> 设置，则图像请求将作为下载、自定义或退出链接发送 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkURL </td> 
   <td colname="col2"> <p>链接的 URL，当 linkName 不存在时用作名称。可设置为任何 URL 字符串。 </p> <p>此为图像请求中的 <code>pev1</code> 参数。 </p> </td> 
   <td colname="col3"> <p>如果通过 <code>linkType</code> 设置，则图像请求将作为下载、自定义或退出链接发送 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkObject </td> 
   <td colname="col2"> <p>点击的引用对象。此为只读。 </p> </td> 
   <td colname="col3"> <p>对测量无直接影响。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

## 验证文件下载、退出链接和自定义链接 {#concept_0B43AD582D3E470899FCCB58E44D3D49}

为充分验证下载、退出和自定义链接，Adobe 建议使用数据包分析器来实时检查链接。

<!-- 

downloads_validate.xml

 -->

由于文件下载、退出链接和自定义链接都不算作页面查看，因此无法使用 [!UICONTROL DigitalPulse Debugger] 工具来验证参数和变量设置。您必须使用[包分析器](../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258) 可查看跟踪链接数据。
