---
title: (hier)
description: 在 Adobe Analytics 中实施层级变量。
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 62%

---

# (hier)

>[!IMPORTANT]
>
>此变量已停用，且在 Analysis Workspace 中不是可用维度。Adobe 建议改用 [eVar](evar.md) 和分类。

层级变量是自定义变量，可让您查看网站的结构。Adobe 最多为实施中的 5 个层级变量提供支持。

此变量适用于网站结构超过三层的网站。例如，媒体网站的“体育”部分可以有 4 个级别：`Sports`、`Local Sports`、`Baseball` 以及 `Team name`。如果有人访问“棒球”页面，则“体育”、“地方体育”和“棒球”这几个级别都会反映此访问。

在实施中使用层级之前，请确保在报表包设置中配置每个层级。

## 使用Web SDK的层级

层级为 [已映射Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM字段下 `_experience.analytics.customDimensions.hierarchies.hier1` to `_experience.analytics.customDimensions.hierarchies.hier5`.

## 使用Adobe Analytics扩展的层级

您可以在配置Analytics扩展时（全局变量）或根据规则设置层级。

1. 登录到 [Adobe Experience Platform数据收集](https://experience.adobe.com/data-collection) 使用您的Adobe ID凭据。
2. 单击所需的标记属性。
3. 转到[!UICONTROL 规则]选项卡，然后单击所需的规则（或创建规则）。
4. 在[!UICONTROL 操作]下，单击现有的 [!UICONTROL Adobe Analytics - 设置变量]操作或单击“+”图标。
5. 将[!UICONTROL 扩展]下拉列表设置为 Adobe Analytics，将[!UICONTROL 操作类型]设置为[!UICONTROL 设置变量]。
6. 找到 [!UICONTROL 层级] 中。

您可以将层次结构值设置为静态字符串或引用数据元素。 您还可以设置所需的分隔符。 确保此处设置的分隔符与报表包设置中设置的分隔符匹配。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.hier1 - s.hier5

每个层级都是一个字符串，其中包含特定于贵组织的自定义值。 这些值的最大长度为 255 字节；超过 255 字节的值在发送到 Adobe 时会自动被截断。

请确保您的所有区域名称中没有分隔符。例如，如果某个部分叫做 `Coach Griffin, Jim`，请选择使用逗号以外的分隔符。变量总限制为 255 字节。分隔符可以包含多个字符，例如 `||` 或 `/|\`，这些字符不太可能出现在变量值中。

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
