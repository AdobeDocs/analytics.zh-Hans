---
title: 迁移到 AppMeasurement for JavaScript
description: 确定从H代码迁移实施所需的内容。
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# 迁移到 AppMeasurement for JavaScript

如果您的实施仍使用H代码，Adobe强烈建议迁移到最新版AppMeasurement。 建议通过 [Adobe Experience Platform Launch实施Analytics](../launch/overview.md) ，但可以使用更新的JavaScript实施。

与H代码相比，AppMeasurement中存在以下显着更改：

* 比H代码快3-7倍。
* 比H代码轻- 21kb未压缩代码，而H代码为33kb未压缩代码。
* 库和页面代码可以部署在 `<head>` 标记中。
* 现有的页面级H代码与AppMeasurement兼容。
* 该库提供了一些本地实用工具，用来获取查询参数、读取和写入 Cookie，以及执行高级链接跟踪。
* 库不支持动态帐户配置变量( `dynamicAccountSelection`包括、 `dynamicAccountMatch`和 `dynamicAccountList`)。
* 但不支持调查模块。

以下步骤概述了典型的迁移工作流程。

1. **下载新的AppMeasurement文件**:登录到Adobe Analytics，然后导航到“管理员”>“代码管理器”，即可访问新文件。 下载的压缩文件包含一个缩 `AppMeasurement.js` 小的文件，以及媒体和集成模块。
1. **将自定`s_code.js`义复制到`AppMeasurement.js`**:将所有代码移到`DO NOT ALTER ANYTHING BELOW THIS LINE`部分`s_code.js`之前的开头`AppMeasurement.js`。
1. **更新所有插件**:确保您使用的是文件中列出的每个插件的最新版本 `s_code.js` 。 这包括媒体和集成模块。
1. **部署AppMeasurement.js文件**:将文件 `AppMeasurement.js` 上传到Web服务器。
1. **更新脚本引用以指向`AppMeasurement.js`**:确保所有页面都引`AppMeasurement.js`用而不是引`s_code.js`用。

## 示例Appmeasurement代码

典型文 `AppMeasurement.js` 件。 确保在函数上方设置配置变 `doPlugins` 量。

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your account manager.*/
s.trackingServer="example.sc.omtrdc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## 示例页面代码

每页加载的典型代码。

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

请务必在每个页面上也加入 `AppMeasurement.js` 和 `VisitorAPI.js` 的引用。有关更 [多信息，请参阅](/help/implement/js/overview.md) JavaScript实施。
