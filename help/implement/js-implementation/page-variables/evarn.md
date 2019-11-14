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


# eVarN

[!UICONTROL eVar] 变量用于生成自定义报表。

<!-- 

eVarN.xml

 -->

在为访客设置了 eVar 的值之后，将记住该值，直到值过期。eVar 值有效期间，访客遇到的任何成功事件将计入该 eVar 值。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 255 字节 | V1-v75（[或 v100 或 v250](/help/implement/js-implementation/c-variables/page-variables.md)） | 自定义转换 | "" |

**过期** {#section_6DB5882B960D4660AE248B91B76883C4}

[!UICONTROL eVar] 在指定的时间段后过期。eVar 过期后，将不再对成功事件计数。eVar 还可配置为在发生成功事件时过期。例如，如果有一个内部促销在一次访问结束时即告过期，对于此促销，将仅对该访问期间（在此期间有效）发生的购买或注册计数。

使 eVar 过期的方法有两种：

* 您可以将 eVar 设置为在指定的时间段或事件后过期。
* 您可以强制使 eVar 过期，在重新利用变量时这非常有用。

如果 eVar 在 5 月用于反映内部促销活动，并且在 21 天后过期，而在 6 月，又要使用它来捕获内部搜索关键词。在这种情况下，您应当在 6 月 1 日强制该变量过期，或重置该变量。这样做有助于从 6 月的报表中排除内部促销值。

**区分大小写** {#section_6E9145B7FCC2438E95BB35AAE3857412}

eVar 不区分大小写，但其第一个实例的首字母以大写显示。例如，如果 eVar1 的第一个实例被设置为“Logged In”，但随后的所有实例都作为“logged in”传递，报表始终显示“Logged In”作为 eVar 的值。

**计数器** {#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

eVar 最常用于保存字符串值，但也可以配置为用作计数器。在您尝试计入用户在某个事件前所执行的操作数时，使用 eVar 与计数器一样有用。例如，可以使用 eVar 捕获购买前的内部搜索数。访客每搜索一次时，eVar 包含值“+1”。如果访客在购买前搜索了四次，则将看到每个总计数的实例：1.00、2.00、3.00 和 4.00。但只有 4.00 针对购买事件（订购和收入量度）计数。只允许正数作为 eVar 计数器的值。

**子关系** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

[!UICONTROL 自定义 eVar] 报表的常见要求是能够按其他报表划分[!UICONTROL 自定义 eVar] 报表。例如，如果一个 eVar 包含性别，另一个包含薪水，您可能会问下面的问题：网站的女性访客中，年薪在 50,000 美元以上的女性访客可以产生多少收入。具有完全子关系的任何 eVar 都允许在报表中使用此类型的划分。例如，如果性别 eVar 启用了完全子关系，则可以按性别划分所有其他自定义 eVar 报表，并且可以按所有其他自定义 eVar 划分性别报表。要了解两个报表之间的关系，只需其中一个报表启用完全子关系。默认情况下，[!UICONTROL 促销活动]、[!UICONTROL 产品]和[!UICONTROL 类别]报表具有完全子关系（可以按促销活动或产品划分任何 eVar）。

**语法和可能值** {#section_BD46438B14F3488FB9AC42994C317B06}

虽然可以重命名 eVar，但在 JavaScript 文件中应始终按 eVarX 的形式表示，其中 X 是介于 1 和 75（[或 100，或 250](/help/implement/js-implementation/c-variables/page-variables.md)）的数字。

```js
s.eVarX="value"
```

在未用作计数器时，eVar 的限制与所有其他变量相同。如果 eVar 是“计数器”，则应接收数值，如“1”或“2.5”。如果小数超过两位，则 eVar 计数器舍入为两位小数。eVar 计数器不能包含负数。

**示例** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**配置设置** {#section_BD1FE63001C84D3DB69F3DEE243960B6}

可以在 [!UICONTROL Analytics &gt; 管理员 &gt; 报表包 &gt; 编辑设置 &gt; 转化 &gt; 转化变量]中配置 eVar。所有 eVar 都可以包含以下几个配置选项：[!UICONTROL 名称]、[!UICONTROL 类型]、[!UICONTROL 分配]、[!UICONTROL 过期时间设置]，或[!UICONTROL 重置]。下面分别介绍了每项配置设置。

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 设置 </th> 
   <th class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 名称 </td> 
   <td> 允许您更改 <span class="keyword">Analytics</span> 中 eVar 报表的名称。 <p>无论在 <span class="keyword">Analytics</span> 中为报表提供了什么样的名称，在 JavaScript 代码中，仍应以 s.eVarX 的形式表示 eVar。 </p> </td> 
  </tr> 
  <tr> 
   <td> 类型 </td> 
   <td> 允许您显示 eVar 是文本字符串，还是计数器。 </td> 
  </tr> 
  <tr> 
   <td> 分配 </td> 
   <td> 用于配置 eVar 的哪个值针对成功事件计数。 <p>如果“分配”被设置为“最近（上一个）”，则 B 获得计数。 </p> <p>如果“分配”被设置为“原始值（第一个）”，则 A 获得计数。 </p> <p>如果“分配”被设置为“线性”，则 A 和 B 分别获得购买值一半的计数。 </p> </td> 
  </tr> 
  <tr> 
   <td> 过期时间 </td> 
   <td> 让您确定 eVar 是在发生特定事件（如购买）时过期，还是在自定义或预定义的时间段后过期。 </td> 
  </tr> 
  <tr> 
   <td> 重置 </td> 
   <td> 通过选中 eVar 的“<span class="wintitle">重置</span>”复选框，并单击位于页面底部的“<span class="wintitle">保存</span>”，可以使 eVar 的所有值立即过期。发生这种情况后，只有 eVar 的新值会针对成功事件计数。 </td> 
  </tr> 
 </tbody> 
</table>

**缺陷、问题和提示** {#section_DA6912C802E445F986C6DE4234C6C737}

* 不同于 [!UICONTROL prop] 变量，eVar 变量不允许使用分隔值列表。如果使用值列表（如“one,two,three”）填充 eVar，则会在报表中显示完全相同的字符串。
* eVar 计数器不能包含负数。
