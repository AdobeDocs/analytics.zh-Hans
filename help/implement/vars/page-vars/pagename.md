---
title: pageName
description: 站点上页面的名称。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# pageName

变 `pageName` 量通常存储给定页面的名称。 确定哪些页面最受欢迎很有帮助。 此变量填充“页面名称”维。

> [!NOTE] 此维始终从链接跟踪调用中去除。 如果要查看跟踪链接的页面名称，请考虑将此变量复制到eVar中。

如果给定的页面跟踪调用中未定义此变量，则 [`pageURL`](pageurl.md) 会改用该变量。

## Adobe Experience Platform Launch中的页面名称

您可以在配置Analytics扩展时（全局变量）或根据规则设置页面名称。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Rules] 然后单击所需的规则（或创建规则）。
4. 在下 [!UICONTROL Actions]面，单击现有 [!UICONTROL Adobe Analytics - Set Variables] 操作或单击“+”图标。
5. 将下拉 [!UICONTROL Extension] 列表设置为Adobe Analytics，将其设置为 [!UICONTROL Action Type] to [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Page name] section.

可以将页面名称设置为任何字符串值，包括数据元素。

## AppMeasurement中的s.pageName和启动自定义代码编辑器

变 `s.pageName` 量是一个字符串，通常包含页面名称。 最大值为100字节；长值被截断。 此截断包括实例，如果此变量为空， `pageURL` 则该实例会返回。

```js
// Set page name to a static value
s.pageName = "Example page name";

// Set page name to the page's title
s.pageName = window.document.title;
```
