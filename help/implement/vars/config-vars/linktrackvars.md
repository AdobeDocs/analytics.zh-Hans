---
title: linkTrackVars
description: 指定要包含在链接跟踪图像请求中的变量。
feature: Variables
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 62%

---

# linkTrackVars

某些实施不希望将所有变量包含在所有链接跟踪图像请求中。使用 `linkTrackVars` 和 [`linkTrackEvents`](linktrackevents.md) 变量可在 [`tl()`](../functions/tl-method.md) 调用中有选择地包含维度和量度。

页面查看调用（[`t()`](../functions/t-method.md) 方法）不使用此变量。

## 使用Web SDK确定要包含在XDM事件中的变量

Web SDK不排除链接跟踪调用的某些字段。 但是，您可以使用 `onBeforeEventSend` 在将数据发送到Adobe之前进行回调以清除或设置所需的字段。 请参阅 [全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) 有关更多信息，请参阅Web SDK文档。

## 使用Adobe Analytics扩展程序的链接跟踪调用中的变量

此变量会根据界面中设置的变量自动填充到后端，因此实施始终使用Adobe Analytics扩展来设置此变量。

>[!IMPORTANT]
>
>如果使用自定义代码编辑器设置变量，则必须将变量包含在 `linkTrackVars` 使用自定义代码。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.linkTrackVars

`s.linkTrackVars` 变量是一个字符串，其中包含以逗号分隔的变量列表，您要将这些事件包含在链接跟踪图像请求（`tl()` 方法）中。必须满足以下两个条件才能在链接跟踪点击中包含维度：

* 设置所需的变量值。例如：`s.eVar1 = "Example value";`。
* 在 `linkTrackVars` 变量中设置所需变量。例如：`s.linkTrackVars = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

此变量的默认值是空字符串。但是，Adobe 在代码管理器中提供了 AppMeasurement 代码，其中该变量被设置为 `"None"`。有效值是用于填充维度的任何页面级变量。

* 如果未定义此变量或将其设置为空字符串，则&#x200B;*所有* 变量都将包含在链接跟踪图像请求中。
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
