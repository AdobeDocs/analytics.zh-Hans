---
description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
keywords: Analytics 实施
seo-description: 通过动态变量，您可以将一个变量中的值复制到另一个变量，而无需在网站上的图像请求中多次键入完整的值。
solution: null
title: 动态变量
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountList

[!DNL AppMeasurement] for JavaScript 可以动态选择数据发送到的报表包。 变量包含用于确定目标报表包的规则。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | "" |

此变量与  and  variables. *`dynamicAccountSelection`**`dynamicAccountMatch`* The rules in  are applied if  is set to 'true,' and they apply to the section of the URL specified in .*`dynamicAccountList`**`dynamicAccountSelection`**`dynamicAccountMatch`*

If none of the rules in  matches the URL of the page, the report suite identified in  is used. *`dynamicAccountList`*`s_account`此变量中列出的规则按从左到右的顺序应用。如果页面 URL 与多个规则匹配，则使用最左侧的规则确定报表包。因此，应将较通用的规则移动到列表的右侧。

In the following examples, the page URL is  and  is set to true and  is set to `www.mycompany.com/path1/?prod_id=12345``dynamicAccountSelection`**`s_account``mysuitecom.`

| DynamicAccountList 值 | DynamicAccountMatch 值 | 接收数据的报表包 |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1、mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom、mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

## 语法和可能值

The`dynamicAccountList`变量为一组分号分隔的规则列表，每条规则表示为一个名称=值对。每个列表段都应包含以下项目：

* 一个或多个报表包 ID（以逗号分隔）
* 一个等号
* 一个或多个 URL 过滤器（以逗号分隔）

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

该字符串中只能使用标准的 ASCII 字符（不允许有空格）。

## 示例

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## 配置设置

无

## 缺陷、问题和提示

* 动态帐户选择不受 [AppMeasurement for JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* 如果页面 URL 与多个规则匹配，则使用最左侧的规则。
* 如果没有匹配的规则，则使用默认报表包。
* 如果页面被保存到某个人的硬盘，或通过基于 Web 的翻译引擎（如 Google 的翻译页面）进行了翻译，动态帐户选择可能无效。要进行更精确的跟踪，请在服务器端填充`s_account`变量。
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update  every time you obtain a new domain.*`dynamicAccountList`*
* 在尝试确定目标报表包时，请使用 [!DNL DigitalPulse Debugger]。The `dynamicAccountSelection` variable always overrides the value of `s_account`.
