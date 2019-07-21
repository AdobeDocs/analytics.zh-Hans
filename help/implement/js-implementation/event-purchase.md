---
description: 对于购买事件，Analytics 变量将用于捕获特定的购买信息。s.purchaseID 变量用于序列化（消除重复）事件。
keywords: Analytics 实施
seo-description: 对于购买事件，Analytics 变量将用于捕获特定的购买信息。s.purchaseID 变量用于序列化（消除重复）事件。
seo-title: 购买活动
solution: Analytics
title: 购买活动
topic: 开发人员和实施
uuid: d90cdc7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 购买活动

对于购买事件，Analytics 变量将用于捕获特定的购买信息。s.purchaseID 变量用于序列化（消除重复）事件。

*`purchaseID`* 长度仅限20个字符。*`purchaseID`* 变量可序列化变量 [!UICONTROL s.events] 内传递的所有事件，并覆盖事件的任何序列化值。If *`purchaseID`* is left blank, each instance of the purchase event, even page reloads, is counted.

如果调用的购买事件没有 *`purchaseID`*，那么系统将根据 *`s.products`* 和 *`s.events`变量自动为其生成一个唯一值。*&#x200B;这个自动生成的 *`purchaseID`将作为访客浏览器内的 Cookie 值存储在本地，且不会发送给任何报表包表格。* Manually defined *`purchaseID`*s on the other hand are sent to a back-end table within the report suite. The last five purchases made by a visitor (with or without *`purchaseID`*) are stored in the local cookie.

如果访客执行了任何购买操作，则会核对下列事项：

* Do the *`purchaseID`* 是否匹配五个 Cookie 值中的任意一个？如果存在匹配，那么图像请求将被视为重复购买。包括购买事件在内的所有转化变量都不会显示在报表中。
* *`purchaseID`* 如果定义，它是否与报表包的后端表格中的值匹配？如果存在匹配，那么图像请求将被视为重复购买。包括购买事件在内的所有转化变量都不会显示在报表中。
* 如果 *`purchaseID`* 对于 Cookie 中最后 5 个存储值和报表包的 *`purchaseID`表而言都是唯一的，那么图像请求也将是唯一的，并会包含在报表中。*&#x200B;例如，如果五次购买均已包含在本地 Cookie 中，那么最早的一个将被覆盖。

特定的服务器端代码可用于生成嵌入 HTML 源代码中的唯一值（字母数字值）。一般而言，订购 ID 或类似的字母数字值，都是用于此目的。如果用户刷新页面，该值不会发生更改。以下是一个简短示例（注意&#x200B;*`purchaseID`*&#x200B;代码以粗体显示）：

## 语法{#section_4FBF138093BD41F59885D2ACC429FF5B}

```js
s.products="Category;ProductName;Qty;total_price [,Category2;ProductName2;Qty;total_price]" 
s.state="XX" 
s.zip="00000" 
 
<b>s.purchaseID="<%=getPurchaseID()%>"</b> 
s.events="purchase" 
```

## 示例 {#section_2CBA9B6386A146C0BEF375E1B55687BC}

```js
s.products="Footwear;Hiking Boots (1234);1;170.00" 
s.state="UT" 
s.zip="84097" 
s.purchaseID="12341234" 
s.events="purchase"
```

## 其他说明 {#section_5A0590B8FD4F40DC89776F55ED9DE668}

* 请确保使用服务器端代码来生成事件的唯一标识符。请不要使用 JavaScript 随机函数生成值，因为该函数在每次加载页面时都会生成唯一值（每个[!UICONTROL 实例]/[!UICONTROL pageview] 计数）。

* 唯一标识符适用于所有会话间的所有用户。因此，请确保标识符在这些用户和会话间是唯一的。例如，如果订购 ID 在 30 天后重复，请附加订购日期，以确保[!UICONTROL 订购 ID] 是唯一的。
* 序列化值可能是字母数字值，其长度最多为 20 个字符。这与 [!UICONTROL s.purchaseID] 的限制相同（在 G 代码中将 s. 替换为 s_）。
* [!UICONTROL s.purchaseID] 变量可序列化变量 [!UICONTROL s.events] 内传递的所有事件，并覆盖事件的任何序列化值。如果当前页面中使用了 [!UICONTROL s.purchaseID] 变量（在 G 代码中将 s. 替换为 s_），则不要将[!UICONTROL 事件序列化]用于任何事件。

