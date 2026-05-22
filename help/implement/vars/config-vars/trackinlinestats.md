---
title: trackInlineStats
description: （已停用）在您的实施中启用或禁用ClickMap 。
keywords: 禁用clickmap
feature: Appmeasurement Implementation
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/UoeOR4qNKfuectzZJVKJ2gCNhSxMSBOggMEj9Z9v08g'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 29%

---

# trackInlineStats

>[!IMPORTANT]
>
>此变量已停用，不再使用。

ClickMap是Adobe Analytics中一项已弃用的功能，用于收集有关访客点击位置及其点击内容的数据。 此功能已替换为[Activity Map](/help/analyze/activity-map/overview.md)。

启用此功能后，AppMeasurement 会收集有关链接的信息，并在下一个图像请求中发送该数据。 每次点击的信息存储在标记为`s_sq`的Cookie中。

## 使用Adobe Analytics扩展启用ClickMap

在配置ClickMap扩展时，[!UICONTROL 启用Adobe Analytics]是[!UICONTROL 链接跟踪]折叠面板下的复选框。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 扩展]选项卡，然后单击 Adobe Analytics 下的&#x200B;**配置**&#x200B;按钮。
4. 展开[!UICONTROL 链接跟踪]折叠面板，这会显示[!UICONTROL 启用ClickMap]复选框。

>[!NOTE]
>
>此复选框与[!UICONTROL 使用Activity Map]复选框不同，该复选框位于[!UICONTROL 库管理]折叠面板下。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.trackInlineStats

`s.trackInlineStats`是一个布尔值，用于启用或禁用ClickMap跟踪。 由于该功能已停用，因此Adobe不建议设置此变量。 其默认值为 `false`。

```js
s.trackInlineStats = false;
```
