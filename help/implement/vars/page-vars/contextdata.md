---
title: contextData
description: 上下文数据变量允许您在处理规则可读取的每个页面上定义自定义变量。
feature: Variables
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
source-git-commit: 35e7c8bccb8524fa5e87cae223f0854956c7528a
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 80%

---

# contextData

上下文数据变量允许您在处理规则可读取的每个页面上定义自定义变量。您可以在上下文数据变量中发送数据，而不是显式地为代码中的 Analytics 变量分配值。然后，处理规则会接收上下文数据变量值并将其传递给相应的 Analytics 变量。请参阅《管理员用户指南》中的[处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)。

上下文数据变量有助于开发团队收集指定元素中的数据而不是编号变量。例如，您可以请求开发团队将页面的作者分配给 `s.contextData["author"]`，而不是请求他们将其分配给 `eVar10`。然后，贵组织中的 Analytics 管理员可以创建处理规则，以将上下文数据变量映射到用于报告的 Analytics 变量。开发团队最终只需关注上下文数据变量，而无需考虑 Adobe 提供的许多页面变量。

## 使用Web SDK的上下文数据变量

如果XDM字段不为 [已映射Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=zh-Hans)，则会自动将其作为上下文数据变量包含在内。 然后，您可以使用 [处理规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) 将上下文数据变量分配给所需的Analytics变量。

虽然将数据映射到数据流中正确的XDM字段是最佳做法，但这种方法获得了类似的结果。

## 使用Adobe Analytics扩展的上下文数据变量

Adobe Experience Platform数据收集没有用于设置上下文数据变量的专用位置。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展的自定义代码编辑器中的s.contextData

`s.contextData` 变量不会直接接收值。它会将此变量的属性设置为字符串。

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* 有效的上下文数据变量只包含字母数字字符、下划线和句点。如果您包括其他字符（如连字符），则 Adobe 无法对处理规则中的数据收集提供担保。
* 请勿将上下文数据变量以 `"a."` 开头。此前缀由 Adobe 保留和使用。例如，请勿使用 `s.contextData["a.InstallEvent"]`。
* 上下文数据变量不区分大小写。变量 `s.contextData["example"]` 和 `s.contextData["EXAMPLE"]` 是相同的。

## 使用处理规则填充 Analytics 变量

>[!WARNING]
>
>运行处理规则后，上下文数据变量将被丢弃。如果没有可将值置于变量的处于活动状态的处理规则，则该数据会永久丢失！

1. 更新您的实施以设置上下文数据变量名称和值。
2. 登录到 Adobe Analytics，然后转到“管理员”>“报表包”。
3. 选择所需的报表包，然后转到“编辑设置”>“常规”>“处理规则”。
4. 创建一个将 Analytics 变量设置为上下文数据变量值的处理规则。
5. 保存更改。

处理规则在保存后会立即生效。它们不适用于历史记录数据。

## 在链接跟踪调用中发送上下文数据

将上下文数据变量作为 `contextData` 的属性包含在 [`s.linkTrackVars`](../config-vars/linktrackvars.md) 中：

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## 使用上下文数据变量递增事件

创建处理规则时，可以将上下文数据变量分配给事件。

* 如果上下文数据变量包含任何类型的文本，则事件将递增 1。
* 如果上下文数据变量包含整数，则事件将按该整数量递增。

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
