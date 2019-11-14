---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# purchaseID

 用于防止在报表中对一次订购多次计数。

<!-- 

purchaseID.xml

 -->

任何时候，当您的网站使用了[!UICONTROL 购买]事件时，都应使用 *`purchaseID`* 变量。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 20 字节 | purchaseID | “转化”&gt;“购买”&gt;“收入转化” | "" |

当访客从您的网站上购买项目时，*`purchaseID`*&#x200B;将在“谢谢”页面中被填充（该页面与触发[!UICONTROL 购买]事件的位置相同）。如果 *`purchaseID`* 被填充，则“感谢”页面中的产品将被计数，并且针对每个 *`purchaseID`* 仅计数一次。这一点至关重要，因为许多访问您网站的访客都会出于各自的目的保存“谢谢”或“确认页面”。The *`purchaseID`*&#x200B;可防止每次查看页面时都对购买计数。

使用 *`purchaseID`* 时，除可以避免将购买数据计数两次外，还可以防止所有转化数据在报表中被重复计数。

**语法和可能值** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

*`purchaseID`* 必须在 20 字符以内，而且必须为标准的 ASCII 字符。

**示例** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**配置设置** {#section_1808631C96674380BF9C4A6D9A2C568E}

无

**缺陷、问题和提示** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

*`purchaseID`* 变量允许页面中的所有转化变量在报表中仅被计数一次。
