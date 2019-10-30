---
description: 'null'
seo-description: 'null'
seo-title: PHP
solution: Analytics
subtopic: 发行说明
title: PHP
topic: 开发人员和实施
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# PHP{#php}

> [!NOTE]要找到当前库版本，请打开调试记录。

## 版本 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

发行日期：**2014 年 8 月**

* 执行了某些内部更改以支持即将推出的功能。

## 版本 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

发行日期：**2012 年 7 月**

* 新增对 IIS 中 $_SERVER['HTTPS'] 返回的 "off" 的检查。如果没有此检查，无论请求是通过 HTTP 还是 HTTPS 进行，对布尔值 ((bool)$_SERVER['HTTPS']) 的类型转换会在 IE 中返回 true。这会导致非安全页面尝试做出安全图像请求。

## 版本 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

PHP 1.1 的测量库包含来自版本 1.0 的以下更新：

* 更精确的地域划分（在启用了 `sendFromServer` 的情况下）。
* 修复了相应错误，以便用户现在能够附加到 `userAgent` 变量。
* 图像信标现在可与更多移动浏览器兼容。
* 在启用了移动设备的情况下，`imageDimensions` 变量现在默认为 5x5。
* 优化了机器人检测列表。
* 在启用 `debugTracking` 和 `sendFromServer` 的情况下添加了调试信息（HTTP 标头、响应、错误等）。

* 添加了 `debugFilename` 变量（在启用了 `sendFromServer` 的情况下）。

* 在 `pagename` 和 `pageURL` 均未设置的情况下，pagename 变量默认为 `$_SERVER['SCRIPT_NAME']`。

* 对 PHP 的 CGI 实施提供完全支持。
* 性能增强。

