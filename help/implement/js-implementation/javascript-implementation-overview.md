---
description: 要开始使用 Analytics，必须将数据发送到报表包才能在报表中进行显示。
keywords: Analytics实施；javascript；javascript实施；appasurement；下载AppMeasurement；标识服务；loc torapi. js；缓存；appasurement压缩
seo-description: 要开始使用 Analytics，必须将数据发送到报表包才能在报表中进行显示。
seo-title: JavaScript 实施概述
solution: Analytics
title: JavaScript 实施概述
topic: 开发人员和实施
uuid: bb661d8c-faf9-4454-ac3 c-0c1 a4 c0 a9336
translation-type: tm+mt
source-git-commit: 0a1db598a2b113ad71eb5d05d3f5c97f1af7cd62

---


# JavaScript 实施概述

要开始使用 Analytics，必须将数据发送到报表包才能在报表中进行显示。

The easiest and recommended way to send data to [!DNL Analytics] is by using [Launch](/help/implement/implement-with-launch/create-analytics-property.md). 但是，在有些情况下，您可能需要使用更传统的 JavaScript 方法来实施 Analytics。

>[!NOTE]
>
>本节介绍实施Analytics的传统方法。All Analytics customers have access to [Launch](/help/implement/implement-with-launch/create-analytics-property.md), which is the standard method to deploy Experience Cloud tags.

## 实施步骤 {#section_73961BAD5BB4430A95E073DE5C026277}

要成功对页面实施代码收集数据，必须拥有访问主机服务器的权限，这样才能将新内容上载到您的网站。在现有网站上实施代码时，此方法也非常有用。

以下步骤详细说明了如何进行基本的 Analytics 实施。

| 任务 | 描述 |
|--- |--- |
| 1. 下载AppMeasurement for JavaScript和ID服务。 | 通过Experience Cloud登录Analytics。下载文件可在“Analytics”(分析)&gt;“Admin”(管理)&gt;“Code Manager”(代码管理器)中找到。此下载 zip 文件中包含多个文件。其中，AppMeasurement.js 和 VisitorAPI.js 是实施 Analytics 时要用到的相关文件。 |
| 2. 设置标识服务。(以前称为访客ID服务) | 请参阅 [设置用于Analytics的Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| 3. Update `AppMeasurement.js`. | Copy the [example AppMeasurement.js code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) and paste it at the beginning of your `AppMeasurement.js` file. 请至少更新以下变量：<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>请参阅 [正确填充TrackingServer和TrackingServerSecure变量](https://helpx.adobe.com/analytics/kb/determining-data-center.html) ，如果您不确定其中任何值，请与客户关怀联系。如果这些值设置错误，那么将无法通过您的实施来收集数据。</br> |
| 4. 主持人 `AppMeasurement.js` 和 `VisitorAPI.js`。 | 这些核心 JavaScript 文件必须在一个您的所有站点页面都能访问的 Web 服务器上托管。下一步需要使用这些文件的路径。 |
| 5. Reference `AppMeasurement.js` and `VisitorAPI.js`  on all site pages. | <ul><li>Include the Visitor ID Service by adding the following line of code in the `head` or `body` tag on each page. (`VisitorAPI.js` must be included before `AppMeasurement.js`).<br>`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</br></li><li>Include AppMeasurement for JavaScript by adding the following line of code in the `head` or `body` tag on each page:<br>`script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</br></li></ul> |
| 6. 更新和部署页面代码。 | Copy the [Example Page Code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) and paste it just after the opening `body` tag on each page you want to track. 请至少更新以下变量：<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s. pageName=“INSERT-NAME-HERE”(例如，s. pageName= document. title)</li></ul> |
| 7. 使用Experience Cloud调试器验证数据是否正在发送。 | Install the [Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2). 安装完成后，载入某个您已部署页面代码的页面，然后打开调试程序。调试程序会显示有关已发送的收集数据的详细信息。 |

## 缓存 {#section_4E2D1D962DF046418134C43CFC49AD4A}

JavaScript 文件首次加载后会缓存在访客的浏览器中，通常情况下，针对每个会话至多下载一次。即使网站上的每个页面都使用该文件，也不会为每个页面下载它。在大多数网站上，用户在每个会话内平均都会查看多个页面，因此将使用多次的 JavaScript 转移到此文件中可减少总体下载数据量。

## JavaScript for AppMeasurement 压缩 {#section_C10BBC84C81C414088F97363D29E021B}

如果您注重 H 代码的页面大小（AppMeasurement for JavaScript 1.0 已进行预压缩），Adobe 建议您考虑使用 GZIP 压缩文件。所有主要浏览器都支持 GZIP，而且与 JavaScript 压缩相比，其压缩和解压缩核心 [!DNL s_code.js] JavaScript 文件的效率更高。

以下链接可帮助说明在您的网站中如何使用 GZIP 功能压缩 [!DNL s_code.js] JavaScript 代码：

[Apache 模块 mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[通过 Tomcat 和 Flex 启用 gzip 压缩](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
