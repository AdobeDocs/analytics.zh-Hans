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


# visitorNamespace

 变量用于识别设置 Cookie 的域。

<!-- 

visitorNamespace.xml

 -->

如果在 JavaScript 文件中使用 *`visitorNamespace`*，请不要将其删除或进行更改。如果更改 *`visitorNamespace`*，则所有在 Analytics 中报告的访客都可能会变成新访客。访客历史记录将断开当前和将来流量连接。未经 Adobe 代表批准，请不要更改此变量。

| 最大大小 | 调试程序参数 | 填充报表 | 默认值 |
|---|---|---|---|
| 不适用 | ns | 不适用 | "" |

Analytics 使用 Cookie 来唯一标识访问网站的访客。如果未使用 *`visitorNamespace`*，则 Cookie 将与 2o7.net 关联。如果使用 *`visitorNamespace`*，则 Cookie 将与 2o7.net 的子域关联。所有访问您网站的访客都应将其 Cookie 与同一域或同一子域关联。

之所以使用&#x200B;*`visitorNamespace`*&#x200B;变量，是为了避免超出浏览器的 Cookie 限制。Internet Explorer 中每个域限制为 20 个 Cookie。通过使用&#x200B;*`visitorNamespace`*&#x200B;变量，其他公司的 Analytics Cookie 将不会与访客的 Cookie 冲突。

**语法和可能值** {#section_EE247FE371784CA4B6058182181F3EA1}

*`visitorNamespace`* 的值必须由 Adobe 提供，并且为不包含逗号、句点、空格或特殊字符的 ASCII 字符串。

```js
s.visitorNamespace="company_specific_value"
```

**报表包中的访客识别** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

如果您没有指定 `visitorNamespace`，贵公司的每个报表包都会收到它自己的访客 ID Cookie，其编写格式为 `s_vi_[random string]`。如果您指定 `visitorNamespace`，那么所有向指定的 `s_vi` 发送数据的报表包都会使用相同的 `trackingServer` Cookie。如果您实施了多包标记，请确保您指定了访客命名空间，这样每个报表包就会使用相同的 Cookie。

**示例** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**配置设置** {#section_1128A2531ECC43DFA6749ECC21F050A2}

无
