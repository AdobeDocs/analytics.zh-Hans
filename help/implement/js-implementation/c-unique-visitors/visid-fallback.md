---
description: 如果其他访客 ID 方法失败，Adobe 会设置回退 Cookie 或使用 IP 地址和用户代理的组合来识别访客。
keywords: Analytics 实施
seo-description: 如果其他访客 ID 方法失败，Adobe 会设置回退 Cookie 或使用 IP 地址和用户代理的组合来识别访客。
seo-title: 回退ID方法
solution: Analytics
title: 回退ID方法
topic: 开发人员和实施
uuid: f242d481-81f0-4287-be4 f-52fd03 eb01 fc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 回退ID方法

如果其他访客 ID 方法失败，Adobe 会设置回退 Cookie 或使用 IP 地址和用户代理的组合来识别访客。

## 回退访客识别方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x 和 JavaScript H.25.3（2013 年 1 月发布）包含一个新的回退访客识别方法，专门针对某些访客的浏览器会阻止由 Adobe 数据收集服务器设置的 Cookie（称为 `s_vi`）的情况。之前，如果不能设置 Cookie，会在数据收集期间使用 IP 地址和用户代理字符串的组合来识别访客。

在这次更新后，只要遇到标准 `s_vi` Cookie 不可用的情况，即会在网站的域中通过一个随机生成的唯一 ID 创建一个回退 Cookie。这个 Cookie 名为 `s_fid`，具有 2 年期限，可用作今后的回退识别方法。This change should result in increased accuracy in visit and visitor counts in situations where the primary cookie ( `AMCV_` or `s_vi`) cannot be set.

总访问量包含通过 `s_vi` Cookie 或使用回退方法识别的所有访客。

## IP 地址、用户代理、网关 IP 地址 {#section_104819D74C594ECE879144FCC5DEF4BF}

。If the `AMCV_` or `s_vi` and the `s_fid` cookies cannot be set, visitors are identified using a combination of IP address and User Agent.
