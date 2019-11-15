---
description: 一个 .js 文件，可对其进行配置以自动选择报表包 ID。
keywords: Analytics Implementation
solution: Analytics
title: 报表包 ID - 动态帐户
topic: Developer and implementation
uuid: 763a9741-309d-4795-8819-6543866047d5
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 报表包 ID - 动态帐户

一个 .js 文件，可对其进行配置以自动选择报表包 ID。此 .js 文件可基于 URL 自动将图像请求发送到相应的报表包中。例如，如果 URL 为 `www.mysite.com`，则图像请求自动发送至报表包 A。如果 URL 为 `www.mysite1.com`，则图像请求将自动发送至报表包 B。

这些字符串可在以下任何位置找到：

* 主机/域（默认设置）
* 路径
* 查询字符串
* 主机/域名和路径
* 路径和查询字符串
* 完整 URL

有关配置 [!DNL Analytics] 以自动选择[!UICONTROL 报表包 ID] 的详细信息，请联系 Adobe 实时支持。

## 定义要匹配的 URL 区段 {#section_8099162F75F641CFBE46FD814450EF36}

基于以下示例 URL，下面显示了 URL 的某些部分，以及必须设置的 `s.dynamicAccountMatch` 变量。（默认设置 - 如果 `s.dynamicAccountMatch` 未定义 -为只搜索主机/域名）。示例 URL：`https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321`

| 部分 | 示例（参见上面） |
|---|---|
| 主机/域名 | `www.client.com` |
| 路径 | `directory1/directory2/filename.html` |
| 查询字符串 | `param1=1234&param2=4321` |
| 主机/域名和路径 | `www.client.com/directory1/directory2/filename.html` |
| 路径和查询字符串 | `directory1/directory2/filename.html?param1=1234&param2=4321` |
| URL | `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321` |
| 部分 | `s.dynamicAccountmatch` |
| 主机/域名 | 未定义 |
| 路径 | `window.location.pathname` |
| 查询字符串 | `(window.location.search?window.location.search:"?")` |
| 主机/域名和路径 | `window.location.host+window.location.pathname` |
| 路径和查询字符串 | `window.location.pathname+(window.location.search?window.location.search:"?")` |
| URL | `window.location.href` |

请仔细研究下面的示例：

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com"`
* `s.dynamicAccountMatch=window.location.host+window.location.pathname`

## 多规则 {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

如果选择多规则（参见上面的示例），则按从左到右的顺序执行这些规则。一旦匹配成功，规则即会停止，如下所示（采用给定的规则集）。

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"`

此代码首先检查以确定主机/域名内是否存在 `qa.client.com`。如果存在，则选中报表包 `devreportsuite1`，并且匹配停止。以分号隔开各项多规则。

## 默认报表包 {#section_0360D724929348B0B211708B5BA15647}

`s_account` 变量可最先设置，并在找不到任何指定字符串的情况下充当默认值。示例如下：

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

在以上示例中，如果主机/域名不包含 `qa.client.com` 或 `client.com`，将使用报表包 *defaultreportsuiteid*。
