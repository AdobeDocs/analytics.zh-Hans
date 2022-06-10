---
title: 省/州
description: 在 Reports and Analytics 中填充“访客所在州报表”。
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 87%

---

# state

>[!IMPORTANT]
>
>此变量已停用，且在 Analysis Workspace 中不是可用维度。请改用“美国”维度，AppMeasurement 会根据访客的位置自动收集该维度。

在 Adobe Analytics 的早期版本中，访客在零售网站上填写送货信息时，会使用 `state` 变量。它的功能与 prop 相同，但在 Analysis Workspace 中不可用。

## 使用Adobe Analytics扩展的状态

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置州。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) 使用您的Adobe ID凭据。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 州]部分。

您可以将州设置为任何字符串值或数据元素。

## AppMeasurement和Analytics扩展的自定义代码编辑器中的s.state

`s.state` 变量是一个字符串，通常包含访客所在州或省份。完整的州名称或双字母代码均有效。其值的最大长度为 50 字节；超出此长度的值会被截断。其默认值是空字符串。

```js
s.state = "Utah";
```
