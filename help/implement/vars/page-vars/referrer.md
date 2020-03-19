---
title: referrer
description: 覆盖自动收集的点击参照。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# referrer

该变 `referrer` 量将覆盖报告中自动收集的引用。 当引用程序可能丢失时，例如重定向或将访客临时转发给付款处理器时，此变量很有帮助。 此变量有助于填充“引用域”和“引用域”维。

## Adobe Experience Platform Launch中的参考

您可以在配置Analytics扩展时（全局变量）或根据规则设置引用。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Rules] 然后单击所需的规则（或创建规则）。
4. 在下 [!UICONTROL Actions]面，单击现有 [!UICONTROL Adobe Analytics - Set Variables] 操作或单击“+”图标。
5. 将下拉 [!UICONTROL Extension] 列表设置为Adobe Analytics，将其设置为 [!UICONTROL Action Type] to [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Referrer] section.

可以将引用设置为任何字符串值，包括数据元素。

## AppMeasurement中的s.referrer和启动自定义代码编辑器

变 `s.referrer` 量是包含上一页URL的字符串。 此变量最多可存储255字节；大于255字节的值会被截断。 AppMeasurement会自动将此变量设置为 `document.referrer`;除非要覆盖自动收集的值，否则无需设置此变量。

```js
s.referrer = "https://example.com";
```

避免将此变量设置为非URL值。

## 示例

许多组织都处理有关重定向的实施。 如果您的站点 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) 容纳了该实用程序，则可以使用该实用程序从URL获取引用。 确保URL对查询字符串中包含的任何值进行编码。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
