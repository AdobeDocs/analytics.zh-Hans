---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics 实施
seo-description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
seo-title: 页面变量
solution: Analytics
subtopic: 变量
title: 页面变量
topic: 开发人员和实施
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 页面变量

页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

 变量显示浏览器窗口的高度。

<!-- 
browserheight.xml
-->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此变量应仅读取且不应设置。

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

**参数**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> 查询参数 </th> 
   <th class="entry"> 值 </th> 
   <th class="entry"> 示例 </th> 
   <th class="entry"> 受影响的报表 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>正整数 </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>“流量”&gt;“技术”&gt;“浏览器高度” </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

 变量显示浏览器窗口的宽度。

<!-- 

browserwidth.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此变量应仅读取且不应设置。

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

**参数**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>查询参数</b> </p> </td> 
   <td> <p> <b>值</b> </p> </td> 
   <td> <p> <b>示例</b> </p> </td> 
   <td> <p> <b>受影响的报表</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>正整数 </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>“流量”&gt;“技术”&gt;“浏览器宽度” </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

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

There are two main ways to populate the *`campaign`* variable:

* [!UICONTROL getQueryParam] 插件（在 JavaScript 文件中使用）从 URL 中检索查询字符串参数。有关 [!UICONTROL getQueryParam] 插件的详细信息，请参阅 [实施插件](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* 为网页上HTML *`campaign`* 中的变量赋值。

使用任一填充变量的方 *`campaign`* 法，“返回”按钮流量都可能会夸大营销活动元素的实际点进次数。

例如，访客通过点击付费搜索关键词进入您的网站。在访客转至登陆页面时，URL 中的查询字符串参数会识别此关键词的跟踪代码。接着，访客点击另一个页面的链接，但立刻点击“返回”按钮返回到登陆页面。在访客第二次转至登陆页面时，URL 中的查询字符串参数会再次识别跟踪代码。因此将记录第二次点进，从而导致点进次数虚增。

为了避免点进次数虚增，Adobe 建议使用 [!UICONTROL getValOnce] 插件强制使每次促销活动点进在每个会话中仅计数一次。有关 [!UICONTROL getValOnce] 插件的详细信息，请参阅 [实施插件](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**语法和可能值** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

The *`campaign`* variable has the same limitations as all other variables. Adobe 建议将值限定为标准 ASCII 字符。

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

* 为避免点进次数虚增，请使用 [!UICONTROL getValOnce] 插件使促销活动点进在每个会话中仅计数一次。有关 [!UICONTROL getValOnce] 插件的详细信息，请参阅 [实施插件](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* 有关跟踪营销活动和关键词购买的详细信息，请参阅[促销活动](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html)。
* 使用 [!DNL DigitalPulse Debugger] 可查看促销活动的实际值（调试器中的 v0）。如果 v0 未出现在调试器中，表示未记录该页面的促销活动数据。

## channel {#concept_C7770B8C15724A99B10F8F468AF82D0D}

 变量最常用于识别网站的区域。

<!-- 

channel.xml

 -->

例如，某商家的网站可能设有电器、玩具或服装等区域。某个媒体网站可能设有新闻、体育或商业信息等区域。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | CH | 网站内容 &gt; 网站区域 | "" |

Adobe 建议填充每个页面的渠道变量。您还可以启用&#x200B;*`channel`*&#x200B;和[!UICONTROL 页面名称]变量之间的关联。

When sections have one or more levels of subsections, you can show those sections in the *`channel`* variable or use separate variables to identify levels.

**语法和可能值** {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

The *`channel`* variable has no extra limitations on its values.

**示例** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**缺陷、问题和提示** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

If your site contains multiple levels, you can use the *`hierarchy`* or another variable to designate those levels. The *`channel`* value does not persist, but the success events fired on the same page are attributed to the *`channel`* value.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

 变量用于显示屏幕上各像素颜色的位数。

<!-- 

colordepth.xml

 -->

例如，32 表示屏幕上显示的是 32 位色。此变量在&#x200B;*`doPlugins`*&#x200B;运行之前，填充于页面代码之后。

>[!NOTE]
>
>This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. 此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| c | 8、16 和 32 | 32 | “流量”&gt;“技术”&gt;“显示器颜色深度” |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

 变量在 Internet Explorer 中用来指示浏览器是配置的 LAN 连接，还是调制解调器连接。

<!-- 

conntype.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此变量应仅读取且不应设置。

You may read these values and copy them into `props/eVars`, but you should never alter them. 此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| ct | lan 或 modem | lan | “流量”&gt;“技术”&gt;“连接类型” |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

 变量表示 JavaScript 是否可设置第一方会话 Cookie。

<!-- 

cookiesenabled.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. 此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 |
|---|---|---|
| k | Y 或 N | Y |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

（已弃用） 变量让您可以选择要将数据发送到的数据中心。

<!-- 

dc.xml

 -->

>[!NOTE]
>
>dc 变量已弃用。您应将所有实施的 *`trackingServer`都设置为 s_code.js 中代码管理器生成的值。*

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | 112 |

数据中心在&#x200B;*`dc`*&#x200B;变量中进行识别，以匹配 [!UICONTROL ActionSource]。

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

[!UICONTROL eVar] 变量用于生成自定义报表。

<!-- 

eVarN.xml

 -->

在为访客设置了 eVar 的值之后，将记住该值，直到值过期。eVar 值有效期间，访客遇到的任何成功事件将计入该 eVar 值。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 255 字节 | V1-v75 ( or v100 or v250)[](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28) | 自定义转换 | "" |

**Expiration** {#section_6DB5882B960D4660AE248B91B76883C4}

[!UICONTROL eVar] 在指定的时间段后过期。eVar 过期后，将不再对成功事件计数。eVar 还可配置为在发生成功事件时过期。例如，如果有一个内部促销在一次访问结束时即告过期，对于此促销，将仅对该访问期间（在此期间有效）发生的购买或注册计数。

使 eVar 过期的方法有两种：

* 您可以将 eVar 设置为在指定的时间段或事件后过期。
* 您可以强制使 eVar 过期，在重新利用变量时这非常有用。

如果eVar在5月用于反映内部促销并在21天后过期，而在6月用于捕获内部搜索关键字，那么在6月1日，您应强制该变量过期或重置。 这样做有助于从 6 月的报表中排除内部促销值。

**区分大小写** {#section_6E9145B7FCC2438E95BB35AAE3857412}

eVar 不区分大小写，但其第一个实例的首字母以大写显示。例如，如果 eVar1 的第一个实例被设置为“Logged In”，但随后的所有实例都作为“logged in”传递，报表始终显示“Logged In”作为 eVar 的值。

**Counters** {#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

eVar 最常用于保存字符串值，但也可以配置为用作计数器。在您尝试计入用户在某个事件前所执行的操作数时，使用 eVar 与计数器一样有用。例如，可以使用 eVar 捕获购买前的内部搜索数。访客每搜索一次时，eVar 包含值“+1”。如果访客在购买前搜索了四次，则将看到每个总计数的实例：1.00、2.00、3.00 和 4.00。但只有 4.00 针对购买事件（订购和收入量度）计数。只允许正数作为 eVar 计数器的值。

**子关系** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

[!UICONTROL 自定义 eVar] 报表的常见要求是能够按其他报表划分[!UICONTROL 自定义 eVar] 报表。例如，如果一个 eVar 包含性别，另一个包含薪水，您可能会问下面的问题：网站的女性访客中，年薪在 50,000 美元以上的女性访客可以产生多少收入。具有完全子关系的任何 eVar 都允许在报表中使用此类型的划分。例如，如果性别 eVar 启用了完全子关系，则可以按性别划分所有其他自定义 eVar 报表，并且可以按所有其他自定义 eVar 划分性别报表。要了解两个报表之间的关系，只需其中一个报表启用完全子关系。默认情况下，[!UICONTROL 促销活动]、[!UICONTROL 产品]和[!UICONTROL 类别]报表具有完全子关系（可以按促销活动或产品划分任何 eVar）。

**语法和可能值** {#section_BD46438B14F3488FB9AC42994C317B06}

While eVars may be renamed, they should always be referred to in the JavaScript file by eVarX, where X is a number between 1 and 75 ( [or 100, or 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

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

可以在“分析”&gt;“管 [!UICONTROL 理员”&gt;“报表包”&gt;“编辑设置”&gt;“转换”&gt;“转换变量”中配置eVar]。 所有 eVar 都可以包含以下几个配置选项：[!UICONTROL 名称]、[!UICONTROL 类型]、[!UICONTROL 分配]、[!UICONTROL 过期时间设置]，或[!UICONTROL 重置]。下面分别介绍了每项配置设置。

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

## 事件 {#concept_FFD115543D54401B98FE683BD7D5B3FE}

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

最终事件类型&#x200B;*货币*&#x200B;允许您定义要添加的数量（类似于数值事件），但在报表中显示为货币，并需符合基于 s.*`currencyCode`*&#x200B;值的货币兑换和报表包的默认货币设置。For additional information on using numeric and currency events, see [Products](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**配置变量** {#section_9195286C34C54B02B2598E2B856492C3}

[!UICONTROL s.events] 变量默认为在所有实施中启用。七个预配置转化事件在所有新报表包中自动启用。New custom events (event1- [event100 or event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) can be enabled by any admin-level user using the Admin Console.

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

请参阅[事件序列化](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705)，以了解更多信息。

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

## hierN {#concept_C4475D1584D544ACB4C0A573EB60FA08}

[!UICONTROL 层级]变量确定页面在网站层级中的位置。

<!-- 

hierN.xml

 -->

该变量最适用于网站结构超过三层的网站。例如，某媒体网站的“体育”区域可能有 4 个级别：体育、地方体育、棒球、红袜队 (Red Sox)。如果有人访问“棒球”页面，则“体育”、“地方体育”和“棒球”这几个级别都会反映此访问。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 255 字节 | H1-H5 | 层级 | "" |

有五个可用的[!UICONTROL 层级]变量，它们都必须由 Adobe 客户关怀部门启用。启用层级后，您需要决定变量的分隔符以及层级的最大级别数目。例如，如果使用逗号作为分隔符，则体育层级可能显示如下。

```js
s.hier1="Sports,Local Sports,Baseball"
```

请确保您的所有区域名称中没有分隔符。例如，如果您有一个名为“Coach Griffin, Jim”的区域，则您需要选择逗号以外的其他分隔符。每个层级区域限制在 255 字节以内，且全部变量限制也是 255 字节。分隔符一旦选定（即在层级创建时），便不易更改。

若要更改现有层级的分隔符，请联系 Adobe 客户关怀部门。分隔符也可由多个字符组成，如 || 或 /|\，这些字符组合在层级区域中出现的概率较低。

**语法和可能值** {#section_0739948A68A2420DAB1CBEA3115A5A66}

请不要在分隔符间插入空格。在以下示例语法中，N 是一个介于 1 至 5 之间的数值。

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

除了用于分隔层级的级别外，请不要在其他时候使用分隔符。分隔符可以是您选择的任何字符或字符集。

**示例** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**配置设置** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

无

**缺陷、问题和提示** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* 一旦设置了层级，便不可更改分隔符。若必须更改层级的分隔符，请联系 Adobe 客户关怀部门。
* 层级一旦设置好后，便不可更改级别数。

>[!NOTE]
>
>Changes to hierarchies can result in a service charge.

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

Internet Explorer 中的 变量表示当前的页面是否设置为用户的主页。

<!-- 

homepage.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此变量应仅读取且不应设置。

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| hp | Y 或 N | Y | “流量”&gt;“技术”&gt;“主页” |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

 变量指示 Java 是否已在浏览器中启用。

<!-- 

javaEnabled.xml

 -->

此变量填充在页面代码之后，运行 doPlugins 之前。

>[!NOTE]
>
>此变量应仅读取且不应设置。

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| v | Y 或 N | Y | “流量”&gt;“技术”&gt;“Java” |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

 变量表示受浏览器支持的 JavaScript 的版本。

<!-- 

javascriptVersion.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>此变量应仅读取且不应设置。

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | “流量”&gt;“技术”&gt;“JavaScript 版本” |

H.10 和更高版本的 JavaScript 文件可以准确检测到最高 1.7 版本（这是 H.10 发布时的最高版本）。以前版本的 JavaScript 文件最高只能检测到 1.3 版本

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

The  variable is an optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link.

<!-- 

linkName.xml

 -->

The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> 100 字节 </td> 
   <td> pev2 </td> 
   <td> <p>文件下载 </p> <p>自定义链接 </p> <p>退出链接  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL 自定义链接]是指发送跟踪数据的链接。此 *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. If *`linkName`* is not populated, the URL of the link appears in the report.

**语法和可能值** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

There are no limitations on *`linkName`* outside of the standard variable limitations.

**示例** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**配置设置** {#section_F15FF429FC274F708D50DF79D4668EA3}

无

**缺陷、问题和提示** {#section_170A78452A7340B5B229713AC1FB71FA}

* The *`linkName`* variable is replaced by the third parameter in the *`tl()`* function.

* If the *`linkName`* variable and the third parameter in the *`tl()`* function are blank, the full URL of the link (with the exception of the query string) appears in the report (even if the link is relative).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

 变量是链接跟踪中使用的可选变量，可以确定要显示链接名称或 URL 的报表（自定义、下载或退出链接）。

<!-- 

linkType.xml

 -->

The *`linkType`* variable is not normally needed because the second parameter in the *`tl()`* function replaces it.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
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
   <td> 一个字符 </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>文件下载 </p> <p>自定义链接 </p> <p>退出链接  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

自定义链接将数据发送给 Analytics。The *`linkType`* variable (or the second parameter in the *`tl()`* function) is used to identify the report in which the link name or URL appears ( [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report).

对于退出和下载链接，根 *`linkType`* 据单击的链接是退出链接还是下载链接，会自动填充该变量。 A custom link may be configured to send data to any of the three reports with this variable or with the second parameter in the *`tl()`* function. 通过将 *`linkType`* URL设置为“o”、“e”或“d”, *`linkName`* 或链接URL将分别发送到“自定义链接 [!UICONTROL ”、“]退出链接 [!UICONTROL ”或“文件] 下载”报告。

**语法和可能值** {#section_18DB3A8083FB4F75B970055ED336DA4E}

The *`linkType`* variable syntax depends on whether you use XML or a query string.

如果您使用的是 XML，则此变量只能包含单个字符，即“o”、“e”或“d”。

```js
s.tl(this,’o’,’Link Name’);
```

If you are using the query-string `pe`, you need to use `lnk_d`, `lnk_e`, or `lnk_o`.

**示例** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**配置设置** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

无

**缺陷、问题和提示** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* 如 *`linkType`* 果未指定，则假定自定义链接('o')。

## 列表属性 {#concept_83ED74232225431F83A796E22FFC75B4}

列表属性是一种分隔的值列表，这些值被传入到一个变量，然后作为单独的行项目进行报告。列表属性通常在包含用户可选值的页面上实施，例如，具有复选框或单选按钮的列表项目。当您希望在不发送多个图像请求的情况下，在一个变量中定义多个值时，这些列表属性非常有用。

<!-- 

list_props.xml

 -->

**注意事项**

* 列表属性只在流量变量启用 ([props](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254))。
* 无法为列表属性启用路径分析和关联。
* Analytics 几乎为每个报表（包括所有列表属性报表）都提供了访问和独特访客。
* 列表属性支持分类。
* 任何自定义流量变量都可成为一个列表属性。（ pageName [](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328)[、](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D)channel [和](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2)server。)

* 在同一个图像请求中定义重复值时，不会删除重复实例。

可以通过启用“列表支持”并选择分隔符，在“管理工具”&gt;“报表包”&gt;“流量变量”页面将属性更改为列表属性。常用的分隔符包括冒号、分号、逗号或竖线。从技术上讲，分隔符可以是头 127 个 ASCII 字符中的任意一个。

**实施示例** {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

在请求启用列表属性时，请指明您要使用的分隔符。在启用了您选择的&#x200B;*`s.prop`*&#x200B;之后，可在变量中设置多个值，如以下示例中所示：

由竖线分隔的列表属性，传入两个值：

```js
s.prop1="Banner ad impression|Sidebar impression"
```

由逗号分隔的列表属性，传入多个值：

```js
s.prop2="cerulean,vermilion,saffron"
```

列表属性还可随单个值一起发送：

```js
s.prop3="Single value"
```

分隔符可随时更改。但是，实施必须匹配新的分隔符。如果未使用正确的分隔符，则会导致列表属性值在报表中被视为一个包含若干字符串的行项目。

由于列表属性仍是一个流量变量，因此它必须遵守流量变量的限制。列表属性的数据被限定为 100 字节，并且受区分大小写设置影响。

## 列表变量 {#concept_AC42F2D69B674C02A484137CE5B4E687}

也称为 List Var（列表变量）。与“列表属性”的功能类似，“列表变量”允许在同一图像请求中包含多个值。它们的作用也与 eVar 类似，可独立于定义它们的图像请求之外存在。您可以使用这些变量来查看单一页面上多个元素（例如，产品列表、请求列表、搜索调整列表或展示广告列表）之间的因果关系。

<!-- 

listN.xml

 -->

**注意事项**

* 列表变量可通过引用访客浏览器中的 VisitorID Cookie，记住其特定值。
* 每个访客每次最多可存储 250 个值。如果超出了每个访客 250 个值的限制，则使用最后的 250 个值。这些值的过期设置取决于为变量配置的过期设置。
* 每一个分隔值可包含最多 255 个字符（如果使用多字节字符，则更少）。这是每个元素的最大长度。
* 此变量内的字符数量没有限制。此限制的唯一例外是在旧版 Internet Explorer 浏览器中，所有 URL 请求均有 2083 字符限制。
* 每个报表包均可使用总共三个列表变量。
* 使用列表变量需要 H23 或更高版本的代码。
* 列表 Var 可进行分类。
* 如果在同一个图像请求中定义了重复值，列表变量会删除这些重复值的所有实例。
* 可划分区段的最详细列表变量是在点击（或页面查看）级别。如果列表变量在同一图像请求中有三个值，则匹配一个值的任何区段规则都会将三个值全部提取到报表中。相反，如果定义的排除规则与单个值匹配，则会全部排除这三个值。

**配置** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

无需 Adobe 客户关怀部门的介入，您就可以在管理控制台中访问并更新配置：

1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**
1. 选择报表包。
1. Click  **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

* **名称**：每一个分隔值最多可包含 255 个字符（如果使用多字节字符，则会更少）。这是每个元素的最大长度。
* **值分隔符**：用于在列表变量中分隔值的字符。通常有逗号、冒号、竖线或类似的字符。

   >[!NOTE]
   >
   >Multi-byte characters are not supported as delimiters in List Vars. 分隔符必须为单字节。

* **过期日期**：类似于 eVar 过期日期，此设置决定列表变量和转化事件之间可产生关联的时间量。

   * **在页面查看或访问级别**：超出页面查看或访问以外的成功事件不会链接回列表变量内的任何值。
   * **基于时段，如日、周、月等**：超出指定时段以外的成功事件将不会链接回列表变量内的任何值。还可以定义自定义天数。
   * **特定转化事件**：在指定的特定事件后触发的任何其他成功事件将不会链接回列表变量内的任何值。
   * **从不**：列表变量和成功事件之间可以传递的时间量不限。

* **分配**：此设置确定成功事件如何进行计数：

   * **完整**：变量过期前定义的所有变量值获得成功事件的全部计数。
   * **线性**：变量过期前定义的所有变量值获得转化事件的平均计数。
   * 变量值永远不会被覆盖，但会被添加到获得成功事件计数的值。

* **最大值**：指定此列表变量允许的活动值的数量。例如，如果设置为 3，则只保存最后捕获的 3 个值，而之前捕获的任何值都将被丢弃。请注意，如果一次点击时发送同一列表 var 的多个值，同时您又对使用最大值进行了限制，那么每个值的时间戳将相同，且不确定将保存哪个值。

   每个访客每次最多可存储 250 个值。如果超出了每个访客 250 个值的限制，则使用最后的 250 个值。这些值的过期设置取决于为变量配置的过期设置。

   “最大值”设置可用于将属性限制为特定数量的值。例如，如果某个列表 var 在访问的首个页面上设置为“A,B,C”，然后在下一页上设置为“X,Y,Z”，那么属性将根据分配情况分发到这六个值。如果您希望将属性限制为仅“X,Y,Z”，那么可以将最大值设为 3。

To set up or edit List Vars, go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

**实施示例** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

以下每一个示例都使用逗号作为值分隔符。

**在列表变量内定义单个值：**

```js
s.list1="Cat";
```

**传入多个值：**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**将收入分配给列表变量：**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

此结果会显示三个行项目，并且每个项目的收入为 50 美元。（顶部横幅广告、侧栏广告和内部促销活动 1。）请注意此报表的总量会删除重复的收入，因此总量也将反映为 50 美元。

**将收入分配给访问期间设置了多次的列表变量：**

**分配**：完整

**过期**：访问

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 页面 </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 页面 1 </td> 
   <td colname="col2"> <code> s.list1=”value1,value2,value3”; </code> </td> 
   <td colname="col3"> （未设置） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面 2 </td> 
   <td colname="col2"> <code> s.list1=”value4,value5,value6”; </code> </td> 
   <td colname="col3"> <p> <code> s.events=”purchase”; </code> </p> <p> <code> s.products=”;product;1;200” </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**结果**：访问期间 list var1 中设置的所有值（value1、value2、value3、value4、value5、value6）获得购买的全部计数。

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

s.maxDelay 变量主要用在 Genesis DFA 集成中，用来确定联系 DFA 主机时的超时时间段。如果 Adobe 在 变量中设置的指定时间段内没有收到来自 DFA 服务器的响应，则断开连接，并正常处理数据。如果您关注的是每个页面上的 DFA 响应时间，则实施此变量。建议使用此值进行试验，以确定最佳的超时时间段。

<!-- 

maxDelay.xml

 -->

**实施示例**

```
s.maxDelay="750";
```

**属性**

* 此变量是一个可选事件量度，通过网站上实施的 JavaScript 填充。
* 如果 DFA 主机未在给定的时间内响应，将运行被指定给超时的事件（通过 Genesis 集成向导指定）。
* 此变量可只包含一个数字值。
* 指定的时间以毫秒为单位计算。
* 增加等待时间会收集到更多的 DFA 数据，但这也会增加 Analytics 点击数据丢失的风险。

   Losing Analytics hit data would occur when the user navigates away from the page during the *`s.maxDelay`* period.

* 减少等待时间会降低 Analytics 点击数据丢失的风险，但这也会减少随点击数据发送的 DFA 数据量。

   当该时间段不能容纳DFA主 *`s.maxDelay`* 机进行响应的足够时间时，将会丢失DFA集成数据。

>[!NOTE]
>
>Adobe does not have control over DFA's response time. 如果将最大延迟时段增加到一个合理的时间范围后发现问题依然存在，请咨询贵组织的 DFA 帐户管理员。

## mediaLength {#concept_F52B1670122C4461824223E525307060}

 变量可指定正在播放的媒体的总长度。

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
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
   <td> 整个 pev3 请求无最大大小 - 大小受浏览器的 URL 长度限制。 </td> 
   <td> pev3 </td> 
   <td> 视频查看时间； <p>查看的视频区段 </p> </td> 
   <td> 无 </td> 
  </tr> 
 </tbody> 
</table>

**语法和可能值** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

** autoTrack Method: **

如果使用 [!UICONTROL s.Media.autoTrack]，则不需要明确实施 [!UICONTROL mediaLength] 变量。它由 JavaScript AppMeasurement 代码自动确定。

**手动跟踪方法：**

语法：

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能值：

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**示例** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**缺陷、问题和提示** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* 只有在使用 [!UICONTROL s.Media.autoTrack] = true 无法跟踪播放器时，才需要调用媒体跟踪方法。
* 如果不是使用 [!UICONTROL autoTrack] 进行跟踪，请务必以秒为单位设置其长度。

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

此变量指定视频或媒体项目的名称。

<!-- 

mediaName.xml

 -->

此变量只能通过[!UICONTROL 数据插入 API] 和[!UICONTROL 完全处理数据源]来使用。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 64KB | pev3 | 视频、下一视频流量、上一视频流量、查看的视频区段、视频查看时间 | 无 |

**语法和可能值** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**autoTrack 方法：**

如果使用 [!UICONTROL s.Media.autoTrack]，则不需要明确实施&#x200B;*`mediaName`*&#x200B;变量。它由 JavaScript AppMeasurement 代码自动确定。

**手动跟踪方法：**

语法：

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

可能值：

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**示例** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**缺陷、问题和提示** {#section_941A445BB52E4063B0F6920E61BB90DE}

* 仅当使用 [!UICONTROL s.Media.autoTrack] = true 无法跟踪播放器时，才调用媒体跟踪方法。
* 与 VARCHAR(100) 相反，这个变量存储为 mySQL TEXT 变量。

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

此变量指定用于播放视频或媒体项目的播放器。

<!-- 

mediaPlayer.xml

 -->

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | pev3 | 视频播放器 | 无 |

**语法和可能值** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**autoTrack 方法：**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**手动跟踪方法：**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

可能值：

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**示例** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**缺陷、问题和提示** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

仅当使用 s.Media.autoTrack = true 无法跟踪播放器时，才调用媒体跟踪方法。

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

此变量指定所播放视频或媒体资产的区段。

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
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
   <td> 255 字节 </td> 
   <td> pev3 </td> 
   <td> 视频查看时间 <p>查看的视频区段 </p> </td> 
   <td> 无 </td> 
  </tr> 
 </tbody> 
</table>

**语法和可能值** {#section_9A63266633C4427CB4A6549E4D887B85}

**autoTrack 方法：**

如果使用 [!UICONTROL s.Media.autoTrack]，则不需要明确实施&#x200B;*`mediaName`*。它将由 AppMeasurement for JavaScript 代码来自动确定。

**手动跟踪方法：**

语法：

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

可能值：

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**示例** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**缺陷、问题和提示** {#section_1BCEB037AB724B6EBE87420BD3604B88}

仅当使用 [!UICONTROL s.Media.autoTrack] = true 无法跟踪播放器时，才调用媒体跟踪方法。

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

 变量会确定点击媒体时应发送哪些事件。

<!-- 

media_trackEvents.xml

 -->

此变量仅适用于 JavaScript 和 [!UICONTROL ActionSource]。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | s.Media.trackEvents="None" |

**语法和可能值** {#section_66A978EF56914BEAAE73359A268A1B4A}

事件名称，如 event1 或 purchase。

**示例** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents=”event1,purchase”
```

**缺陷、问题和提示** {#section_030B11C64EE84D46A85CA550DB732D28}

请确保只要填充了此变量就使用“events”填充 [!UICONTROL trackVars]。

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

 变量用来确认点击媒体时应发送哪些变量。

<!-- 

media_trackVars.xml

 -->

此变量仅适用于 JavaScript 和 [!UICONTROL ActionSource]。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | s.Media.trackVars="None" |

**语法和可能值** {#section_7374684A7EB34AE685E8C40A66CFD289}

变量名 [!UICONTROL 称]，如 *`eVarN`* propN、 *`events`*、 *`channel`*、等等。

**示例** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars=”prop2,events,eVar3”
```

**缺陷、问题和提示** {#section_615AE1B696124B00B78F651B03813EAB}

* 即使在 [!UICONTROL trackVars] 中指定了 eVar3，点击媒体时也会发送此变量。

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

 变量可控制使用 Cookie 和订阅者 ID 识别访客的顺序。

<!-- 

mobile.xml

 -->

See [Mobile network protocols](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 图像 URL 路径中的 /5/ 或 /1/ | 不适用 | 无 |

**语法和可能值** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**缺陷、问题和提示** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

在JavaScript cookie实施中使用变量时，使用跨访客识别来减轻访 *`s.mobile`* 客流量的可能高峰。

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

 变量包含网站中每个页面的名称。

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
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
   <td> 100 字节 </td> 
   <td> pageName </td> 
   <td> <p>页面 </p> <p>路径 </p> </td> 
   <td> 页面 URL </td> 
  </tr> 
 </tbody> 
</table>

The *`pageName`*&#x200B;变量应使用企业用户可识别的值填充。在大多数情况下， *`pageName`* 该值不是URL或文件的路径。 Common *`pageName`* values include names such as "Home Page," "Checkout," "Purchase Thank you," or "Registration."

请注意，页面名称和其他变量中不允许出现换行符、长划线或短划线，或任何 HTML 字符。有些浏览器可以传送换行符，而有些则不能，这会导致 Analytics 中的数据被分割到两个看起来相同的页面名称。在键入连字符时，许多文字处理器和电子邮件客户端会自动将其转换为长划线或短划线。由于长划线和短划线在 Analytics 变量中被视为非法字符（编码值高于 127 的 ASCII 字符），因此 Analytics 不会记录包含非法字符的页面名称，而改为显示 URL。

If *`pageName`* is left blank, the URL is used to represent the page name. Leaving *`pageName`* blank is often problematic because the URL may not always be the same for a page `www.mysite.com` and `mysite.com` are the same page with different URLs).

**语法和可能值** {#section_7A61EE70F1A84D26B414404998C84BA8}

The *`pageName`* variable should contain a useful identifier for business users of Analytics.

```js
s.pageName="page_name"
```

There are no limitations on *`pageName`* outside of the standard variable limitations.

**示例** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**配置设置** {#section_58CBC68C805344A999EB47455FEBA8D5}

管理员可以使用[!UICONTROL 命名页面]工具在 Analytics 中更改显示的页面名称，这存在潜在的危险，可能会对报表造成负面影响。在使用命名页面工具之前，请联系 Adobe [!UICONTROL 客户关怀]部门。

**缺陷、问题和提示** {#section_BB41DC9682C34385B9CAA80D5257C113}

确保不 *`pageName`* 包含非法字符。

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

 变量仅用于指定“页面未找到”404 错误页面。

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
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
   <td> 20 字节 </td> 
   <td> pageType </td> 
   <td> “路径”&gt;“页面”&gt;“页面 <p>未找到” </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`*&#x200B;变量会在显示 404 错误页面时捕获错误的 URL，这样您可以迅速找到自定义网站上已无效且损坏的链接和路径。在错误页 *`pageType`* 面上设置变量，如下所示。

不要在 404 错误页面上使用页面名称变量。此&#x200B;*`pageType`*&#x200B;变量仅用于 404 错误页面。

大多数情况下，404 错误页面是一个硬编码的静态页面。在这种情况下，将 .JS 文件的引用设置为合适的全局或相对路径/目录非常重要。

**语法和可能值** {#section_C1C59968226446559B05F6EE7374D525}

唯一允许的值 *`pageType`* 是“errorPage”，如下所示。

```js
s.pageType="errorPage"
```

**示例** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**配置设置** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

无

**缺陷、问题和提示** {#section_943681AB01FE47BEAC72E93CB60C53C8}

To capture other server-side errors (such as 500 errors), use a prop to capture the error message and put "`500 Error: <URL>`" where `<URL>` is the URL requested, in the *`pageName`* variable. 按照这一操作过程，您可以使用[!UICONTROL 路径分析]报表查看是哪些路径导致用户产生 500 错误。prop 可解释哪个错误消息是由服务器发出的。

## pageUrl {#concept_A15F710CD0174297A2286BF3E7452113}

 变量覆盖实际的页面 URL。

<!-- 

pageURL.xml

 -->

在少数情况下，页面的 URL 不是您想在 Analytics 中报告的 URL。

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
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
   <td> 无限制* </td> 
   <td> <p>G </p> </td> 
   <td> “流量”&gt;“分段”&gt;“最受欢迎页面路径” </td> 
   <td> 页面 URL </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Although Adobe allows *`pageURL`* values up to 64k, some browsers impose a size limit on the URL of image requests. To prevent truncation of other data, page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter.

**语法和可能值** {#section_22AF3BF7C2F743549967B0C760A095C0}

The *`pageURL`* variable must be a valid URL, with a valid protocol. 域被填充到报表之前，将强制以小写字母形式显示域名，并有可能根据 Analytics 设置清空查询字符串。

```js
s.pageURL="proto://domain/path?query_string"
```

页面 URL 只能采用 URL 兼容的字符。

>[!NOTE]
>
>强烈建议您在将变量用于自定义目的之前先与Adobe顾问或客 *`pageURL`* 户关怀联系。

**示例** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**配置设置** {#section_A8F77DAD88164528ACC5C16C066B47DF}

无

## plugins {#concept_B570F04FEDA34EB7A9826687FE633953}

在 Netscape 和基于 Mozilla 的浏览器中， 变量会列出浏览器中安装的插件。

<!-- 

plugins.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| p | 认可的插件 | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Windows Media Player Plug-in Dynamic Link Library;Microsoft® DRM; | “流量”&gt;“技术”&gt;“插件” |

## 产品 {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

 变量用于跟踪产品和产品类别，以及购买数量和购买价格。products 通常与购物车事件或 事件一起设置。

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. 此更新可能会导致 *`prodView`事件增加。**`prodViews`*&#x200B;仅在以下情况下增加：
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
   >
   >
1. The *`products`* variable is not empty.
>
>
A possible side effect is that merchandising eVars triggered by *`prodView`* events could be associated with an empty *`product`*, but only if the *`product list`* contains only an invalid product (such as a semicolon with no product listed).

The *`products`* variable tracks how users interact with products on your site. 例如，products 变量可跟踪产品被查看、添加到购物车、结帐以及购买的次数。它也可跟踪网站上促销类别的相对效果。以下方案是 products 变量的常见使用方式。

The *`products`*&#x200B;变量应始终结合成功事件进行设置。

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
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
   <td> <p>“ <span class="wintitle"> products </span>”字符串的最大大小为64k。 </p> </td> 
   <td> products </td> 
   <td> 产品 <p>类别（可选） </p> <p>收入（可选） </p> <p>件数（可选） </p> <p>自定义事件（可选） </p> <p>eVar（可选） </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**语法** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| 字段 | 定义 |
|---|---|
| 类别 | 包含关联的产品类别。在版本 15 中，products 可以与多个类别相关联，从而修复了版本 14 中存在的限制。如果之前未记录产品类别，则建议开始为版本 15 上的报表包填充此字段。 |
| 产品 | （必需）用于跟踪产品的标识符。此标识符用于填充[!UICONTROL 产品]报表。请务必在整个结帐过程中使用同一标识符。 |
| 数量 | 所购买的件数。此字段必须在[!UICONTROL 购买]事件中设置才能记录。 |
| 价格 | 指总购买量的联合成本（件数 x 单价），而不是单价。此字段必须在[!UICONTROL 购买]事件中设置才能记录。 |
| 事件 | 与指定产品关联的货币事件。请参阅[产品特定的货币事件](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C)和[订单范围的货币事件](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0)。 |
| eVar | 与特定产品关联的促销 eVar 值。请参阅[促销变量](/help/components/c-variables/c-merch-variables/var-merchandising.md)。 |

包含在&#x200B;*`products`*&#x200B;变量中包含的值基于您所记录的事件类型。省略类别时，需要使用类别/产品分隔符 (;) 作为占位符。仅当需要区分所包含的参数时，才要求使用其他分隔符，如本页上的示例所示。

**设置非购买事件的 products** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

The *`products`* variable must be set in conjunction with a success event.

**设置购买事件的 products** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

The *`purchase`* event should be set on the final confirmation ("Thank You!") 页面上设置。产品名称、类别、数量和价格都将使用 *`products`* variable. Although the *`purchaseID`* variable is not required, it is strongly recommended in order to prevent duplicate orders.

**产品特定的货币事件** {#section_F814DF053C0D463A97DA039E6323720C}

如果货币事件接收到变量中的值而 *`products`* 不是events变量，则它仅应用于该值。 这对于跟踪产品特定的折扣、产品运输及类似值非常有用。例如，如果将事件 1 配置为跟踪产品运输，则运输费用为“4.50”的产品可能会类似于以下内容：

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

在此示例中，值 4.50 直接与“Running Shoes”产品相关联。如果将 event1 添加到 products 报表中，您会发现“Running Shoes”行项目将列出“4.50”。与“价格”类似，该值应反映所列数量的总值。如果有 2 个运输费用均为“4.50”的项目，则 event1 应为“9.00”。

**订单范围的货币事件** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

如果货币事件在事件列表中而非变量中收到一个值，则该值将应 *`products`* 用于变量中的所有产 *`products`* 品。 这对于在不修改产品价格，或单独跟踪产品列表中值的情况下，跟踪订单范围折扣、运输费以及类似值非常有用。

例如，如果将 event10 配置为包含订单范围的折扣，则折扣为 10% 的购买可能会类似于以下内容：

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

在货币事件报表中，报表合计表示去除重复后的事件总数（在本示例中为报表期间的总折扣数），而不是每个产品的事件值总数。例如，您会发现“Running Shoes”和“Running Socks”都列为“9.95”，而总值也为“9.95”。

>[!NOTE]
>
>如果在变量和变量中指定了同一数字／货币事 *`products`* 件的值，则 *`events`* 将使用来自 *`events`* 的值。

**缺陷、问题和提示** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* The *`products`* variable should always be set in conjunction with a [!UICONTROL success] event (events). 如果未指定任何[!UICONTROL 成功]事件，则默认事件为 [!UICONTROL prodView]。

* 在填充 products 变量之前，请先清除产品和类别名称中的所有逗号和分号。
* 清除所有 HTML 字符（注册符号、商标等）。
* 清除价格中的货币符号 ($)。

**示例** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code>s.products="Category;ABC123"</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.products="Category2;ABC123,;ABC456"</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.products="Category3;ABC123;1;10"</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.products="Category;ABC123;1;10,;ABC456;2;19.98"</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.events="event1,event2"</code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.events="event1,event2"</code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.events="event1,event2"</code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.events="event1,event2"</code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.events="event1,event2,event3"</code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code>s.events="event1,event2,event3=9.95"</code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

属性 ([!UICONTROL prop]) 变量用于在[!UICONTROL 流量模块]建立自定义报表。

<!-- 

propN.xml

 -->

props 变量可用作路径报表或关联报表的计数器（计算一个页面查看的发送次数）。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | c1 - c75 | 自定义流量 | "" |

**语法和可能值** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

除标准变量限制以外，[!UICONTROL 属性]变量无其他限制。

**示例** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**配置设置** {#section_25FDEB6ECA8242A2A44EE540C083078A}

要了解有关显示 prop 变量的[!UICONTROL 访问]、[!UICONTROL 访客]和[!UICONTROL 路径]量度的信息，请联系 Adobe [!UICONTROL 客户关怀]部门。

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

 用于防止在报表中对一次订购多次计数。

<!-- 

purchaseID.xml

 -->

Whenever the [!UICONTROL purchase] event is used on your site, you should use the *`purchaseID`* variable.

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 20 字节 | purchaseID | “转化”&gt;“购买”&gt;“收入转化” | "" |

当访客从您的网站上购买项目时，*`purchaseID`*&#x200B;将在“谢谢”页面中被填充（该页面与触发[!UICONTROL 购买]事件的位置相同）。If the *`purchaseID`* is populated, the products on the "Thank You" page are counted only once per *`purchaseID`*. 这一点至关重要，因为许多访问您网站的访客都会出于各自的目的保存“谢谢”或“确认页面”。The *`purchaseID`*&#x200B;可防止每次查看页面时都对购买计数。

除了避免将购买数据计数两次外，使用时还 *`purchaseID`*&#x200B;会防止所有转化数据在报告中重复计数。

**语法和可能值** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

The *`purchaseID`* must be 20 characters or fewer, and be standard ASCII.

**示例** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**配置设置** {#section_1808631C96674380BF9C4A6D9A2C568E}

无

**缺陷、问题和提示** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

The *`purchaseID`* variable allows all conversion variables on the page to be counted only once in reports.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

 变量可用于还原丢失的反向链接信息。

<!-- 

referrer.xml

 -->

通常情况下，我们通过服务器端和 JavaScript 重定向将访客转至适当的位置。但是，重定向浏览器时，原始反向链接 URL 将丢失。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 255 字节 | R | “流量”&gt;“查找方法转化”&gt;“查找方法” | document.referrer |

许多公司在其整个网站中的许多地方使用重定向。例如，可以从某个搜索引擎付费搜索结果将访客重定向。重定向浏览器时，反向链接通常会丢失。The 变 *`referrer`* 量可用于在重定向后 *`referrer`* 恢复第一页上的原始值。 The *`referrer`* may be populated server-side, or via JavaScript from the query string.

若要 Analytics 记录反向链接，其格式必须正确，即必须遵循标准 URL 格式，并且包含协议和相应的位置。

**语法和可能值** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

只能在 *`referrer`*. 请确保字符串为 URL 编码（无空格）。

**示例** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**配置设置** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

无

**缺陷、问题和提示** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

The *`referrer`* must look like a standard URL and include a protocol.

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

 变量表示访客查看网页时的显示器分辨率。

<!-- 

resolution.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>This variable should only be read and never set.

您可以读取这些值，并将它们复制到 prop/eVar，但不得更改它们。此变量在 JavaScript 文件 H.11 版本中另有介绍。

| 查询参数 | 值 | 示例 | 受影响的报表 |
|---|---|---|---|
| s | WxH | 1680 x 1050 | “流量”&gt;“技术”&gt;“显示器分辨率” |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

The  variable is a global variable that should be set in the [!UICONTROL onClick] event of a link.

<!-- 

s_objectID.xml

 -->

By creating a unique object ID for a link or link location on a page, you can either improve visitor activity tracking or use [!UICONTROL Activity Map] to report on a link type or location, rather than the link URL.

>[!NOTE]
>
>A trailing semicolon (;) is required when using s_objectID with [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | 点击链接的绝对 URL |

使用 *`s_objectID`*:

* 为了整合一天内经常发生变化的访客活动。
* To separate link activity that [!UICONTROL Activity Map] combines.
* To improve the accuracy of [!UICONTROL Activity Map] data reporting.

**汇总高度动态链接的点击** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

如果您的站点具有高度动态性，并且某些页面上的链接在一天中都会发生更改，则 *`s_objectID`* 可能会用于标识页面上链接的位置。 如果 *`s_objectID`**`s_objectID`* 设置为“左上角1”或“左上角2”（例如，它表示页面左上角的第一个链接），则显示在该位置（或设置为相同值的链接）的所有链接都会与访客点击图一起报告。 If you don't use *`s_objectID`*, you see the number of times that a specific link was clicked, but you lose insight into how all the other links in that location were used by visitors to your site.

**区分整合的点击** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

If the  variable on your site is used to show the section or template a visitor is viewing, rather than the specific page the visitor is viewing, you may want to use  to separate links that appear on multiple versions of that page template. *`pageName`**`s_objectID`*&#x200B;例如，如果您有一个适用于网站中所有产品的模板页面，可能在所有页面上都会有一个指向主页和指向模板中搜索框的链接。若要按单个产品（而非模板）了解这些链接的使用情况，您可以使用产品特定的值填充&#x200B;*`s_objectID`*，例如“prod 123789 home page”或“prod 123789 search”。Once completed, [!UICONTROL Activity Map] reports on those links at an individual product basis.

**提高[!UICONTROL 活动图](Activity Map)准确性**{#section_08B3406821294DCCABEEB99C90CF5C52}

在某些情况下，访客点击图不会报告除 Internet Explorer、Firefox、Netscape、Opera 和 Safari 以外的浏览器。尽管其他浏览器所占的比例很小，但确实存在一部分点击量和其他量度。Use *`s_objectID`* within links to uniquely identify the addresses the browser reporting issue. 以下示例介绍了如何使用 *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**语法和可能值** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID 可以包含任何文本标识符。

```js
s_objectID="unique_id" 
```

除标准变量限制以外，*`s_objectID`*&#x200B;无其他限制。

**示例** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**配置设置** {#section_95396657D55B41ECB66B83D0534EA827}

无

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

 变量用于显示网页的域（显示访客访问的域）或提供页面的服务器（用于负载平衡快速引用）。

<!-- 

server.xml

 -->

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | server | 服务器 | "" |

如果您的网站有多个域提供相同的内容服务，则&#x200B;*`server`*&#x200B;变量可用于跟踪访客使用了这其中哪些域。以下 JavaScript 将页面的域填入服务器变量。

```js
s.server=window.location.hostname
```

如果您使用服务器变量为负载平衡提供快速指导，则可以将服务器名称或数量填入服务器变量。请参阅以下示例：

```js
s.server="server 14"
```

虽然[!UICONTROL 最受欢迎服务器]报表可用作负载平衡快速引用，但它并不能精确地测量服务器负载。例如，后退按钮流量并不会增加服务器负载，但会在报表中显示。该报表不会显示哪些服务器提供图像或大容量下载服务。

**语法和可能值** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

There are no limitations on the *`server`* variable outside of the standard variable limitations.

**示例** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**配置设置** {#section_969DB379D5BD469FBEE8D505D3000E49}

无

**缺陷、问题和提示** {#section_42A28F9B01574F38891D9D54B411D8FE}

The *`server`* variable can be used to show which domains are most popular or which servers are serving the most pages.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

和变量是转换变量。

<!-- 

state.xml

 -->

这些变量与 eVar 一样均可捕获事件，但不同之处在于，这些变量不是永久性变量。The *`zip`* and *`state`* variables are like eVars that expire immediately.

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 50 字节 | state | 转化 &gt; 访客资料 &gt; 访客所在州 | "" |

Because the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events that are fired on the same page on which they are populated. For example, if you are using *`state`* to compare conversion rates by state, you should populate the *`state`* variable on every page of the checkout process. 对于转化网站，Adobe 建议使用帐单地址作为邮政编码的来源，但您也可以选择使用送货地址（假定订单上只有一个送货地址）。媒体网站可选择使用 *`zip`* and *`state`* for registration or ad click-through tracking.

**语法和可能值** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

The *`state`* variable does not impose any special value or format restrictions. There are no limitations on *`state`* outside of the standard variable limitations.

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

* Populate *`state`* on every page that a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

此变量让您可以自定义点击的时间戳，与用于其他平台的 AppMeasurement 库类似。

<!-- 

timestamp.xml

 -->

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 4 字节 | 日期/时间 | 未直接报告。 | 由数据收集服务器设置。 |

**语法** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

The *`timestamp`* variable must be in the format explained in the next section.

>[!IMPORTANT]
>
>Your report suite must be timestamp-enabled by Customer Care before you can use the *`timestamp`* variable. After timestamp support is enabled, all hits sent to this report suite from JavaScript must have a timestamp manually set (using *`s.timestamp`*) or the hits will not be recorded.
>
>Additionally, if you enable timestamp support on a report suite to support offline tracking, all hits sent to this report suite from JavaScript must also have a timestamp manually set (using *`s.timestamp`*). 您无法将已设置时间戳和未设置时间戳的点击发送至同一报表包中。
>
>您也可以使用[可选时间戳](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F)设置，将加盖时间戳和未加盖时间戳的数据混合到同一个全局报表包中，将来自移动设备应用程序的加盖时间戳数据发送到全局报表包中，然后将应用程序升级为无需创建新报表包即可部署时间戳。

**时间戳格式** {#section_C12CBCECCD7047D38EF63A5800761CE9}

时间戳必须是 UNIX 格式（自 1970 年 1 月 1 日以来经过的秒数）或 ISO-8601 格式，并且可接受的 ISO-8601 格式具有以下限制：

* 必须提供日期和时间，中间由 "T" 隔开
* 日期必须是一个全精确度的日历日期（年、月和日）。。不支持周日期和序数日期。
* 日期可以是标准格式或扩展格式（`YYYY-MM-DD` 或 `YYYYMMDD`），但它们必须包含小时和分钟。秒是可选的( `HH:MM`、 `HH:MM:SS`、 `HHMM`或 `HHMMSS`)。 可传入小数格式的分和秒，但小数部分将被忽略。

* An optional time zone can be specified in standard or extended format ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`, or Z)

仍然支持 UNIX 时间戳（自 1970 年 1 月 1 日以来经过的秒数）。

**示例** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

以下列表包含包含有效的 ISO-8601 格式的时间戳示例：

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**配置设置** {#section_5275D206F2CB4009B3681E8C4457124A}

必须首先启用报表包以接受由客户关怀部门提供的自定义时间戳，才能使用此变量。在启用了自定义时间戳之后，发送至报表包的所有点击都必须包含一个时间戳，否则它们将被放弃。

**缺陷、问题和提示** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* 时间戳主要用于跟踪移动平台上的离线数据。自定义时间戳通常处于禁用状态，除非您同时收集同一报表包内的 Web 和离线应用程序数据。
* 当在移动 SDK 中启用离线数据（默认设置），或在任何时候将报表包配置为接受设置时间戳的数据时，数据即会设置时间戳。在移动设备上离线收集的数据可能在发生日期后的数小时或数周内发送。这些点击可能会在 Analytics 平台内排队等候，并且比没有设置时间戳的点击要多等数分钟或数小时：

   * 如果已设置时间戳的数据是在不久之前刚刚发送的，则可能的延迟为 10 至 15 分钟。
   * 如果已设置时间戳的数据是在昨天发送的，则可能的延迟为 2 小时。
   * 如果已设置时间戳的数据是在昨天之前发送的，则每倒退一天增加约 1 小时的延迟，最多累计到 15 天之前，此时延迟会停止增加。

* 启用了时间戳的会话数据会保存长达 92 天。

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

 变量用于第一方 Cookie 实施，以指定写入图像请求和 Cookie 的域名。

<!-- 

trackingServer.xml

 -->

用于非安全页面。如果&#x200B;*`trackingServer`*&#x200B;已定义，则无任何数据发送至 2o7.net。If *`trackingServer`* is not defined (and dc is not defined), data goes to 112.2o7.net.

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | "" |

可在[此处](https://helpx.adobe.com/analytics/kb/determining-data-center.html)查找 Adobe 数据中心列表。

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

 变量用于第一方 Cookie 实施，以指定写入图像请求和 Cookie 的域名。

<!-- 

trackingServerSecure.xml

 -->

用于安全页面。如果 *`trackingServerSecure`* 未定义，SSL 数据将转至 *`trackingServer`*.

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | "" |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

[!UICONTROL 集成数据源使用交易 ID 将离线数据绑定至在线交易（如在线生成的商机或购买）。]

<!-- 

transactionID.xml

 -->

Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. 请参阅[数据源](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 100 字节 | xact | 不适用 | "" |

**启用事务ID存储**{#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Before *`transactionID`* values are recorded, [!UICONTROL Transaction ID Storage] must be enabled for the report suite selected in the Report Suite Manager. 此设置位于

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

To see whether  is enabled for a report suite, go to *`transactionID Storage`*

```
Analytics > Admin > Data Sources > Manage
```

**语法和可能值** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

The *`transactionID`* should contain only alphanumeric characters. 如果在一次点击中记录多个 [!UICONTROL transactionID]，可使用逗号分隔多个值。

**示例** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**缺陷、问题和提示** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* 如果 *`transactionID`* 未启用录制，则值将 *`transactionID`* 被丢弃，并且不可用于集 [!UICONTROL 成数据源]。 Make sure to set a conversion variable or event (an eVar or the events variable) on the page where *`transactionID`* is set. 否则，将不会为 *`transactionID`*.

* 如果您正在为多 [!UICONTROL 个系统(如购买和潜在客户] )记录transactionID，请确保中的值始终 *`transactionID`* 是唯一的。 可通过向 ID 添加前缀（例如 lead_1234 和 purchase_1234）来达到这一目的。[!UICONTROL 如果两次看到唯一数据] ，集成数据源将不能按预期方式工作( [!UICONTROL 数据源数据将绑定到错误]*`transactionID`* 数据)。

* By default,  values are remembered for 90 days. *`transactionID`*&#x200B;如果离线互动过程的时间超过 90 天，请联系客户关怀延长该期限。

>[!NOTE]
>
>The *`transactionID`* variable can contain any character other than a comma. 它应在指定字符限制（100 字节）的相同位置。如果使用多字节字符，则必须启用多字节字符支持，以避免 *`transactionID`*。

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

可根据 变量或 IP 地址/用户代理确认访客。

<!-- 

visitorID.xml

 -->

The *`visitorID`* can be up to 100 alpha-numeric characters and must not contain a hyphen.

如果您显式设置了一个自定义 ID，那么在出现其他 ID 方法之前将始终使用此 ID。

使用顺序如下：s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA。

| ** 最大大小** | ** 调试程序参数** | ** 填充报表** | ** 默认值** |
|---|---|---|---|
| 100 字节 | vid | 不适用 | "" |

**语法和可能值** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

>[!NOTE]
>
>The *`visitorID`* variable should not contain a hyphen.

**示例** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**配置设置** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

无

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

 变量用于识别设置 Cookie 的域。

<!-- 

visitorNamespace.xml

 -->

If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. If *`visitorNamespace`* changes, all visitors reported in Analytics may become new visitors. 访客历史记录将断开当前和将来流量连接。未经 Adobe 代表批准，请不要更改此变量。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | ns | 不适用 | "" |

Analytics 使用 Cookie 来唯一标识访问网站的访客。If *`visitorNamespace`* is not used, the cookie is associated 2o7.net. If *`visitorNamespace`* is used, the cookie is associated with a sub-domain of 2o7.net. 所有访问您网站的访客都应将其 Cookie 与同一域或同一子域关联。

之所以使用&#x200B;*`visitorNamespace`*&#x200B;变量，是为了避免超出浏览器的 Cookie 限制。Internet Explorer 中每个域限制为 20 个 Cookie。通过使用&#x200B;*`visitorNamespace`*&#x200B;变量，其他公司的 Analytics Cookie 将不会与访客的 Cookie 冲突。

**语法和可能值** {#section_EE247FE371784CA4B6058182181F3EA1}

The value of *`visitorNamespace`* must be provided by Adobe and is a string of ASCII characters that don't contain commas, periods, spaces, or special characters.

```js
s.visitorNamespace="company_specific_value"
```

**报表包中的访客识别** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

If you do not specify a `visitorNamespace`, each report suite in your company receives its own visitor ID cookie written as `s_vi_[random string]`. 如果您指定 `visitorNamespace`，那么所有向指定的 `s_vi` 发送数据的报表包都会使用相同的 `trackingServer` Cookie。如果您实施了多包标记，请确保您指定了访客命名空间，这样每个报表包就会使用相同的 Cookie。

**示例** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**配置设置** {#section_1128A2531ECC43DFA6749ECC21F050A2}

无

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

和变量是转换变量。

<!-- 

zip.xml

 -->

这些变量与 eVar 一样均可捕获事件，但不同之处在于，这些变量不是永久性变量。The *`zip`* and *`state`* variables are like eVars that expire immediately.

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 50 字节 | zip | “转化”&gt;“访客资料”&gt;“邮政编码” | "" |

由于 *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. For example, if you are using *`zip`* to compare conversion rates by Zip Code, you should populate *`zip`* on every page of the checkout process. Adobe 推荐使用帐单地址作为邮政编码来源。您也可以选择使用发货地址（假设该订单只有一个发货地址）。媒体网站可选择使用 *`zip`* and *`state`* for registration or ad click-through tracking.

**语法和可能值** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

The *`zip`* variable does not impose any value or format restrictions. There are no limitations on *`zip`* outside of the standard variable limitations.

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
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

