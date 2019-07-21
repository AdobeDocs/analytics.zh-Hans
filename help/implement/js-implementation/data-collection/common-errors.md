---
description: 以下章节说明了动态帐户中的常见错误。
keywords: Analytics 实施
seo-description: 以下章节说明了动态帐户中的常见错误。
seo-title: 常见错误
solution: Analytics
subtopic: 故障诊断
title: 常见错误
topic: 开发人员和实施
uuid: 04345355-60cc-4678-81c3-390c8672df1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 常见错误

以下章节说明了动态帐户中的常见错误。

## 硬编码帐户 {#section_FB6F89BF317F45D387C00986ACA690BC}

如果您希望始终向特定报表包发送数据，请将 [!UICONTROL s_dynamicAccountSelection] 设置为 false。或者，也可以彻底删除变量：

```js
var s_account="defaultreportsuiteid" 
REMOVE: s.dynamicAccountSelection=true 
REMOVE: s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

从以上示例中可知，在另外两个代码行被删除后，将会一直使用 defaultreportsuiteid。

## 代码放置 {#section_05375CB2EF5A414794BC8209C906AEEB}

Defining *`s_account`* after the lines of code does not override the dynamic account selection, as shown below.

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
s_account="anotherreportsuiteid" 
```

在以上示例中，帐户“anotherreportsuiteid”覆盖了“defaultreportsuiteid”，但是它不会覆盖 [!UICONTROL s.dynamicAccountList] 中发生的任何匹配。用于评估 [!UICONTROL s.dynamicAccountList] 的函数实际上在 .JS 文件中很晚才会执行。

## 多包标记 {#section_6C014FA9B87D4622B483BCDE4281D2A9}

多包标记可与动态帐户选择一起使用，如下所示。

```js
s.dynamicAccountSelection=true 
s.dynamicAccountList="suiteid1,suiteid2=client.com" 
```

## 动态帐户匹配 {#section_647AB47B38D640D6BCC853FDA4E4342D}

请不要在[!UICONTROL 动态帐户匹配]变量前后加引号。以下显示相关选项。

| 主机/域名 | 无 |
|---|---|
| 查询字符串 | s.dynamicAccountMatch=(window.location.search?window.location.search:"?") |
| 主机/域名和路径 | s.dynamicAccountMatch=window.location.host+window.lcation.pathname |
| 路径和查询字符串 | s.dynamicAccountMatch=window.location.pathname+(window.location.search?window.location.search""?") |
| 完整 URL | s.dynamicAccountMatch=window.location.href |

