---
title: linkTrackVars
description: 指定要包含在链接跟踪图像请求中的变量。
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
TQID: https://experienceleague.adobe.com/B3So-VtGCz2klaFJT2a1zA3-AzSPaM9R-0jafXNsrVE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 344
ht-degree: 60%

---

# linkTrackVars

某些实施不希望将所有变量包含在所有链接跟踪图像请求中。 使用 `linkTrackVars` 和 [`linkTrackEvents`](linktrackevents.md) 变量可在 [`tl()`](../functions/tl-method.md) 调用中有选择地包含维度和量度。

页面查看调用（[`t()`](../functions/t-method.md) 方法）不使用此变量。

## 使用Web SDK确定要包含在XDM事件中的变量

Web SDK不排除链接跟踪调用的某些字段。 但是，您可以在将数据发送到Adobe之前使用`onBeforeEventSend`回调清除或设置所需字段。 有关详细信息，请参阅Web SDK文档中的[全局修改事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally)。

## 使用Adobe Analytics扩展程序的链接跟踪调用中的变量

此变量会根据界面中设置的变量自动填充到后端，因此实施始终使用Adobe Analytics扩展来设置此变量。

>[!IMPORTANT]
>
>如果使用自定义代码编辑器设置变量，则还必须使用自定义代码在`linkTrackVars`中包含这些变量。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.linkTrackVars

`s.linkTrackVars` 变量是一个字符串，其中包含以逗号分隔的变量列表，您要将这些事件包含在链接跟踪图像请求（`tl()` 方法）中。 必须满足以下两个条件才能在链接跟踪点击中包含维度：

* 设置所需的变量值。 例如，`s.eVar1 = "Example value";`。
* 在 `linkTrackVars` 变量中设置所需变量。 例如，`s.linkTrackVars = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

此变量的默认值是空字符串。 但是，Adobe 在代码管理器中提供了 AppMeasurement 代码，其中该变量被设置为 `"None"`。 有效值是用于填充维度的任何页面级变量。

* 如果未定义此变量或将其设置为空字符串，则&#x200B;*所有* 变量都将包含在链接跟踪图像请求中。
* 如果此变量被设置为 `"None"`,则链接跟踪图像请求中&#x200B;*不*&#x200B;包含任何变量。

>[!TIP]
>
>在此变量中指定变量时，请避免使用 Analytics 对象标识符 (`s.`)。 例如，`s.linkTrackVars = "eVar1";` 是正确的，而 `s.linkTrackVars = "s.eVar1";` 是错误的。

## 示例

以下链接跟踪函数在发送到 Adobe 的图像请求中仅包含 `eVar1`（不包含 `eVar2`）：

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
