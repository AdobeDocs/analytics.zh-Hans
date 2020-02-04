---
title: contextData
description: 上下文数据变量允许您在处理规则可读取的每个页面上定义自定义变量。
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# contextData

上下文数据变量允许您在处理规则可读取的每个页面上定义自定义变量。 您可以在上下文数据变量中发送数据，而不是在代码中显式地为Analytics变量赋值。 然后，处理规则将上下文数据变量值传递给相应的Analytics变量。 See [Processing rules](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) in the Admin user guide.

上下文数据变量有助于开发团队收集指定元素中的数据而不是编号变量。 例如，您可以请求开发团队将页面的作者分配给页面，而 `eVar10`不是请求开发团队将页面的作者分配给 `s.contextData["author"]` 它。 然后，组织中的Analytics管理员可以创建处理规则，将上下文数据变量映射到分析变量中以进行报告。 开发团队最终只会担心上下文数据变量，而不是Adobe提供的许多页面变量。

## Adobe Experience Platform Launch中的上下文数据变量

启动项没有用于设置上下文数据变量的专用位置。 按照AppMeasurement语法使用自定义代码编辑器。

## s.contextAppMeasurement中的数据和启动自定义代码编辑器

该 `s.contextData` 变量不直接取值。 而是将此变量的属性设置为字符串。

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* 有效的上下文数据变量只包含字母数字字符、下划线和句点。 如果您包括其他字符（如连字符），则Adobe不保证在处理规则中收集数据。
* 请勿使用上下文数据变量启动 `"a."`。 此前缀由Adobe保留和使用。 例如，请勿使用 `s.contextData["a.InstallEvent"]`。
* 上下文数据变量不区分大小写。 变量 `s.contextData["example"]` 和 `s.contextData["EXAMPLE"]` 相同。

## 使用处理规则填充分析变量

> [!IMPORTANT] 运行处理规则后，上下文数据变量将被丢弃。 如果没有将值放入变量的活动处理规则，则该数据会永久丢失！

1. 更新您的实施以设置上下文数据变量名称和值。
2. 登录到Adobe Analytics，然后转到“管理员”>“报表包”。
3. 选择所需的报表包，然后转到编辑设置>常规>处理规则。
4. 创建一个将Analytics变量设置为上下文数据变量值的处理规则。
5. 保存更改。

处理规则在保存后立即生效。 它们不适用于历史数据。

## 在链接跟踪调用中发送上下文数据

将上下文数据变量作为以下项的属 `contextData` 性包含 `s.linkTrackVars`:

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
