---
description: 按用户类型划分路径区段是一种常见的请求，这种方法便于了解您站点上特定用户类型的路径。
keywords: Analytics 实施
seo-description: 按用户类型划分路径区段是一种常见的请求，这种方法便于了解您站点上特定用户类型的路径。
seo-title: 按用户类型细分路径
solution: Analytics
title: 按用户类型细分路径
topic: 开发人员和实施
uuid: 5c298f39-381d-453b-a608-109e3276 b361
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 按用户类型细分路径

按用户类型划分路径区段是一种常见的请求，这种方法便于了解您站点上特定用户类型的路径。

您可以将用户类型和页面名称合并为 [!UICONTROL sprop]，并为 [!UICONTROL sprop] 启用路径分析。

For example, let's say you have two user types: _Registered_ users and _Non-Registered_ users. 您需要在每个页面上区分这两种用户类型，并将值放置在指定的 [!UICONTROL sprop] 中。在填充该属性时，其内容应如下所示：

```js
 s.prop1=”Registered : “ + s.pageName;
```

如果用户为注册用户，并且访问了主页，则该属性中的值如下所示：

```js
 “Registered : Home Page”
```

如果他们点击名为“Page 2”的另一个页面，则该页面上的值如下所示：

```js
 “Registered : Page 2”
```

如果启用了[!UICONTROL 路径分析]，则会看到这两个值连续显示。若要了解注册用户如何离开主页，请在一个路径报表中找到值“Registered : Home Page”，然后查看他们访问的下一个页面。在此情况下，他们访问的下一个页面为“Page 2”。
