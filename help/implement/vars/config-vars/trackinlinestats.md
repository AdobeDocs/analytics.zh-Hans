---
title: trackInlineStats
description: （已停用）在实施中启用或禁用ClickMap。
keywords: 禁用clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 30%

---

# trackInlineStats

>[!IMPORTANT]
>
>此变量已停用。请参阅 [启用Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md) 而是。

ClickMap是Adobe Analytics中一项已停用的功能，用于收集有关访客点击位置及其点击内容的数据。 该功能已替换为 [Activity Map](/help/analyze/activity-map/activity-map.md).

启用此功能后，AppMeasurement 会收集有关链接的信息，并在下一个图像请求中发送该数据。每次点击的信息都存储在标记为 `s_sq`.

## 使用Adobe Analytics扩展启用ClickMap

[!UICONTROL 启用ClickMap] 是下的复选框 [!UICONTROL 链接跟踪] 配置Adobe Analytics扩展时的折叠面板。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
4. 展开 [!UICONTROL 链接跟踪] 折叠面板，这会显示 [!UICONTROL 启用ClickMap] 复选框。

>[!NOTE]
>
>此复选框与 [!UICONTROL 使用Activity Map] 复选框，位于 [!UICONTROL 库管理] 风琴折。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.trackInlineStats

此 `s.trackInlineStats` 是一个布尔值，用于启用或禁用ClickMap跟踪。 由于该功能已停用，因此Adobe不建议设置此变量。 其默认值为 `false`。

```js
s.trackInlineStats = false;
```
