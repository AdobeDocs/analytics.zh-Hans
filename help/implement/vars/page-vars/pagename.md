---
title: pageName
description: 您的网站中页面的名称。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# pageName

`pageName` 变量通常会存储给定页面的名称。确定哪些单个页面最受欢迎很有帮助。此变量会填充“页面名称”维度。

>[!NOTE] 将始终从链接跟踪调用中去除此维度。如果要查看跟踪链接的页面名称，请考虑将此变量复制到 eVar 中。

如果给定的页面跟踪调用中未定义此变量，则将改用 [`pageURL`](pageurl.md) 变量。

## Adobe Experience Platform Launch 中的页面名称

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置页面名称。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在下 [!UICONTROL Actions]面，单击现有 [!UICONTROL Adobe Analytics - Set Variables] 操作或单击“+”图标。
5. 将下拉 [!UICONTROL Extension] 列表设置为Adobe Analytics，将其设置为 [!UICONTROL Action Type] to [!UICONTROL Set Variables]。
6. 找到该 [!UICONTROL Page name] 部分。

您可以将页面名称设置为任何字符串值，包括数据元素。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.pageName

`s.pageName` 变量是一个字符串，通常包含页面名称。其值的最大长度为 100 字节；超出此长度的值会被截断。如果此变量为空，则此截断会包含返回 `pageURL` 的实例。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
