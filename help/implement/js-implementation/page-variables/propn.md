---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# propN

属性 (`prop`) 变量用于在流量模块建立自定义报表。

<!-- 

propN.xml

 -->

props 变量可用作路径报表或关联报表的计数器（计算一个页面查看的发送次数）。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | c1 - c75 | 自定义流量 | "" |

**语法和可能值**

```js
s.propN="value"
```

除标准变量限制以外，[!UICONTROL 属性]变量无其他限制。

**示例**

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**配置设置**

要了解有关显示 变量的访问、访客和路径量度的信息，请联系 Adobe `prop`客户关怀部门。
