---
title: trackInlineStats
description: （已停用）在您的实施中启用或禁用ClickMap 。
keywords: 禁用clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 28%

---

# trackInlineStats

>[!IMPORTANT]
>
>此变量已停用，不再使用。

ClickMap是Adobe Analytics中一项已弃用的功能，用于收集有关访客点击位置及其点击内容的数据。 此功能已替换为[Activity Map](/help/analyze/activity-map/overview.md)。

启用此功能后，AppMeasurement 会收集有关链接的信息，并在下一个图像请求中发送该数据。每次点击的信息存储在标记为`s_sq`的Cookie中。

## 使用Adobe Analytics扩展启用ClickMap

在配置ClickMap扩展时，[!UICONTROL 启用Adobe Analytics]是[!UICONTROL 链接跟踪]折叠面板下的复选框。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**[!UICONTROL 配置]**&#x200B;按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 启用ClickMap]复选框。

>[!NOTE]
>
>此复选框与[!UICONTROL 使用Activity Map]复选框不同，该复选框位于[!UICONTROL 库管理]折叠面板下。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.trackInlineStats

`s.trackInlineStats`是一个布尔值，用于启用或禁用ClickMap跟踪。 由于该功能已停用，因此Adobe不建议设置此变量。 其默认值为 `false`。

```js
s.trackInlineStats = false;
```
