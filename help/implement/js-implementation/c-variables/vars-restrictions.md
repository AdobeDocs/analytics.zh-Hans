---
description: JavaScript 变量中完全不许使用的字符和字符串。
keywords: Analytics 实施
seo-description: JavaScript 变量中完全不许使用的字符和字符串。
seo-title: 非法JavaScript字符
solution: Analytics
subtopic: 变量
title: 非法JavaScript字符
topic: 开发人员和实施
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 非法JavaScript字符

JavaScript 变量中完全不许使用的字符和字符串。

* Tab (0x09)
* 回车 (0x0D)
* 换行 (0x0A)
* 代码超过 127 的 ASCII 字符（除非启用多字节字符且适当填充&#x200B;*`charSet`*）
* HTML tags (e.g. <b></b> or &amp;#153)

许多变量，尤其是产品、层级和事件另有其他限制或语法要求。有关各个变量的限制和语法要求，请参阅&#x200B;*`s_account`*&#x200B;变量参数对应的章节。
