---
title: 迁移到 AppMeasurement for JavaScript
description: 确定从 H 码迁移实施所需的内容。
feature: Implementation Basics
exl-id: ed606ab4-bd7d-4871-baa1-77e30fdd419e
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 91%

---

# 迁移到 AppMeasurement for JavaScript

如果您的实施仍使用 H 码，Adobe 强烈建议迁移到最新版 AppMeasurement。建议通过 [Adobe Experience Platform 中的标记](../launch/overview.md) 实施 Analytics，但也可以使用更新的 JavaScript 实施。

与 H 码相比，AppMeasurement 中存在以下显著更改：

* 比 H 码快 3 至 7 倍。
* 比 H 码更轻 - 21kb（未压缩）相对于 H 码的 33kb（未压缩）。
* 库和页面代码可以部署在 `<head>` 标记中。
* 现有的页面级别 H 码与 AppMeasurement 兼容。
* 该库提供了一些本地实用工具，用来获取查询参数、读取和写入 Cookie，以及执行高级链接跟踪。
* 该库不支持动态帐户配置变量（包括 `dynamicAccountSelection`、`dynamicAccountMatch` 和 `dynamicAccountList`）。

以下步骤概述了典型的迁移工作流程。

1. **下载新的 AppMeasurement 文件**：登录到 Adobe Analytics，然后导航到“管理员”>“所有管理员”>“代码管理器”以访问新文件。下载的压缩文件包含一个缩小的 `AppMeasurement.js` 文件，以及媒体和集成模块。
1. **将 `s_code.js` 自定义项复制到`AppMeasurement.js`**：将 `s_code.js` 中 `DO NOT ALTER ANYTHING BELOW THIS LINE` 部分之前的所有代码移到 `AppMeasurement.js` 的开头。
1. **更新所有插件**：确保使用`s_code.js`文件中列出的每个插件的最新版本。 此步骤包括媒体和集成模块。
1. **部署 AppMeasurement.js 文件**：将 `AppMeasurement.js` 文件上传到 Web 服务器。
1. **更新脚本引用以指向`AppMeasurement.js`**：确保所有页面都引用 `AppMeasurement.js` 而不是 `s_code.js`。

## 示例 Appmeasurement 代码

典型的 `AppMeasurement.js` 文件。确保在 `doPlugins` 函数上方设置配置变量。

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
made when instructed to do so by your Adobe Account Team.*/
s.trackingServer="example.data.adobedc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## 示例页面代码

在每个页面上加载的典型代码。

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

请务必在每个页面上也加入 `AppMeasurement.js` 和 `VisitorAPI.js` 的引用。有关更多信息，请参阅 [JavaScript 实施](/help/implement/js/overview.md)。
