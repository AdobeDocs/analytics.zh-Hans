---
title: 省/州
description: 在“报告和分析”中填充“访客状态报告”。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# state

> [!IMPORTANT] 此变量已停用，但在Analysis Workspace中不是可用维。 请改用“美国州”维度，AppMeasurement会根据访客的位置自动收集该维度。

在Adobe Analytics的早期版本中，访客在 `state` 零售网站上填写送货信息时，会使用该变量。 它的功能与prop相同，但在Analysis Workspace中不可用。

## Adobe Experience Platform Launch中的状态

您可以在配置Analytics扩展时（全局变量）或根据规则设置状态。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 单击所需的属性。
3. 转到“规 [!UICONTROL 则] ”选项卡，然后单击所需的规则（或创建规则）。
4. 在“ [!UICONTROL 操作]”下，单击现有  Adobe Analytics —— 设置变量操作或单击“+”图标。
5. 将“扩 [!UICONTROL 展] ”下拉列表设置为Adobe Analytics，将“操作类 [!UICONTROL 型] ”设置为“ [!UICONTROL 设置变量”]。
6. 找到“状 [!UICONTROL 态] ”部分。

您可以将状态设置为任何字符串值或数据元素。

## AppMeasurement中的s.state和启动自定义代码编辑器

变 `s.state` 量是一个字符串，通常包含访客的状态或省份。 全状态名称或双字母代码均有效。 最大值为50字节；长值被截断。 其默认值是空字符串。

```js
s.state = "Utah";
```
