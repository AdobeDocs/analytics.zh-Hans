---
description: 如果其他访客 ID 方法失败，Adobe 会设置回退 Cookie 或使用 IP 地址和用户代理的组合来识别访客。
keywords: Analytics Implementation
solution: Analytics
title: 回退 ID 方法
topic: Developer and implementation
uuid: f242d481-81f0-4287-be4f-52fd03eb01fc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 回退 ID 方法

如果其他访客 ID 方法失败，Adobe 会设置回退 Cookie 或使用 IP 地址和用户代理的组合来识别访客。

## 回退访客识别方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x and JavaScript H.25.3 (released January 2013) contain a new fallback visitor identification method for visitors whose browser blocks the cookie set by Adobe's data collection servers (called `s_vi`). 之前，如果不能设置 Cookie，会在数据收集期间使用 IP 地址和用户代理字符串的组合来识别访客。

在这次更新后，只要遇到标准 `s_vi` Cookie 不可用的情况，即会在网站的域中通过一个随机生成的唯一 ID 创建一个回退 Cookie。这个 Cookie 名为 `s_fid`，具有 2 年期限，可用作今后的回退识别方法。在无法设置主 Cookie（`AMCV_` 或 `s_vi`）的情况下，此项更改应会提高访问和访客计数的准确性。

总访问量包含通过 `s_vi` Cookie 或使用回退方法识别的所有访客。

## IP 地址、用户代理、网关 IP 地址 {#section_104819D74C594ECE879144FCC5DEF4BF}

。如果无法设置 `AMCV_` 或 `s_vi` 和 `s_fid` Cookie，则可使用 IP 地址和用户代理的组合来识别访客。
