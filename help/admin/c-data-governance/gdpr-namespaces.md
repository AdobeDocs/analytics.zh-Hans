---
description: 您希望能够搜索的每个 ID 均分配有一个命名空间；命名空间是一个自定义字符串，用于在所有报表包之间使用的任何变量中识别该 ID。
seo-description: 您希望能够搜索的每个 ID 均分配有一个命名空间；命名空间是一个自定义字符串，用于在所有报表包之间使用的任何变量中识别该 ID。
seo-title: 命名空间
title: 命名空间
uuid: cab61844-3209-4980-b14 c-6859de777606
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 命名空间

您希望能够搜索的每个 ID 均分配有一个命名空间；命名空间是一个自定义字符串，用于在所有报表包之间使用的任何变量中识别该 ID。

命名空间字符串用于识别您在 GDPR 请求中提供 ID 时要搜索的字段。在提交 GDPR 请求后，该请求将包含一个 JSON 部分，以指定要用于该请求的数据主体 ID。一位数据主体的一个请求中，可以包含多个 ID。JSON 包括：

* “namespace”字段，其中包含命名空间字符串。
* “type”字段，它在大部分 Adobe Analytics 请求中包含值“analytics”。
* “value”字段，其中包含 Analytics 应在每个报表包的关联命名空间变量中搜索的 ID。

请参考 [Experience Cloud GDPR API 文档](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)，以了解更多详细信息。

<!-- Meike, I converted this table to headings and text to fix a validation error. -Bob -->

## Cookie ID

旧版 Analytics 跟踪 Cookie，又称为 Adobe Analytics ID (AAID)：

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

该值必须指定为两个十六进制数字，并使用短横线进行分隔。十六进制数中的所有字母字符都必须指定为使用大写字母。十六进制值不得以零开头（请注意，这与弃用版本中指定相同值的要求不同，弃用版本中要求该值以零开头）。

It is also acceptable to use `“namespaceId”: 10` instead of or in addition to `“namespace”: “AAID”` and you may see some other Adobe products use that form.

## 旧版 Analytics 跟踪 Cookie：弃用版本

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

弃用版本：

该值应指定为两个 16 位十六进制数或两个 19 位十进制数。数字之间应使用短横线、下划线或冒号进行分隔。如果任一数字没有足够的位数，则需在开头补零。

## 标识服务Cookie

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

该值必须指定为一个 38 位十进制数。如果您从一个数据源或一个数据仓库报告中提取这两个misdd\_ high/low或post\_ msload\_ high/low列，您必须将这两个数字中的每一个都设为19位数字，然后将它们与高值连接在一起。

It is also acceptable to use: `“namespaceId”: 4` instead of or in addition to `“namespace”: “ECID”` and you may see some other Adobe products use that form.

>[!NOTE]
>
>Experience Cloud ID(ECID)以前称为Marketing Cloud ID(MCID)，在某些现有文档中仍被该名称引用。
>
>这些ID是Analytics支持的唯一ID，它使用“analytics”以外的“类型”值。

若任何这些 Cookie ID 的值格式与规定的该 ID 格式不符，则 GDPR 请求会失败，并出现“值格式不正确”的错误消息。

通常，您将会使用新的[隐私 JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm) 收集这些 Cookie ID，该 JavaScript 将为这些 JSON ID 自动提供所有相关的密钥/值对。

除了上面所列的字段（“namespace”、“type”、“value”）以外，该 JavaScript 代码还会在 JSON 中填充其他密钥/值对，但是上面列出的字段对于 Analytics GDPR 处理来说最为重要，而且在您以其他方式收集 ID 时，只需提供上述字段。

## 自定义访客 ID

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

还会为自定义访客 ID 预定义命名空间。

## 自定义变量中的 ID

```
{
    namespace: "Email Address",
    type: "analytics", 
    value: "john@xyz.com" }, 
{
    namespace: "CRM ID", 
    type: "analytics", 
    value: "123456-ABCD" 
}
```

对于自定义流量或转化变量（prop 或 eVar）中的 ID，您应当为变量设置 ID-DEVICE 或 ID-PERSON 标签，然后将您自己的命名空间名称分配给此类型的 ID。请参阅[为变量设置 ID-DEVICE 或 ID-PERSON 标签时提供命名空间](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)。

您还可以查看之前为其他变量或报表包定义的命名空间并重复使用其中之一，以便轻松地将相同的命名空间用于存储此类型 ID 的所有报表包。另外，还可以将相同的命名空间分配给一个报表包内的多个变量。例如，某些客户将 CRM ID 存储在流量变量和转化变量中（根据页面，有时存储在其中任一变量中，有时同时存储在这两个变量中），并且他们可以将命名空间“CRM ID”同时分配给这两个变量。

>[!NOTE]
>
>在将命名空间指定给GDPR API时，您不能使用变量的友好名称(在报表UI中显示的名称)或变量的编号(如eVar12)，除非这也是将ID-设备或ID-PEN标签应用于此变量时指定的命名空间。在这些情况下，使用命名空间而不是友好名称可以允许相同的用户标识块为多个报表包指定正确的变量：

* 某些报表包中的 ID 位于不同的 eVars 中，或者
* 友好名称不匹配（例如，友好名称为了适应特定的报表包而进行了本地化）

更多信息，请参阅[为变量设置 ID-DEVICE或 ID-PERSON 标签时提供命名空间](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)。
