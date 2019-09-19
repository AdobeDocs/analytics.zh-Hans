---
description: 在AppMeasurement.js中设置的配置变量。
keywords: Analytics 实施
seo-description: 在AppMeasurement.js for Adobe Analytics中设置的配置变量
seo-title: 配置变量
solution: Analytics
subtopic: 变量
title: 配置变量
topic: 开发人员和实施
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: edc1ecb471aadb9399664c0985a3aa3ecde328bf

---


# 配置变量

配置变量能够控制报表中捕获和处理数据的方式。最常见的配置变量通常在主全局JavaScript appMeasurement.js中设置。 这些变量可在Analytics页面级别代码和链接中进行设置（如果适用）。

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. 某些配置变量可能并不适用于您站点的实施需求。

使用这些配置变量的部分目的在于：

* 跟踪多个站点/域。
* 购买时可使用任意货币。
* 捕获不同语言的数据。
* 链接跟踪（已下载文件的数量，指向外部站点的链接）。
* 跟踪自定义链接以实现独特的目的。

>[!NOTE]
>
>[!DNL AppMeasurement] 要求在对跟踪函数的初始调用之前设置所有配置变量 `t()`。 如果在调用后设置了配置变量，则可 `t()`能会出现意外结果。 To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

 变量可确定存储和报告数据的报表包。

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. 报表包 ID 由 Adobe 来确定。

**参数**

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 40 字节 | 在 URL 路径中 | 不适用 | 不适用 |

Each report suite ID must match the value created in the [!DNL Admin Console]. 每个报表包 ID 不得大于 40 字节，但所有报表包（整个逗号分隔的列表）的总大小没有任何限制。

在报表中，报表包是区段的最基础级别。您可以设置任意数量的报表包，只要不超过合同允许的最大数量即可。每个报表包都指向 Adobe 收集服务器中填充的一套专用表格。报表包由 JavaScript 代码中的`s_account`变量标识。

