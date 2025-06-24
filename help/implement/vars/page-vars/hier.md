---
title: hier
description: （已停用）在Adobe Analytics中实施层级变量。
feature: Appmeasurement Implementation
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 93%

---

# hier

>[!IMPORTANT]
>
>此变量已停用，且在 Analysis Workspace 中不是可用维度。Adobe 建议改用 [eVar](evar.md) 和分类。

层级变量是自定义变量，可让您查看网站的结构。Adobe 最多为实施中的 5 个层级变量提供支持。

此变量适用于网站结构超过三层的网站。例如，媒体网站的“体育”部分可以有 4 个级别：`Sports`、`Local Sports`、`Baseball` 以及 `Team name`。如果有人访问“棒球”页面，则“体育”、“地方体育”和“棒球”这几个级别都会反映此访问。

在实施中使用层级之前，请确保先在报告包设置中配置每个层级。

## 使用 Web SDK 的层级

在 XDM 字段 `xdm._experience.analytics.customDimensions.hierarchies.hier1` 至 `xdm._experience.analytics.customDimensions.hierarchies.hier5` 中，[为 Adobe Analytics 映射](/help/implement/aep-edge/xdm-var-mapping.md) 层级。

## 使用 Adobe Analytics 扩展的层级

您可以在配置 Analytics 扩展程序时（全局变量）或根据规则设置层级。

1. 使用您的 Adobe ID 凭据登录 [Adobe Experience Platform 数据收集](https://experience.adobe.com/data-collection)。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到[!UICONTROL 层级]分区。

您可以将层次结构值设置为静态字符串或引用数据元素。 您还可以设置所需的分隔符。 请确保您在此处设置的分隔符与报告包设置中设置的分隔符匹配。

## AppMeasurement 和 Analytics 扩展代码编辑器中的 s.hier1 – s.hier5

每个层级都是一个字符串，其中包含特定于贵组织的自定义值。 这些值的最大长度为 255 字节；超过 255 字节的值在发送到 Adobe 时会自动被截断。

请确保您的所有区域名称中没有分隔符。例如，如果某个部分叫做 `Coach Griffin, Jim`，请选择使用逗号以外的分隔符。变量总限制为 255 字节。分隔符可以包含多个字符，例如 `||` 或 `/|\`，这些字符不太可能出现在变量值中。

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
