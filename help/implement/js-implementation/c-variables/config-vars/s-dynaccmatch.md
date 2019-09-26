---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountMatch

 变量使用 DOM 对象检索 中所有规则都适用的 URL 的区域。

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' 由于默认值为 [!DNL window.location.host]，因此[!UICONTROL 动态帐户选择]不需要此变量也可使用。有关其他信息，请参 [阅dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。

中找到的规 `dynamicAccountList` 则将应用于的值 `dynamicAccountMatch`。 如 `dynamicAccountMatch` 果仅包 [!DNL window.location.host] 含（默认），则中的规则 `dynamicAccountList` 仅适用于页面的域。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | window.location.host |

## 语法和可能值

The`dynamicAccountMatch`变量通常由提供 AppMeasurement for JavaScript 文件的 Adobe 顾问来填充。但下列值可随时应用。

```js
s.dynamicAccountMatch=[DOM object]
```

| 描述 | 值 |
|---|---|
| 域（默认） | window.location.host |
| 路径 | window.location.pathname |
| 查询字符串 | (window.location.search?window.location.search:"?") |
| 域和路径 | window.location.host+window.location.pathname |
| 路径和查询字符串 | window.location.pathname+(window.location.search?window.location.search:"?") |
| 完整 URL | window.location.href |

## 示例

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## 配置设置

无

## 缺陷、问题和提示

* 动态帐户选择不受 [AppMeasurement for JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* 页面被保存到硬盘时，[!DNL window.location.host] 为空，从而导致这些页面查看被发送到默认报表包（在 `s_account`).

* 在页面通过基于 Web 的翻译引擎（如 Google）进行了翻译时，[!UICONTROL 动态帐户选择]无法按预期使用。如需更精确的跟踪，请通过服务器端填充 [!UICONTROL s_account] 变量。
