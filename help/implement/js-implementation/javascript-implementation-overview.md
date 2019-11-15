---
description: 要开始使用 Analytics，必须将数据发送到报表包才能在报表中进行显示。
keywords: Analytics Implementation;javascript;javascript implementation;appmeasurement;download appmeasurement;Identity Service;visitorapi.js;caching;appmeasurement compression
solution: Analytics
title: JavaScript 实施概述
topic: Developer and implementation
uuid: bb661d8c-faf9-4454-ac3c-0c1a4c0a9336
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# JavaScript 实施概述

要开始使用 Analytics，必须将数据发送到报表包才能在报表中进行显示。

将数据发送到 [!DNL Analytics] 的最简单方法是使用 [Launch](/help/implement/implement-with-launch/create-analytics-property.md)。但是，在有些情况下，您可能需要使用更传统的 JavaScript 方法来实施 Analytics。

> [!NOTE]此部分介绍了实施 Analytics 的原有方法。所有 Analytics 客户都具有访问 [Launch](/help/implement/implement-with-launch/create-analytics-property.md) 的权限，这是部署 Experience Cloud 标记的标准方法。

## 实施步骤 {#section_73961BAD5BB4430A95E073DE5C026277}

要成功对页面实施代码收集数据，必须拥有访问主机服务器的权限，这样才能将新内容上载到您的网站。在现有网站上实施代码时，此方法也非常有用。

以下步骤详细说明了如何进行基本的 Analytics 实施。

| 任务 | 描述 |
|--- |--- |
| 1. 下载 AppMeasurement for JavaScript 和 ID 服务。 | 通过 Experience Cloud 登录到 Analytics。下载文件位于“Analytics”&gt;“管理员”&gt;“代码管理器”中。此下载 zip 文件中包含多个文件。其中，AppMeasurement.js 和 VisitorAPI.js 是实施 Analytics 时要用到的相关文件。 |
| 2. 设置 Identity Service。（以前称为访客 ID 服务） | See [Set up the Identity Service for Analytics](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| 3 更新 `AppMeasurement.js`。 | Copy the [example AppMeasurement.js code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) and paste it at the beginning of your `AppMeasurement.js` file. 请至少更新以下变量：<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>如果 [您不确定这些值中的任何一个](https://helpx.adobe.com/analytics/kb/determining-data-center.html) ，请参阅正确填充trackingServer和trackingServerSecure变量或联系客户关怀。 如果这些值设置错误，那么将无法通过您的实施来收集数据。</br> |
| 4. 托管 `AppMeasurement.js` 和 `VisitorAPI.js`。 | 这些核心 JavaScript 文件必须在一个您的所有站点页面都能访问的 Web 服务器上托管。下一步需要使用这些文件的路径。 |
| 5. 在所有网站页面上引用 `AppMeasurement.js` 和 `VisitorAPI.js`。 | <ul><li>通过将下面一行代码添加至每个页面的 `head` 或 `body` 标记中来加入访客 ID 服务。（`VisitorAPI.js` 必须在 `AppMeasurement.js` 之前加入）。<br>`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</br></li><li>通过将下面一行代码添加至每个页面的 `head` 或 `body` 标记中来加入 AppMeasurement for JavaScript：<br>`script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</br></li></ul> |
| 6. 更新并部署页面代码。 | Copy the [Example Page Code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) and paste it just after the opening `body` tag on each page you want to track. 请至少更新以下变量：<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s.pageName="INSERT-NAME-HERE"（例如，s.pageName=document.title）</li></ul> |
| 7. 使用 Experience Cloud 调试器验证数据是否已发送。 | 安装 [Experience Cloud 调试器](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2)。安装完成后，载入某个您已部署页面代码的页面，然后打开调试程序。调试程序会显示有关已发送的收集数据的详细信息。 |

## 缓存 {#section_4E2D1D962DF046418134C43CFC49AD4A}

JavaScript 文件首次加载后会缓存在访客的浏览器中，通常情况下，针对每个会话至多下载一次。即使网站上的每个页面都使用该文件，也不会为每个页面下载它。在大多数网站上，用户在每个会话内平均都会查看多个页面，因此将使用多次的 JavaScript 转移到此文件中可减少总体下载数据量。

## JavaScript for AppMeasurement 压缩 {#section_C10BBC84C81C414088F97363D29E021B}

如果您注重 H 代码的页面大小（AppMeasurement for JavaScript 1.0 已进行预压缩），Adobe 建议您考虑使用 GZIP 压缩文件。所有主要浏览器都支持 GZIP，而且与 JavaScript 压缩相比，其压缩和解压缩核心 [!DNL s_code.js] JavaScript 文件的效率更高。

以下链接可帮助说明在您的网站中如何使用 GZIP 功能压缩 [!DNL s_code.js] JavaScript 代码：

[Apache 模块 mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[通过 Tomcat 和 Flex 启用 gzip 压缩](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
