---
title: Util.cookieRead
description: 获取 Cookie 的值。
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 72%

---

# Util.cookieRead

Cookie 可以在同一域上的不同页面中存储和检索信息。使用 `Util.cookieRead()` 方法从 Cookie 检索值。

## 使用Adobe Analytics扩展和Web SDK扩展读取Cookie

您可以通过在数据元素中设置值来读取 Cookie。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 数据元素]选项卡，然后单击所需的数据元素（或创建数据元素）。
4. 将[!UICONTROL 扩展]下拉列表设置为&#x200B;**[!UICONTROL 核心]**，将[!UICONTROL 数据元素类型]设置为&#x200B;**[!UICONTROL Cookie]**。
5. 在文本字段中输入 Cookie 名称。

Cookie 值会存储在数据元素中。然后，您可以引用规则中的数据元素来分配所需的变量。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.Util.cookieRead()

调用 `s.Util.cookieRead()` 方法可读取所需的 Cookie 值。其唯一参数是一个字符串，且是必需参数。此方法会返回包含 Cookie 值的字符串。如果 Cookie 不存在，则会返回空字符串。

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
