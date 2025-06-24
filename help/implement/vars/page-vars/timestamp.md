---
title: timestamp
description: 手动设置点击的时间戳。
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 81%

---

# timestamp

`timestamp` 变量可手动为启用了时间戳的报表包设置点击的时间戳。

>[!WARNING]
>
>如果您的报表包未明确配置为接受带有时间戳的点击，请勿使用此变量。AppMeasurement 会为不支持带有时间戳的点击的报表包自动设置点击时间。如果使用此变量将点击发送到不支持时间戳的报表包，则该数据将永久丢失。

## 使用Web SDK的时间戳

在XDM字段`xdm.timestamp`下，为Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/xdm-var-mapping.html)映射时间戳[。 此字段仅支持Unix时间。

## 使用Adobe Analytics扩展的时间戳

Adobe Analytics 扩展程序中没有专门的字段来使用此变量。 按照 AppMeasurement 语法使用自定义代码编辑器。

## AppMeasurement和Analytics扩展自定义代码编辑器中的s.timestamp

`s.timestamp` 变量是一个包含点击日期和时间的字符串。有效的时间戳格式包括[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)和[Unix时间](https://en.wikipedia.org/wiki/Unix_time)（秒）。

```js
// Timestamp using ISO 8601
s.timestamp = "2024-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## ISO 8601 值

以 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 表示的日期和时间可以采用几种不同的形式。Adobe 并不支持 ISO 8601 中的所有功能。

* 必须提供日期和时间，中间由 `T` 隔开。
* 需要提供小时和分钟；秒是可选的，但建议提供。
* 不支持周日期和序数日期。
* 日期可以采用标准格式或扩展格式。例如，`2024-01-01T00:00:00Z` 和 `20240101T000000Z` 均有效。
* 从技术上讲，小数分钟数和秒数是有效的，但 Adobe 会忽略小数。
* 采用标准格式和扩展格式的时区均受支持。

以下是 `timestamp` 变量中的有效 ISO 8601 示例值：

```text
2024-01-01T00:00:00+00:00
2024-01-01T00:00:00Z
2024-01-01T00:00:00
2024-01-01T00:00
20240101T000000+0000
20240101T000000Z
20240101T000000
20240101T0000
```
