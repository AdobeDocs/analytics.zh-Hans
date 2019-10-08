---
description: 对于购买事件，Analytics 变量将用于捕获特定的购买信息。s.purchaseID 变量用于序列化（消除重复）事件。
keywords: Analytics 实施
seo-description: 对于购买事件，Analytics 变量将用于捕获特定的购买信息。s.purchaseID 变量用于序列化（消除重复）事件。
seo-title: 购买事件
solution: Analytics
title: 购买事件
topic: 开发人员和实施
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: e21bb18dd0d0eb13222c655091c3a87939a0351d

---


# 购买事件

对于购买事件，Analytics 变量将用于捕获特定的购买信息。`s.purchaseID` 变量用于序列化（消除重复）事件。

如果调用的购买事件没有 `purchaseID`，那么系统将根据 `s.products` 和 `s.events` 变量自动为其生成一个唯一值。此自动生成的购买ID作为Cookie值存储在访客的浏览器中的本地，不会发送给Adobe。 另一方面，手动定义的购买ID将发送给Adobe。 访客（无论有无购买ID）最后五次购买都存储在本地Cookie中。

如果访客执行了任何购买操作，则会核对下列事项：

* 是否 购买ID是否与五个Cookie值中的任意一个匹配？ 如果存在匹配，那么图像请求将被视为重复购买。包括购买事件在内的所有转化变量都不会显示在报表中。
* 如果 `s.purchaseID` 已定义，它是否与报告套件中已收集的任何值匹配？ 如果存在匹配，那么图像请求将被视为重复购买。包括购买事件在内的所有转化变量都不会显示在报表中。

特定的服务器端代码可用于生成嵌入 HTML 源代码中的唯一值（字母数字值）。一般而言，订购 ID 或类似的字母数字值，都是用于此目的。如果用户刷新页面，该值不会发生更改。

## 语法

```js
s.purchaseID="12345678";
```

## 示例

```js
s.products="Footwear;Hiking Boots;1;170.00";
s.purchaseID="12345678";
s.events="purchase";
```

## 其他说明

* 请勿使用JavaScript随机化函数生成一个数字，该数字在每次加载页面时都会生成唯一的数字。 Adobe建议使用数据层存储给定的购买ID。
* 唯一标识符适用于所有会话间的所有用户。确保所有购买ID都是真正唯一的。
* 有效值是长度不超过20个字符的字母数字值。
* `s.purchaseID``s.events` 变量可序列化变量   内传递的所有事件，并覆盖事件的任何序列化值。如果当前页 [!UICONTROL 面上使用了变量] ，则不要对任何事 `s.purchaseID` 件使用事件序列化。
* If the `s.purchaseID` variable is left blank, each instance of the purchase event, even page reloads, is counted.
