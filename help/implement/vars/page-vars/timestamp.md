---
title: timestamp
description: 手动设置点击的时间戳。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# timestamp

变量 `timestamp` 手动设置启用时间戳的报表包的点击时间戳。

> [!WARNING] 如果您的报表包未明确配置为接受时间戳的点击，请勿使用此变量。 AppMeasurement会为不支持加盖时间戳的点击的报表包自动设置点击时间。 如果将包含此变量的点击发送到不支持时间戳的报表包，则该数据将永久丢失。

## Adobe Experience Platform Launch中的时间戳

Launch中没有专用字段可使用此变量。 按照AppMeasurement语法使用自定义代码编辑器。

## AppMeasurement和Launch自定义代码编辑器中的s.timestamp

变 `s.timestamp` 量是包含点击日期和时间的字符串。 有效的时间戳格式 [包括ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 和 [Unix时间](https://en.wikipedia.org/wiki/Unix_time)。

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## ISO 8601值

在 [ISO 8601中表示的日期和时间](https://en.wikipedia.org/wiki/ISO_8601) ，可以采用几种不同的形式。 Adobe不支持ISO 8601中的所有功能。

* Both the date and time must be provided, separated by `T`.
* 需要数小时和数分钟；秒是可选的，但建议使用。
* 不支持周日期和序数日期。
* 日期可以采用标准或扩展格式。 例如， `2020-01-01T00:00:00Z` 和 `20200101T000000Z` 均有效。
* 分数分钟数和秒数在技术上是有效的，但Adobe会忽略分数。
* 标准和扩展格式支持时区。

以下是变量中的有效ISO 8601值示 `timestamp` 例：

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```
