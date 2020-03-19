---
title: visitorNameSpace
description: 已弃用的变量，用于确定cookie域。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# visitorNamespace

> [!IMPORTANT] 此变量已停用。 请改 [`trackingServer`](trackingserver.md) 用。

在Adobe Analytics的早期版本中，AppMeasurement使 `visitorNameSpace` 用变量帮助确定存储访客Cookie `2o7.net` 的子域。 现代浏览器中增加的隐私权惯例使第三方Cookie变得不那么可靠。 随着和变量的 `trackingServer` 引入 [`trackingServerSecure`](trackingserversecure.md) , `visitorNameSpace` 不再需要。

> [!TIP] Adobe建议在您的网站上使用第一方Cookie。 第一方Cookie不使用此变量。

## Adobe Experience Platform Launch中的访客命名空间

[!UICONTROL Visitor Namespace] 是配置Adobe Analytics扩展 [!UICONTROL Cookies] 时accordion下的字段。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到选项卡， [!UICONTROL Extensions] 然后单击“Adobe Analytics” [!UICONTROL Configure] 下的按钮。
4. 展开可 [!UICONTROL Cookies] 折叠面板，以显示 [!UICONTROL Visitor Namespace] 字段。

Adobe建议不要使用此字段。 请改 `trackingServer` 用 `trackingServerSecure` 和。

## AppMeasurement和Launch自定义代码编辑器中的s.visitorNamespace

变 `s.visitorNamespace` 量是一个字符串，其中包含每个组织的唯一值。 旧版AppMeasurement库在从旧版Adobe Analytics下载时会自动包含此唯一值。 当前AppMeasurement库不使用此变量，除非 `trackingServer` 且 `trackingServerSecure` 未设置。

如果您的组织仍需要此变量，请选取一个表示您的组织的值。 您可以将此值存储在解决方案 [设计文档中](../../prepare/solution-design.md)。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
