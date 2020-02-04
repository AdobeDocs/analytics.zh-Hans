---
title: linkURL
description: 覆盖AppMeasurement在链接跟踪调用中使用的自动生成的链接URL。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkURL

每当向Adobe发送链接跟踪调用时，数据收集服务器都会自动检测URL。 使用该 `linkURL` 变量可覆盖检测到的URL。

## Adobe Experience Platform Launch中的链接URL

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和Launch自定义代码编辑器中的s.linkURL

变 `s.linkURL` 量是一个字符串，包含单击链接时浏览器的URL。 此变量不填充报表中可用的任何维。

```js
s.linkURL = "https://example.com";
```

如果未 `linkName` 为链接跟踪调用设置变量，则会改 `linkURL` 用该变量。
