---
title: Util.cookieRead
description: 获取 Cookie 的值。
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '171'
ht-degree: 100%

---

# Util.cookieRead

Cookie 可以在同一域上的不同页面中存储和检索信息。使用 `Util.cookieRead()` 方法从 Cookie 检索值。

## 使用 Adobe Experience Platform 中的标记的“读取 Cookie”

您可以通过在数据元素中设置值来读取 Cookie。

1. 使用您的 Adobe ID 凭据登录[数据收集 UI](https://experience.adobe.com/data-collection)。
2. 单击所需的属性。
3. 转到[!UICONTROL 数据元素]选项卡，然后单击所需的数据元素（或创建数据元素）。
4. 将[!UICONTROL 扩展]下拉列表设置为[!UICONTROL 核心]，将[!UICONTROL 数据元素类型]设置为 [!UICONTROL Cookie]。
5. 在文本字段中输入 Cookie 名称。

Cookie 值会存储在数据元素中。然后，您可以引用规则中的数据元素来分配 Analytics 变量。

## AppMeasurement 和自定义代码编辑器中的 s.Util.cookieRead()

调用 `s.Util.cookieRead()` 方法可读取所需的 Cookie 值。其唯一参数是一个字符串，且是必需参数。此方法会返回包含 Cookie 值的字符串。如果 Cookie 不存在，则会返回空字符串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
