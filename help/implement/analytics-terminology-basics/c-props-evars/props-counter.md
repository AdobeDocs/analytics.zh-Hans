---
description: 计数器存储（有时显示）特定事件或流程的发生次数。
keywords: Analytics实施；props；s. prop；自定义流量；计数器
seo-description: 计数器存储（有时显示）特定事件或流程的发生次数。
seo-title: 使用prop作为计数器
solution: Analytics
title: 使用prop作为计数器
topic: 开发人员和实施
uuid: ab83bd7e-10d9-49f9-b9 e7-c50397 e95 c17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用prop作为计数器

计数器存储（有时显示）特定事件或流程的发生次数。

您可以使用 prop 计算某个事件发生的次数。例如，您希望跟踪网站上 Real Player 与 Windows Media Player 的使用情况。每个页面都包含[!UICONTROL 要粘贴的代码]，在此可以查看 [!UICONTROL s.prop] 变量。使用 [!UICONTROL s.prop] 1 跟踪播放器。对于页面 A，在 [!UICONTROL s.prop]1 中输入一个值表示 Real Player。

```js
s.prop1="RealPlayer"
```

对于页面 B，在 [!UICONTROL s.prop]1 中输入一个类似的值表示 Windows Media Player，如下所示。

```js
s.prop1="WindowsMP"
```

>[!NOTE]
>
>Adobe offers up to 75 [!UICONTROL s.prop] variables for you to use.

在访客来到您的网站，并访问包含 Real Player 或 Windows Media Player 的页面时，[!DNL Analytics] 能够根据他们访问的页面划分用户区段。然后，[!UICONTROL 自定义流量]报表显示每个页面的访问次数。

>[!NOTE]
>
>The name of the [!UICONTROL Custom Traffic] report can be customized. 例如，可以将[!UICONTROL 自定义流量]报表重命名为“Player Types Report”。

