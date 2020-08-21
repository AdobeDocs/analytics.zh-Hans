---
title: linkTrackVars
description: 指定要包含在链接跟踪图像请求中的变量。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '271'
ht-degree: 100%

---


# linkTrackVars

某些实施不希望将所有变量包含在所有链接跟踪图像请求中。使用 `linkTrackVars` 和 [`linkTrackEvents`](linktrackevents.md) 变量可在 [`tl()`](../functions/tl-method.md) 调用中有选择地包含维度和量度。

页面查看调用（[`t()`](../functions/t-method.md) 方法）不使用此变量。

## 使用 Adobe Experience Platform Launch 的链接跟踪调用中的变量

Launch 会根据界面中设置的变量自动在后端填充此变量，因此实施始终使用 Launch 来设置此变量。

>[!IMPORTANT]
>
>如果使用自定义代码编辑器在 Launch 中设置事件，则还必须使用自定义代码在 `linkTrackVars` 中包含该变量。

## AppMeasurement 和 Launch 自定义代码编辑器中的 s.linkTrackVars

`s.linkTrackVars` 变量是一个字符串，其中包含以逗号分隔的变量列表，您要将这些事件包含在链接跟踪图像请求（`tl()` 方法）中。必须满足以下两个条件才能在链接跟踪点击中包含维度：

* 设置所需的变量值。例如：`s.eVar1 = "Example value";`。
* 在 `linkTrackVars` 变量中设置所需变量。例如：`s.linkTrackVars = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

此变量的默认值是空字符串。但是，Adobe 在代码管理器中提供了 AppMeasurement 代码，其中该变量被设置为 `"None"`。有效值是用于填充维度的任何页面级变量。

* 如果未定义此变量或将其设置为空字符串，则&#x200B;*所有*&#x200B;变量都将包含在链接跟踪图像请求中。
* 如果此变量被设置为 `"None"`,则链接跟踪图像请求中&#x200B;*不*&#x200B;包含任何变量。

>[!TIP]
>
>在此变量中指定变量时，请避免使用 Analytics 对象标识符 (`s.`)。例如，`s.linkTrackVars = "eVar1";` 是正确的，而 `s.linkTrackVars = "s.eVar1";` 是错误的。

## 示例

以下链接跟踪函数在发送到 Adobe 的图像请求中仅包含 `eVar1`（不包含 `eVar2`）：

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
