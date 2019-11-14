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


# propN

属性 ([!UICONTROL prop]) 变量用于在[!UICONTROL 流量模块]建立自定义报表。

<!-- 

propN.xml

 -->

props 变量可用作路径报表或关联报表的计数器（计算一个页面查看的发送次数）。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | c1 - c75 | 自定义流量 | "" |

**语法和可能值** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

除标准变量限制以外，[!UICONTROL 属性]变量无其他限制。

**示例** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**配置设置** {#section_25FDEB6ECA8242A2A44EE540C083078A}

要了解有关显示 prop 变量的[!UICONTROL 访问]、[!UICONTROL 访客]和[!UICONTROL 路径]量度的信息，请联系 Adobe [!UICONTROL 客户关怀]部门。
