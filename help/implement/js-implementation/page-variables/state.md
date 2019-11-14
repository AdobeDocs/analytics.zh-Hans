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


# state

zip 和 state 变量是转化变量。

<!-- 

state.xml

 -->

这些变量与 eVar 一样均可捕获事件，但不同之处在于，这些变量不是永久性变量。The *`zip`* 和 *`state`* 变量与 eVar 类似，都会立即过期。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 50 字节 | state | 转化 &gt; 访客资料 &gt; 访客所在州 | "" |

由于 *`state`* 和 *`zip`* 变量会立即过期，因此，与之关联的事件就是在填充这些变量的同一页面上被触发的事件。例如，如果使用 *`state`* 变量来根据州比较转化率，则需在结账流程每一页面填充 *`state`* 变量。对于转化网站，Adobe 建议使用帐单地址作为邮政编码的来源，但您也可以选择使用送货地址（假定订单上只有一个送货地址）。媒体网站可选择使用 *`zip`* 和 *`state`* 进行注册或广告点进跟踪。

**语法和可能值** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

*`state`* 变量不限定任何特殊值或格式限制。*`state`* 除标准变量限制以外，无其它限制。

**示例** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**配置设置** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

无

**缺陷、问题和提示** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* 在每个触发相关事件的页面中填充 *`state`*（例如，每个结帐流程页面）。
* *`zip`* 和 *`state`* 变量的操作方式类似于“页面查看次数”上过期的 eVar。
