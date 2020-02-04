---
title: linkTrackVars
description: 指定要包含在链接跟踪图像请求中的变量。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackVars

某些实现不希望将所有变量包含在所有链接跟踪图像请求中。 使用和 `linkTrackVars` 变量 `linkTrackEvents` 在调用中有选择地包含维度和 `tl()` 度量。

此变量不用于页面查看调用(函`t()` 数)。

## 使用Adobe Experience Platform Launch进行链接跟踪调用中的变量

Launch会根据在界面中设置的变量在后端自动填充此变量，因此始终在使用Launch的实现中设置它。

> [!IMPORTANT] 如果使用自定义代码编辑器在启动项中设置变量，则还必须在使用自定义代码 `linkTrackVars` 时包含该变量。

## AppMeasurement中的s.linkTrackVars和启动自定义代码编辑器

变 `s.linkTrackVars` 量是一个字符串，其中包含要包含在链接跟踪图像请求（函数）中的以逗号分隔的变量`tl()` 列表。 必须满足以下两个条件才能在链接跟踪点击中包含维：

* 设置所需的变量值。 例如：`s.eVar1 = "Example value";`。
* 在变量中设置所需的 `linkTrackVars` 变量。 例如：`s.linkTrackEvents = "eVar1";`。

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

此变量的默认值是空字符串。 但是，Adobe在代码管理器中提供了AppMeasurement代码，该变量设置为 `"None"`。 有效值是填充维的任何页面级变量。

* 如果未定义此变量或将其设置为空字符串，则所 *有变量* 都将包含在链接跟踪图像请求中。
* 如果此变量设置为 `"None"`, *则链接跟踪图像请求中* 不包含任何变量。

> [!TIP] 在此变量中指定变量时，请`s.`避免使用Analytics对象标识符()。 例如， `s.linkTrackVars = "eVar1";` 正确，而错误 `s.linkTrackVars = "s.eVar1";` 则正确。

## 示例

以下链接跟踪功能仅包 `eVar1` 括( `eVar2`非)发送到Adobe的图像请求：

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
