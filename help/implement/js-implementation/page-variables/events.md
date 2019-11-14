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



# 事件

 变量用于记录常见的购物车成功事件以及自定义成功事件。

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大大小 </th> 
   <th class="entry"> 调试程序参数 </th> 
   <th class="entry"> 填充报表 </th> 
   <th class="entry"> 默认值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 无限制 </td> 
   <td> events </td> 
   <td> <p>购物车事件 </p> <p>自定义事件 </p> </td> 
   <td> 不适用 </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL 事件]可视为网站内部的“里程碑”。成功事件通常在流程的最终确认页面上填充，如注册过程或新闻稿注册。使用以下可能值部分中定义的字面值填充 events 变量，可定义自定义事件。

成功事件默认配置为&#x200B;*计数器*&#x200B;事件。计数器事件可计算成功事件的设置次数 (x+1)。事件还可配置为&#x200B;*数值*&#x200B;事件。数值事件允许您指定要增加的数量（在计算动态值或不定值时可能有用，例如由内部搜索返回的结果数量）。

最终事件类型&#x200B;*货币*&#x200B;允许您定义要添加的数量（类似于数值事件），但在报表中显示为货币，并需符合基于 s.*`currencyCode`*&#x200B;值的货币兑换和报表包的默认货币设置。有关使用数值和货币事件的其他信息，请参阅[产品](/help/implement/js-implementation/c-variables/page-variables.md)。

**配置变量** {#section_9195286C34C54B02B2598E2B856492C3}

[!UICONTROL s.events] 变量默认为在所有实施中启用。七个预配置转化事件在所有新报表包中自动启用。新的自定义事件（event1- [event100 或 event1000](/help/implement/js-implementation/c-variables/page-variables.md)）可由管理员级别的任何用户通过使用 Admin Console 来启用。

**可能值** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

以下是事件变量的可能值列表：

| 事件 | 描述 | 填充报表 |
|---|---|---|
| prodView | 产品查看次数 | 产品 |
| scOpen | 打开/启动新购物车 | 购物车 |
| scAdd | 向购物车添加项目 | 购物车加货 |
| scRemove | 从购物车中删除项目 | 购物车减货 |
| scView | 查看购物车 | 购物车查看 |
| scCheckout | 开始结账过程 | 结账 |
| purchase | 购买（订购）完成 | 订购 |
| event1 至 event1000（event100 对应点产品） | 自定义事件 | 自定义事件 |

**语法和示例** {#section_45A159DF00114066B8551DDEB15E084C}

在以逗号隔开的列表（如果有多个事件需要传递）中，将所需的事件置于 [!UICONTROL s.events] 变量中，可设置计数器事件。

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

如果是在 H23 或更高级别的代码中，则可以赋予计数器事件大于一的整数。

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

实施分配了整数值的计数器事件，会检查事件是否在图像请求内触发了多次。计数器事件不允许有小数，如果您需要此功能，建议使用数值事件。数值和货币事件必须包含在 [!UICONTROL s.events] 变量中，即使它们经常会收到 [!UICONTROL s.products] 变量中的数字值（例如 24.99）。这允许您将特定的数值和货币值与各个产品条目关联。

**事件序列化** {#section_A89488EF4471405AAFC4D6DD05E77621}

默认情况下，某事件在您的网站每设置一次，都会计为一个事件。

请参阅[事件序列化](/help/implement/js-implementation/event-serialization.md)，以了解更多信息。

**语法** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**示例** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