在 [!DNL Analytics] 网站中，位于报表左上方的下拉框显示当前的报表包。每个报表包都有一个称为报表包 ID 的唯一标识符。此`s_account`变量包含一或多个接收数据的报表包 ID。[!DNL Analytics] 用户无法查看报表包 ID 的值，且必须由 Adobe 提供或批准后才能使用。Every report suite ID has an associated "friendly name" that can be changed in the report suites section of the [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). 您可以在HTML `s_account` 页面上声明变量，这是在页面值可能不同页面时 `s_account` 的常见做法。 Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. 在某些情况下，的值 `s_account` 也会显示在域中112.2o7.net之前。 路径中的值是唯一确定目标报表包的值。下面的粗体文本显示接收发送数据的报表包，它也会在调试程序中显示。请参阅 [DigitalPulse Debugger](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**语法和可能值** {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

报表包 ID 是 ASCII 字符的字母数字字符串，长度不超过 40 个字节。唯一允许使用的非字母数字字符是连字符。不得使用空格、点号、逗号和其他标点符号。此`s_account`变量可能包含多个报表包，所有报表包都从该页面接收数据。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

Adobe必须提 `s_account` 供或批准所有值。

**示例** {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

**在 Analytics** 中配置变量 {#section_7DFB2CCF02F045AFB1AD4F376638393B}

Adobe [!DNL Customer Care] 可能会更改与各个报表包 ID 关联的易记名称。在 [!DNL Analytics] 网站屏幕左上方的下拉框中可看到易记名称。

**缺陷、问题和提示** {#section_BFFDA5C0AF31442494B0E02F0925CF93}

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. 使用 [!DNL DigitalPulse Debugger] 确定目标报表包。

* 在有些情况下，可以使用 [!DNL VISTA] 更改目标报表包。在使用第一方 Cookie 或您的网站有超过 20 个活动报表包时，建议使用 [!DNL VISTA] 把数据重新路由或复制到另一报表包。

* Always declare `s_account` inside the JS file or just before it is included.

## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

 变量允许您根据各个页面的 URL 动态选择报表包。

>[!NOTE]
>
>`dynamicAccountSelection`无法应用于自定义链接跟踪。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | false |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

**语法和可能值** {#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

 *`dynamicAccountSelection`*.

**示例** {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

**配置设置** {#section_F052FA38144B4F84B015A263A8E711CF}

无

**缺陷、问题和提示** {#section_62F0B0895BC84A05840AEEED0643DE60}

* AppMeasurement for javaScript不支持动态帐 [户选择](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)。
* 通常使用 [!DNL DigitalPulse Debugger] 来确定将由哪个报表包从各页面接收数据。

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

[!DNL AppMeasurement] for JavaScript 可以动态选择数据发送到的报表包。 变量包含用于确定目标报表包的规则。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | "" |

此变量与 和 *`dynamicAccountSelection`* 变 *`dynamicAccountMatch`* 量。 如果将 *`dynamicAccountList`* 中的规 *`dynamicAccountSelection`* 则设置为“true”，则将应用这些规则，并且这些规则适用于中指定的URL部分 *`dynamicAccountMatch`*。

如果中的任何规 *`dynamicAccountList`* 则都与页面的URL不匹配，则使用中标识的报 `s_account` 表包。 此变量中列出的规则按从左到右的顺序应用。如果页面 URL 与多个规则匹配，则使用最左侧的规则确定报表包。因此，应将较通用的规则移动到列表的右侧。

在以下示例中，页面URL已 `www.mycompany.com/path1/?prod_id=12345` 设 `dynamicAccountSelection` 置为 *true* , `s_account` 并且设置为 `mysuitecom.`

| DynamicAccountList 值 | DynamicAccountMatch 值 | 接收数据的报表包 |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1、mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom、mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**语法和可能值** {#section_7360E4354ED345E8BAAE210DBD58A7EC}

The `dynamicAccountList` variable is a semicolon-separated list of name=value pairs (rules). 每个列表段都应包含以下项目：

* 一个或多个报表包 ID（以逗号分隔）
* 一个等号
* 一个或多个 URL 过滤器（以逗号分隔）

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

该字符串中只能使用标准的 ASCII 字符（不允许有空格）。

**示例** {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

**配置设置** {#section_9F99CD741BC7449B8CCC108094B2EB85}

无

**缺陷、问题和提示** {#section_3E10534FCC05457AB67147BB480C8BB3}

* AppMeasurement for javaScript不支持动态帐 [户选择](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)。
* 如果页面 URL 与多个规则匹配，则使用最左侧的规则。
* 如果没有匹配的规则，则使用默认报表包。
* 如果页面被保存到某个人的硬盘，或通过基于 Web 的翻译引擎（如 Google 的翻译页面）进行了翻译，动态帐户选择可能无效。要进行更精确的跟踪，请在服务器端填充`s_account`变量。
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* 使用动态帐户选择时，请确保每次获 *`dynamicAccountList`* 取新域时都进行更新。
* 在尝试确定目标报表包时，请使用 [!DNL DigitalPulse Debugger]。The `dynamicAccountSelection` variable always overrides the value of `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

 变量使用 DOM 对象检索 中所有规则都适用的 URL 的区域。

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' 由于默认值为 [!DNL window.location.host]，因此[!UICONTROL 动态帐户选择]不需要此变量也可使用。有关其他信息，请参 [阅dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51)。

中找到的规 `dynamicAccountList` 则将应用于的值 `dynamicAccountMatch`。 如 `dynamicAccountMatch` 果仅包 [!DNL window.location.host] 含（默认），则中的规则 `dynamicAccountList` 仅适用于页面的域。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | window.location.host |

**语法和可能值** {#section_95CD81972C22419B80A921CA137D3841}

The `dynamicAccountMatch` variable is usually populated by the Adobe consultant who provides the AppMeasurement for JavaScript file. 但下列值可随时应用。

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

**示例** {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

**配置设置** {#**section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

无

**缺陷、问题和提示** {#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* AppMeasurement for javaScript不支持动态帐 [户选择](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8)。
* 页面被保存到硬盘时，[!DNL window.location.host] 为空，从而导致这些页面查看被发送到默认报表包（在 `s_account`).

* 在页面通过基于 Web 的翻译引擎（如 Google）进行了翻译时，[!UICONTROL 动态帐户选择]无法按预期使用。如需更精确的跟踪，请通过服务器端填充 [!UICONTROL s_account] 变量。

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

 变量允许部署应当动态填充的标记变量。

Cookie、请求头和图像查询字符串参数均适用于动态填充。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | D= | 任何 | D= |

**语法和可能值** {#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

或将自定义标记应用于动态变量

```js
s.dynamicVariablePrefix=".."
```

**示例** {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

或将自定义标记应用于动态变量

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

**缺陷、问题和提示** {#section_6889908FBD78488D955F67DDB17617B1}

* 动态变量可通过将值复制到其他变量，大幅缩短 URL 的总长度。
* 动态变量可用于收集头及 Cookie 中的数据（而这些数据是无法通过其他数据收集方式获得的）。

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

charSet属性通常在JavaScript文件中设置，Analytics使用它将传入数据转换为UTF-8，以便Analytics进行存储和报告。

>[!N] 注意：向多字节报表包发送数据时需要charSet属性，而且不应与标准报表包一起使用。 在标准 ISO 报表包中设置 charSet 属性可能会截断变量或意外转换字符。

charSet 属性的值应与 META 标签或 http 头中的网页编码匹配，虽然语法可能略有不同。虽然 META 标签可能会使用编码别名，但 charSet 的值应使用编码首选名称（或正式名称）。

下表列示一些常见编码以及它们的首选名称和别名。

| 首选名称 | 别名 |
|--- |--- |
| ISO-8859-1 | ISO_8859-1,CP819,latin1 |
| ISO-8859-2 | ISO_8859-2,latin2 |
| ISO-8859-5 | ISO_8859-5,cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

由于存在大量编码和别名，请联系实施顾问或Adobe客户关怀，确认charSet的正确值（如果它未出现在上表中）。

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

charSet 参数若有非空白值将导致数据转换为 UTF-8 后存储。128-255 范围的所有字符将转换为合适的 UTF-8 双字节序列并存储。这些字符在标准报表包中无法正常显示。因此，在标准报表包中不得使用 charSet 属性。

同样地，charSet 参数若为空值，将跳过数据转换过程，而 128-255 范围的所有字符将以单字节存储。由于这些字符的单字节代码在 UTF-8 中无效，所以它们无法在多字节报表包中正常显示。因此，在多字节报表包中应始终使用 charSet 参数。此外，网页编码时应使用合适的值。

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. 但是，如果页面上的变量包含非ASCII字符，则必须填 *`charSet`* 充该变量。

**参数**

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | CE | 不适用 | "" |

**语法和可能值** {#section_EBC2176067A04D9E814CF78A86DC80FA}

```js
s.charSet="character_set"
```

**示例** {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

 变量确定收入使用的兑换率。

所有货币额都是以您选择的货币进行存储的。如果选择的货币与 *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied.

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | cc | “转化”&gt;“购买”&gt;“收入” 显示收入或货币值的所有转化报表 | "USD" |

如果网站允许访客以多种货币购买，则应使用&#x200B;*`currencyCode`*&#x200B;变量以确保收入以相应的货币进行存储。For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. 数据收集接收到数据后，将使用货币兑换率将 40 欧元兑换为等值的美元。

如果支持以多种货币销售，则建议填充 HTML 页面中的&#x200B;*`currencyCode`*&#x200B;变量，而不是 JavaScript 文件中的变量。如果要使用您自己的折换率而不是Adobe使用的折换率，请将该值设 *`currencyCode`* 置为与报表包的基本货币相等。 然后在将收入发送到 [!DNL Analytics] 之前兑换所有收入。

货币兑换适用于收入和任何货币事件。这些事件用于计算与收入类似的值的总和，例如税款和运输费用。收入和货币事件在产品字符串中指定。有关产品的详细信息，请参阅 [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE).

**语法和可能值** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

**示例** {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

**配置设置** {#section_D05E29F545A04958B1C0A82248BCA1B0}

Adobe [!DNL Customer Care] 可以更改报表包的默认货币设置。更改报表包的本位币时，不会兑换系统中的现有收入，但会相应地兑换所有新收入值。

**缺陷、问题和提示** {#section_08A80A87B54A4861905953A6FA61FF8F}

* 如果您注意到报表中的收入数额惊人，请确 *`currencyCode`* 保报表包的变量和基本货币设置正确。
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* 货币事件不应用于非货币用途。如需计算非货币的任意值或动态值，请使用[!UICONTROL 数值]事件类型。
* 在&#x200B;*`currencyCode`*&#x200B;变量为空时，不会发生兑换。

有关详细信息，请参阅 [货币代码](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html)。

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. 例如，您可以使用以下代码在完全限定的页面名称处设置 Cookie：

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. 某些插件还会使用此变量来确定要设置插件 Cookie 的正确域。

默认值为“ *`cookieDomainPeriods`* 2”。 This is the value that is used if *`cookieDomainPeriods`* is omitted. 例如，使用域 `www.mysite.com`时 *`cookieDomainPeriods`* 应为“2”。 因 `www.mysite.co.jp`为 *`cookieDomainPeriods`* 应该是"3"

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

例如，如果在域 *`cookieDomainPeriods`* 上设置为“2”，则 `www.mysite.co.jp`会在域 `s_cc` 上创建和 `s_sq` cookies `co.jp`。 由于 `co.jp` 是无效的域，所有浏览器都会拒绝这些 Cookie。因而，访客点击图数据会丢失，并且[!UICONTROL “访客资料”]&gt;[!UICONTROL “技术”]&gt;[!UICONTROL “Cookie”]报表指示几乎所有访客都拒绝这些 Cookie。

如果&#x200B;*`cookieDomainPeriods`*&#x200B;被设置为 "3"，而域仅包含两个句点，则 JavaScript 文件会尝试在网站的子域上设置 Cookie。例如，如果在域 *`cookieDomainPeriods`* 上设置为“3”，则 `www2.mysite.com`会在域 `s_cc` 上创建和 `s_sq` cookies `www2.mysite.com`。 When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. 例如， `store.toys.mysite.com` 仍将设 *`cookieDomainPeriods`* 置为“2”。 此变量定义可以在根域 [!DNL mysite.com] 上正确设置 Cookie。Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

另请参 [阅s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274)。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | CDP | 影响多个报表，因为它控制访客 ID 的存储和处理方式。 | "2" |

>[!NOTE]
>
>某些云计算服务被视为顶级域，不允许写入Cookie。 (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) 如果您在这些服务上进行实施，则可能会受到 Analytics 隐私设置的影响，因为如果您还没有设置自己的域（例如，如果您正在测试您的实施），那么该设置会删除已阻止所有 Cookie 的用户。在这种情况下，如果系统已确定其 Cookie 已禁用，则不可用或不可访问的点击会被禁止，因此会从报表中排除。

**示例** {#section_4218BE29FA5E49F58975A2094329B268}

手动设置变量：

```js
s.cookieDomainPeriods = "3";
```

在核心 JavaScript 文件同时包含以下两种情况时，动态设置变量的若干示例：

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

**缺陷、问题和提示** {#section_F3BE3F039E5C4359B694DBB61369822C}

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. 在访客切换子域时，这可能会导致数据丢失。
* The 变量 *`cookieDomainPeriods`* 在设置访客ID cookie之前已弃 *`trackingServer`* 用的实施中使用。 虽然代码过时，但在这种情况下未正确定 *`cookieDomainPeriods`* 义，使您的实施面临数据丢失的风险。

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

 变量适用于由 JavaScript 设置的内置第一方 Cookie（s_sq、s_cc、插件），即使您的实施使用的是第三方 2o7.net 或 omtrdc.net 域。

The *`fpCookieDomainPeriods`* variable should never be dynamically set . 如果您使 *`cookieDomainPeriods`*&#x200B;用，则最好也为指定一个 *`fpCookieDomainPeriods`* 值。 *`fpCookieDomainPeriods`* 继承该 *`cookieDomainPeriods`* 值。 Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

名称“ *`fpCookieDomainPeriods`*”指句点数(“”)“www”开头的域中句点 (.) 的数量。For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

for JavaScript [!DNL AppMeasurement] 文件使用变量确 *`fpCookieDomainPeriods`* 定用哪个域来设置访客ID  (s_vi)Cookie以外的第一方Cookie。 至少有两个 Cookie 会受此变量影响，包括 s_sq 和 s_cc（分别用于访客点击图和 Cookie 检查）。[!UICONTROL getValOnce] 等插件使用的 Cookie 也会受到影响。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | cookieDomainPeriods |

**设置 Cookie 域变量的示例代码** {#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

**语法和可能值** {#section_87923F4C12E74AF99CC9AFC0FFD77D49}

The *`cookieDomainPeriods`* variable is expected to be a string, as shown below.

```js
s.fpCookieDomainPeriods="3"
```

**示例** {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

**配置设置** {#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

无

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

 变量由 JavaScript 和数据收集服务器用来确定 Cookie 的有效期。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | cl | “流量”&gt;“技术”&gt;“Cookie”所有与访客有关的报表 | "" |

如果设置了&#x200B;*`cookieLifetime`*，它会覆盖 JavaScript 和数据收集服务器的任何其他 Cookie 过期日期，但有一种情况除外，下文对此进行了介绍。The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookie
* Cookie
* JavaScript 设置和插件

**语法和可能值** {#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

可能值如下所示：

* ""
* "NONE"
* "SESSION"
* 表示过期前剩余秒数的整数

**示例** {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

**配置设置** {#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

无

**缺陷、问题和提示** {#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* 影响跟 [!DNL Analytics] 踪。 If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. 务请小心设置 *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

 变量是 函数的一个引用，允许在 JavaScript 文件内的合适位置调用 函数。

The *`s_doPlugins`* function is called each time any of the following occurs:

* 函 *`t()`* 数被调用
* 函 *`tl()`* 数被调用
* 点击退出或下载链接时
* 点击由访客 ClickMap 跟踪的任意页面元素时

The *`doPlugins`*&#x200B;函数用于运行自定义例程，以收集或更改数据。If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. 例如，如果对象名为s_mc，则函 *`s_doPlugins`* 数应称为s_mc_doPlugins。

**语法和可能值** {#section_5CFB94598521455E80947964A306EA89}

函 *`s_doPlugins`* 数不应用引号引起来，并且应始终为函数的确切名 *`doPlugins`**`s_doPlugins`* 称（如果该函数已重命名）分配。

```js
s.doPlugins=s_doPlugins;
```

**示例** {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

**配置设置** {#section_641F0EC55E3349E5A3F8671446797074}

无

**缺陷、问题和提示** {#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* 只有当您与其他客户共享内容或提取其他客户的内容时，才需要更改对象名称（例如从 s 更改为 s_mc）。重命名 *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* 如果您意外地开始从其他Adobe客户处提取内容，并且您的 *`s_doPlugins`* 函数正被覆盖，则可以只重命名该函数，而不更改 *`s_doPlugins`* 对象名称。 最好的解决方案是在同一页面上使用与 JavaScript 文件不同的其他对象名称，但并不要求这样做。

## s.registerPreTrackCallback和s.registerPostTrackCallback

这些函数的参数是：“callback”（一个函数）以及“callback”函数包含的参数。例如：

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

注册 callback 时，可通过 `requestUrl` 以及传递的任何参数来调用 callback。根据用来注册 callback 的方法，调用操作可以在跟踪调用之前或跟踪调用之后发生

无法保证调用这些 callback 的顺序。当创建了最终跟踪 URL 后，将调用在 pre 函数中注册的 callback。如果是成功的跟踪调用，则调用 post callback（若跟踪调用失败，则不调用这些函数）。`registerPreTrackCallback` 中注册的任何 callback 都不会影响跟踪调用。此外，不建议在任何已注册的 callback 中调用任何跟踪方法，因为这可能会导致无限循环。

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

如果希望跟踪网站上可下载文件的连接，请将 设置为“true”。

如果 *`trackDownloadLinks`* 为“true”，则用 *`linkDownloadFileTypes`* 于确定哪些链接是可下载文件。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | true |

如果没有指向网站上可下载文件的链接，或者不想跟踪可下载文件的点击次数，则应将&#x200B;*`trackDownloadLinks`*&#x200B;变量设置为“false”。If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. 与下载链接一起发送的数据包括链接下载 URL 以及该链接的访客点击图数据。如果 *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

**语法和可能值** {#section_828492CC2A144BC68D18C30CF397EEFC}

*`trackDownloadLinks`变量应为“true”或“false”。*

**示例** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

**配置设置** {#section_9A5F69966BAF433A8DA2BCF655A652D1}

无

**缺陷、问题和提示** {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

如果为“true”，则用于确定单击的任何链接是否为退出链接。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | true |

如果没有指向网站上可下载文件的链接，或者不想跟踪可下载文件的点击次数，则应将&#x200B;*`trackExternalLinks`*&#x200B;变量仅设置为“false”。退出链接为任何让访客退出网站的链接。如果将 *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. 随退出链接一起发送的数据包括链接 URL、链接名称和该链接的访客 ClickMap 数据。如果将 *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

**语法和可能值** {#section_267748949A7544658E1D838AAEF964B2}

*`trackExternalLinks`变量应为“true”或“false”。*

```
js
s.trackExternalLinks=true|false
```

**示例** {#section_EF18DB05884240F5B5062631E68E10A7}

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

**配置设置** {#section_C8748CFE36324FAFB14C23E3E1FB5082}

无

**缺陷、问题和提示** {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

 变量可用于确定是否收集 ClickMap 数据。

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | ClickMap | false |

**语法和可能值** {#section_46B2C1DD0D104A01A9C239929420CD90}

```
js
s.trackInlineStats=true|false
```

*`trackInlineStats`变量应为“true”或“false”。*

**示例** {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

**配置设置** {#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

无

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

 变量是以逗号隔开的文件扩展名列表。

如果您网站上包含的链接可转到具有任何此类扩展名的文件，则这些链接的 URL 会在[!UICONTROL 文件下载]报表中显示。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | 不适用 | “流量”&gt;“网站流量”&gt;“文件下载” | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

The 变 *`linkDownloadFileTypes`* 量仅在设置为“ *`trackDownloadLinks`* True”时才相关。

只有在链接上单击鼠标左键才会计入[!UICONTROL 文件下载]报表。在页面加载时自动启动的所有文件下载，或仅在重定向后启动的下载，不会计入[!UICONTROL 文件下载]报表。当您右键单击某文件并选择“将目标另存为...”选项时，不会将它计入[!UICONTROL 文件下载]报表。

The *`linkDownloadFileTypes`*&#x200B;变量可用于跟踪 RSS 馈送的点击量。如果您有带。xml或其他扩展名的RSS源链接，则在列表后面附加“,xml” *`linkDownloadFileTypes`* 可查看每个RSS链接的单击频率。

**语法和可能值** {#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

只包含文件扩展名（无空格）。

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

列表中可包含任意文件扩展名。注意不要在 *`linkDownloadFileTypes`*。这样做会导致每次点击时发送额外的图像请求，从而产生主服务器调用计费。

**示例** {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

**配置设置** {#section_CE24D5852E4D441A958A4EDDB82382A7}

无

**缺陷、问题和提示** {#section_786CF22D5553429EB6524B13774793BC}

* 只有左键单击下载文件会导致 URL 在[!UICONTROL 文件下载]报表中显示。
* 在&#x200B;*`linkDownloadFileTypes`*&#x200B;中包含常用文件扩展名可能会显著增加发送到 Adobe 服务器的总服务器调用次数。
* 指向服务器端重定向页面或 HTML 页面自动下载文件的链接不会被计入文件下载报表，除非其文件扩展名包含在 *`linkDownloadFileTypes`*.
* 使用 JavaScript 的链接（如 javascript:openLink( )）不会被计入文件下载中。

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

 变量用于确定您网站中哪些链接为退出链接。

它是以逗号隔开的过滤器列表，显示属于网站一部分的链接。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | “路径”&gt;“登录和退出”&gt;“退出链接” |  |

>[!NOTE]
>
>我们之前曾建议将linkInternalFilters设置为javascript:。 但是，这导致所有的域（包括标签当前所在的域）都被视为外部域。因此，如果您想让一些域被视为内部域，则可以添加一些内容，如以下示例所示。

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. 无论退出链接的目标窗口是弹出窗口还是现有窗口，都不会影响该链接在退出链接报表中的显示。如果 *`trackExternalLinks`* 设置为 `"true"`. （有关 DTM 如何处理退出链接的信息，请参阅“动态标签管理”文档中的[链接跟踪](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html)。）中的过滤 *`linkInternalFilters`* 器不区分大小写。

中的过滤器列表默 *`linkInternalFilters`* 认应用于任何链接的域和路径。 If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). 过滤器通常应用于 URL 的绝对路径，即使将相对路径用作 href 值也不例外。

请小心确认您网站的所有域名（以及使用您的 JavaScript 文件的任何合作伙伴）都包含在 *`linkInternalFilters`*。如果列表中未包含所有的域名，则未包含的域名的所有相关链接都将被视为退出链接，这会增加所发送的服务器调用次数。如果希望多个域或公司对JavaScript文件使用一个 [!DNL AppMeasurement] ，您可以考虑在页面上填充 *`linkInternalFilters`* ，覆盖JavaScript文件中指定的值。 如果您有立刻重定向到主域的虚域，则无需将这些虚域加入此列表。

以下示例说明此变量的使用方法。In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

**语法和可能值** {#section_810966F09912415B96EA9C2EDAE0CEA0}

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. 不允许有空格。

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

**示例** {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

**配置设置** {#section_546AC1FACB664ABFBCF312990097C987}

无

**缺陷、问题和提示** {#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* 定期检查“[!UICONTROL 路径]”&gt;“[!UICONTROL 登入和退出]”&gt;“[!UICONTROL 退出]”链接报表，以确保报表中的所有条目正确无误。

* 定期检查合作伙伴合同，以确定它们是否包含关于链接跟踪的限制。例如，系统可能会禁止跟踪链接在合作伙伴显示广告中显示。通过将合作伙伴的域加入 *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeaveQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

默认情况下，查询字符串被排除在所有报表之外。

对于一些退出链接和下载链接而言，URL 的重要部分可能位于查询字符串中，如下面的示例 URL 中所示。

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

下载文件名称可在查询字符串中定义，因而查询字符串对于提高[!UICONTROL 文件下载]报表的准确度是必需的。

The *`linkLeaveQueryString`*&#x200B;变量确定[!UICONTROL 退出链接]和[!UICONTROL 文件下载]报表中是否包含查询字符串。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|--- |--- |--- |--- |
| 不适用 | 不适用 | 退出链接文件下载 | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

**语法** {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

**示例** {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

**可能值** {#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

**配置设置** {#section_835FD74D3CA9425A9D091CACF88A6F1F}

此变量不需要任何配置。

**缺陷、问题和提示** {#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

 变量是随自定义、退出和下载链接一起发送的、以逗号隔开的变量列表。

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. 为避免与其他变量关联的实例或页面查看次数增加，Adobe建议 *`linkTrackVars`* 在用于链 *`linkTrackEvents`* 接跟踪的链 [!UICONTROL 接的onClick] 事件中填充这些变量。

所有应随链接数据（自定义、退出和下载链接）一起发送的变量都应在 *`linkTrackVars`*. 如果 *`linkTrackEvents`* 使用， *`linkTrackVars`* 应包含“events”。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 任何 | "无" |

在填充 *`linkTrackVars`*, do not use the 's.' prefix for variables. 例如，您应该用“ *`linkTrackVars`* prop1”填充它，而不是使用“s.prop1”填充。 以下示例说明了 *`linkTrackVars`* 如何使用。

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

由于指向 google.com 的链接为退出链接（除非您就是 Google），event1 和 eVar1 将随退出链接数据一起发送，从而增加与 eVar1 关联的实例以及 event1 的触发次数。In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

**语法和可能值** {#section_DCC239F5CFE74959856764DAB1862BA7}

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. 使用“eVar1”而不是“s.eVar1”。

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

The 变 *`linkTrackVars`* 量只能包含发送到的变 [!DNL Analytics]量，即： *`events`*、 *`campaign`*、 *`purchaseID`*、 *`products`* eVar1-75 [!UICONTROL 、]prop1-75、prop [!UICONTROL -75、prop-5、]*`channel`**`server`**`state`**`zip`**`pageType`*-5、Chrop、Chrop、Chrop、Chrop、Chrop、Chrop、Chrop、Chrop、C。

**示例** {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

**配置设置** {#section_E387604B8A434A7F89A82A886649A89D}

无

**缺陷、问题和提示** {#section_99E0783A608C4462945F35D21AB4AC2B}

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* 如果 *`linkTrackEvents`* 使用， *`linkTrackVars`* 则必须包含“events”。

* 请勿使用“s.”或“s_objectname.”作为变量的前缀。

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

在指向 [!DNL help.php] 的第一个链接中，注意事件变量保留了在点击链接前设置的值，这样可允许 event1 随自定义链接一起发送。在第二个示例，即指向 [!DNL test.php] 的链接中，没有记录 event2，因为它未在 *`linkTrackEvents`*.

为避免混淆和潜在问题，Adobe建议 *`linkTrackVars`* 在用于链 *`linkTrackEvents`* 接跟踪的链 [!UICONTROL 接的onClick事件中填充] 。

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. 此变量仅在包含“ *`linkTrackVars`* events”时才被考虑。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 转化 | "无" |

**语法和可能值** {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

The *`linkTrackEvents`* variable is a comma-separated list of events (no spaces).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

在 *`linkTrackEvents`*. These events are listed in [Events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). 如果事件名称前后出现空格，则此事件不会随任何链接图像请求一起发送。

**示例** {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

**配置设置** {#section_D938A47346D94A0C9E98FB327F2EF349}

无

**缺陷、问题和提示** {#section_DBB68BECC9D44380816113DB2566C38C}

* JavaScript文件仅在包含 *`linkTrackEvents`* “ *`linkTrackVars`* events”变量时使用。 仅当定义“事件”时，才 *`linkTrackVars`* 应将“事 *`linkTrackEvents`* 件”包含在中。

* 请注意是否有事件在页面上触发，并在 *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

如果您的网站包含许多指向外部网站的链接，并且您不希望跟踪所有退出链接，则可使用 报告退出链接的特定子集。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | “路径”&gt;“登录和退出”&gt;“退出链接” | "" |

The 变 *`linkExternalFilters`* 量是与一起使用的可选变量，用 *`linkInternalFilters`* 于确定链接是否为退出链接。 退出链接定义为将访客带离您网站的任何链接。无论退出链接的目标窗口是弹出窗口还是现有窗口，都不会影响该链接在退出链接报表中的显示。仅在 *`trackExternalLinks`* is set to 'true.' 和中的过滤 *`linkExternalFilters`* 器不 *`linkInternalFilters`* 区分大小写。

>[!NOTE]
>
>如果您不想使用，请删 *`linkExternalFilters`*&#x200B;除它或将其设置为“”。

过滤器列在中， *`linkExternalFilters`* 并默 *`linkInternalFilters`* 认情况下应用于任何链接的域和路径。 如 *`linkLeaveQueryString`* 果设置为“true”，则过滤器将应用于整个URL（域、路径和查询字符串）。 这些过滤器始终应用于 URL 的绝对路径，即使将相对路径用作 href 值也不例外。

大部分公司发现通过 *`linkInternalFilters`* 足可控制退出链接，他们不需要 *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

以下示例说明此变量的使用方法。In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

**语法和可能值** {#section_E35DAAAE8BDE44CEB8F6763EF1344693}

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. 不允许有空格。

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

URL 的任何部分均可包含于 *`linkExternalFilters`*, separated by commas.

**示例** {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

**配置设置** {#section_2D0CA911855B4B3698145FC18D5021C3}

无

**缺陷、问题和提示** {#section_8B40E6F539E3473B934A8DB7C5086D73}

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. 请勿使用此变量来强制 *`linkInternalFilters`* 内部链接成为退出链接。

* 如 *`linkExternalFilters`* 果应将其应用于链接的查询字符串，请确 *`linkLeaveQueryString`* 保设置为“true”。 See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

如 [!UICONTROL 果usePlugins] 为“true”，则在每 *`s_doPlugins`* 个图像请求之前调用函数。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | 不适用 | 不适用 | true |

**语法和可能值** {#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

[!UICONTROL usePlugins] 变量应为“true”或“false”。

**示例** {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

如 [!UICONTROL 果JavaScript文件中未声明函数，则]*`s_doPlugins`* usePlugins变量应为false（或未声明）。

**配置设置** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

无