---
description: 计数器存储（有时显示）特定事件或流程的发生次数。
keywords: Analytics Implementation;props;s.prop;custom traffic;counters
solution: Analytics
title: 将 prop 用作计数器
topic: Developer and implementation
uuid: ab83bd7e-10d9-49f9-b9e7-c50397e95c17
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 将 prop 用作计数器

计数器存储（有时显示）特定事件或流程的发生次数。

您可以使用 prop 计算某个事件发生的次数。例如，您希望跟踪网站上 Real Player 与 Windows Media Player 的使用情况。每个页面都包含[!UICONTROL 要粘贴的代码]，在此可以查看 [!UICONTROL s.prop] 变量。使用 [!UICONTROL s.prop] 1 跟踪播放器。对于页面 A，在 [!UICONTROL s.prop]1 中输入一个值表示 Real Player。

```js
s.prop1="RealPlayer"
```

对于页面 B，在 [!UICONTROL s.prop]1 中输入一个类似的值表示 Windows Media Player，如下所示。

```js
s.prop1="WindowsMP"
```

> [!NOTE]Adobe 提供了多达 75 个 [!UICONTROL s.prop] 变量供您使用。

在访客来到您的网站，并访问包含 Real Player 或 Windows Media Player 的页面时，[!DNL Analytics] 能够根据他们访问的页面划分用户区段。然后，[!UICONTROL 自定义流量]报表显示每个页面的访问次数。

> [!NOTE]可定制[!UICONTROL 自定义流量]报表的名称。例如，可以将[!UICONTROL 自定义流量]报表重命名为“Player Types Report”。

