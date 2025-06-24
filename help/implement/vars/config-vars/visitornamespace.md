---
title: visitorNameSpace
description: （已停用）帮助确定第三方Cookie域。
feature: Appmeasurement Implementation
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 89%

---

# visitorNamespace

>[!IMPORTANT]
>
>此变量已停用。请改用 [`trackingServer`](trackingserver.md)。

在 Adobe Analytics 的早期版本中，AppMeasurement 使用 `visitorNameSpace` 变量帮助确定访客 Cookie 存储在 `2o7.net` 的哪个子域中。现代浏览器中增加的隐私权惯例使第三方 Cookie 变得不那么可靠。随着 `trackingServer` 和 [`trackingServerSecure`](trackingserversecure.md) 变量的引入，不再需要使用 `visitorNameSpace`。

>[!TIP]
>
>Adobe 建议在您的网站上使用第一方 Cookie。第一方 Cookie 不使用此变量。

## 使用Adobe Analytics扩展的访客命名空间

[!UICONTROL 访客命名空间]是配置 Adobe Analytics 扩展时位于 [!UICONTROL Cookie] 折叠面板下的字段。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
4. 展开 [!UICONTROL Cookie] 折叠面板，这会显示[!UICONTROL 访客命名空间]字段。

Adobe 建议不要使用此字段。请改用 `trackingServer` 和 `trackingServerSecure`。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.visitorNamespace

`s.visitorNamespace` 变量是一个字符串，其中包含每个组织的唯一值。在通过 Adobe Analytics 早期版本下载旧版 AppMeasurement 库时，该库会自动包含此唯一值。当前 AppMeasurement 库不使用此变量，除非未设置 `trackingServer` 和 `trackingServerSecure`。

如果贵组织仍需要此变量，请选取一个值来代表贵组织。您可以将此值存储在[解决方案设计文档](../../prepare/solution-design.md)中。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
