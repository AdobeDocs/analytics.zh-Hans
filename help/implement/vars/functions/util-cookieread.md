---
title: Util.cookieRead
description: 获取 Cookie 的值。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Util.cookieRead

Cookies可以在同一域上跨页面存储和检索信息。 使用 `Util.cookieRead` 该方法从Cookie检索值。

## 阅读Adobe Experience Platform Launch中的cookies

您可以通过在数据元素中设置值来读取cookie。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“数 [!UICONTROL 据元素] ”选项卡，然后单击所需的数据元素（或创建数据元素）。
4. 将“扩 [!UICONTROL 展] ”下拉列表设 [!UICONTROL 置为Core]，将“元 [!UICONTROL 素类型”数据设] 置为 [!UICONTROL Cookie Type]。
5. 在文本字段中输入Cookie名称。

cookie值存储在数据元素中。 然后，您可以引用规则中的数据元素来分配Analytics变量。

## AppMeasurement中的s.Util.cookieRead()和启动自定义代码编辑器

调用该 `s.Util.cookieRead()` 方法以读取所需的cookie值。 其唯一参数是字符串，这是必需的。 此方法返回包含cookie值的字符串。 如果Cookie不存在，则返回空字符串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
