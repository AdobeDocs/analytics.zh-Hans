---
title: 州
description: （已停用）填充了不再可用的“访客所在州报表”。
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 80%

---

# 州

>[!IMPORTANT]
>
>此变量已停用，且在 Analysis Workspace 中不是可用维度。使用 [美国各州](/help/components/dimensions/us-states.md) 维度中列出的维度，AppMeasurement会根据访客的位置自动收集该维度。

在 Adobe Analytics 的早期版本中，访客在零售网站上填写送货信息时，会使用 `state` 变量。它的功能与 prop 相同，但在 Analysis Workspace 中不可用。

## 使用 Adobe Analytics 扩展程序的州

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置州。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 设置 [!UICONTROL 扩展名] Adobe Analytics的下拉列表，以及 [!UICONTROL 操作类型] 到 [!UICONTROL 设置变量].
6. 找到[!UICONTROL 州]部分。

您可以将州设置为任何字符串值或数据元素。

## AppMeasurement 和 Analytics 扩展自定义代码编辑器中的 s.state

`s.state` 变量是一个字符串，通常包含访客所在州或省份。完整的州名称或双字母代码均有效。其值的最大长度为 50 字节；超出此长度的值会被截断。其默认值是空字符串。

```js
s.state = "Utah";
```
