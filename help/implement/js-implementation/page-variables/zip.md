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


# zip

zip 和 state 变量是转化变量。

<!-- 

zip.xml

 -->

这些变量与 eVar 一样均可捕获事件，但不同之处在于，这些变量不是永久性变量。The *`zip`* 和 *`state`* 变量与 eVar 类似，都会立即过期。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 50 字节 | zip | “转化”&gt;“访客资料”&gt;“邮政编码” | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. 例如，如果使用 *`zip`* 变量来根据邮政编码比较转化率，则需在结账流程每一页面填充 *`zip`* 变量。Adobe 推荐使用帐单地址作为邮政编码来源。您也可以选择使用发货地址（假设该订单只有一个发货地址）。媒体网站可选择使用 *`zip`* 和 *`state`* 进行注册或广告点进跟踪。

**语法和可能值** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

*`zip`* 变量不限定任何值或格式限制。*`zip`* 除标准变量限制以外，无其它限制。

**示例** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**配置设置** {#section_7987084EECC34DD38B643B94F82385CA}

无

**缺陷、问题和提示** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* 在每个触发相关事件的页面中填充 [!UICONTROL zip] 变量（例如，每个结帐流程页面）。
* *`zip`* 和 *`state`* 变量的操作方式类似于“页面查看次数”上过期的 eVar。

