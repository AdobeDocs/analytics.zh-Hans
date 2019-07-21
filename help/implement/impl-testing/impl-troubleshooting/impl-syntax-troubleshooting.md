---
description: 下表显示了正确代码和错误代码之间的差异。
keywords: Analytics 实施
seo-description: 下表显示了正确代码和错误代码之间的差异。
seo-title: 常见语法错误
solution: Analytics
subtopic: 故障诊断
title: 常见语法错误
topic: 开发人员和实施
uuid: 9845dcb9-9f10-4f65f65d43d-2ef41eda122
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 常见语法错误

下表显示了正确代码和错误代码之间的差异。

| 错误 | 正确 |
|---|---|
| prop1 | s.prop1（使用“s.”） |
| s.evar1 | s.eVar1（使用正确的大小写） |
| s.pagetype='errorpage'; | s.pageType='errorPage';（使用正确的大小写） |
| s.tl(this,o,pageA) | s.tl(this,'o','pageA');（正确使用单引号） |
| s.events='event1'; s.events='event2'; | s.events='event1,event2';（正确格式） |
| s.pageName="John"（智能引号打开） | s.pageName="John"（智能引号关闭） |
| s.products="shoes,UX4879,1,19.99" | s.products="shoes;UX4879;1;19.99"（使用分号，而不是逗号） |
| s.products=";MacBook Air;1;$1999.99" | s.products=";MacBook Air;1;1999.99"（不要使用美元号） |
| s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.9489183" | s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.95"（舍入或截断长价格） |
| var s_account="rsid1, rsid2" | var s_account="rsid1,rsid2"（标记多个包时报表包 ID 之间不应有空格） |
| s.events="event1, event2" | s.events="event1,event2"（标记多个事件时事件 ID 之间不应有空格） |
| s.products="product name" | s.products=";product name"（未列出产品类别时使用分号） |

## 其他说明 {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

将结束 HTML 注释放在 Adobe 代码的最尾部（即使使用的是脚本的 NOSCRIPT 部分）。
