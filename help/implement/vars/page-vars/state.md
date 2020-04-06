---
title: 省/州
description: 在 Reports and Analytics 中填充“访客所在州报表”。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# state

>[!IMPORTANT] 此变量已停用，且在 Analysis Workspace 中不是可用维度。请改用“美国”维度，AppMeasurement 会根据访客的位置自动收集该维度。

在 Adobe Analytics 的早期版本中，访客在零售网站上填写送货信息时，会使用 `state` 变量。它的功能与 prop 相同，但在 Analysis Workspace 中不可用。

## Adobe Experience Platform Launch 中的州

您可以在配置 Analytics 扩展时（全局变量）或根据规则设置州。

1. 使用您的 Adobe ID 凭据登录 [launch.adobe.com](https://launch.adobe.com)。
2. 单击所需的属性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在下 [!UICONTROL Actions]面，单击现有 [!UICONTROL Adobe Analytics - Set Variables] 操作或单击“+”图标。
5. 将下拉 [!UICONTROL Extension] 列表设置为Adobe Analytics，将其设置为 [!UICONTROL Action Type] to [!UICONTROL Set Variables]。
6. 找到该 [!UICONTROL State] 部分。

您可以将州设置为任何字符串值或数据元素。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.state

`s.state` 变量是一个字符串，通常包含访客所在州或省份。完整的州名称或双字母代码均有效。其值的最大长度为 50 字节；超出此长度的值会被截断。其默认值是空字符串。

```js
s.state = "Utah";
```
