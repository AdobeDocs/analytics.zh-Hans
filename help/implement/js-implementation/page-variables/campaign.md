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



# campaign

 变量识别将访客吸引到您网站的营销活动。 的值通常取自查询字符串参数。

<!-- 

campaign.xml

 -->

**参数**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
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
   <td> <p>255 字节 </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>“转化”&gt;“促销活动”&gt;“跟踪代码” </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

营销活动中的每个元素都应有一个关联的唯一跟踪代码。例如，付费搜索引擎关键词的跟踪代码为 112233。当用户点击跟踪代码为 112233 的关键词，并路由到相应的网站时，*`campaign`*&#x200B;变量会记录该跟踪代码。

可以使用以下两种主要方法填充 *`campaign`* 变量：

* [!UICONTROL getQueryParam] 插件（在 JavaScript 文件中使用）从 URL 中检索查询字符串参数。有关 [!UICONTROL getQueryParam] 插件的详细信息，请参阅 [实施插件](/help/implement/js-implementation/plugins/impl-plugins.md)。

* 为网页上的 HTML 中的 *`campaign`* 变量分配一个值。

无论使用哪种方法填充 *`campaign`* 变量，“返回”按钮流量都可能导致促销活动元素的实际点进次数虚增。

例如，访客通过点击付费搜索关键词进入您的网站。在访客转至登陆页面时，URL 中的查询字符串参数会识别此关键词的跟踪代码。接着，访客点击另一个页面的链接，但立刻点击“返回”按钮返回到登陆页面。在访客第二次转至登陆页面时，URL 中的查询字符串参数会再次识别跟踪代码。因此将记录第二次点进，从而导致点进次数虚增。

为了避免点进次数虚增，Adobe 建议使用 [!UICONTROL getValOnce] 插件强制使每次促销活动点进在每个会话中仅计数一次。有关 [!UICONTROL getValOnce] 插件的详细信息，请参阅 [实施插件](/help/implement/js-implementation/plugins/impl-plugins.md)。

**语法和可能值** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

*`campaign`* 变量的限制与所有其他变量相同。Adobe 建议将值限定为标准 ASCII 字符。

**区分大小写** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

eVar 不区分大小写，但其第一个实例的首字母以大写显示。例如，如果 eVar1 的第一个实例被设置为“Logged In”，但随后的所有实例都作为“logged in”传递，报表始终显示“Logged In”作为 eVar 的值。

**示例** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**配置设置** {#section_4083F281968443169EAF8C0E8529D7BC}

一个用户的每个促销活动值均有效，并针对该用户的活动和成功事件进行计数，直到其过期为止。您可以在管理控制台中更改促销活动变量的过期日期。

**缺陷、问题和提示** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* 为避免点进次数虚增，请使用 [!UICONTROL getValOnce] 插件使促销活动点进在每个会话中仅计数一次。有关 [!UICONTROL getValOnce] 插件的详细信息，请参阅 [实施插件](/help/implement/js-implementation/plugins/impl-plugins.md)。

* 有关跟踪营销活动和关键词购买的详细信息，请参阅[促销活动](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html)。
* 使用 [!DNL DigitalPulse Debugger] 可查看促销活动的实际值（调试器中的 v0）。如果 v0 未出现在调试器中，表示未记录该页面的促销活动数据。
