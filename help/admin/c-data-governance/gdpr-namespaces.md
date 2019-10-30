---
description: 您希望能够搜索的每个 ID 均分配有一个命名空间；命名空间是一个自定义字符串，用于在所有报表包之间使用的任何变量中识别该 ID。
seo-description: 您希望能够搜索的每个 ID 均分配有一个命名空间；命名空间是一个自定义字符串，用于在所有报表包之间使用的任何变量中识别该 ID。
seo-title: 命名空间
title: 命名空间
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 命名空间

您希望能够搜索的每个 ID 均分配有一个命名空间；命名空间是一个自定义字符串，用于在所有报表包之间使用的任何变量中识别该 ID。

命名空间字符串用于标识您在提供作为数据隐私请求一部分的ID时要搜索的字段。 提交数据隐私请求时，该请求将包括一个JSON部分，它指定要用于请求的数据主体ID。 一位数据主体的一个请求中，可以包含多个 ID。JSON 包括：

* “namespace”字段，其中包含命名空间字符串。
* “type”字段，它在大部分 Adobe Analytics 请求中包含值“analytics”。
* “value”字段，其中包含 Analytics 应在每个报表包的关联命名空间变量中搜索的 ID。

Refer to the [Experience Cloud Data Privacy API documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) for more details.

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

此外，也可以转而使用 `"namespaceId": 10` 作为 `"namespace": "AAID"` 的代替或补充，您可能会看到其他一些 Adobe 产品使用该表单。

## 旧版 Analytics 跟踪 Cookie：弃用版本

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

弃用版本：

该值应指定为两个 16 位十六进制数或两个 19 位十进制数。数字之间应使用短横线、下划线或冒号进行分隔。如果其中一个数字没有足够的数字，则应添加前导零。

## Identity 服务 Cookie

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

该值必须指定为一个 38 位十进制数。如果您要从数据馈送或 Data Warehouse 报表的 mcvisid\_high/low 或 post\_msvisid\_high/low 两列中提取该数字，则必须将这两个数字都补零为 19 位，然后先将它们与高值连接起来。

此外，也可以转而使用 `"namespaceId": 4` 作为 `"namespace": "ECID"` 的代替或补充，您可能会看到其他一些 Adobe 产品使用该表单。

> [!NOTE]Experience Cloud ID (ECID) 以前称为 Marketing Cloud ID (MCID)，在一些现有的文档中依然会采用这种旧称。
>
>这些 ID 是 Analytics 支持的唯一 ID，使用“type”值而不是“analytics”值。

如果这些Cookie ID中任何一个的值部分的格式不遵循该ID描述的格式，则数据隐私请求将失败，并出现“值格式不正确”错误。

通常，您将会使用新的[隐私 JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm) 收集这些 Cookie ID，该 JavaScript 将为这些 JSON ID 自动提供所有相关的密钥/值对。

此JavaScript代码除了上面列出的键／值对(namespace、type、value)之外，还使用其他键／值对填充JSON，但上面列出的字段对于Analytics数据隐私处理最重要，并且在以其他方式收集ID时，您只需提供这些字段。

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

对于自定义流量或转化变量（prop 或 eVar）中的 ID，您应当为变量设置 ID-DEVICE 或 ID-PERSON 标签，然后将您自己的命名空间名称分配给此类型的 ID。See [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON.](gdpr-labels.md)

您还可以查看之前为其他变量或报表包定义的命名空间并重复使用其中之一，以便轻松地将相同的命名空间用于存储此类型 ID 的所有报表包。另外，还可以将相同的命名空间分配给一个报表包内的多个变量。例如，某些客户将 CRM ID 存储在流量变量和转化变量中（根据页面，有时存储在其中任一变量中，有时同时存储在这两个变量中），并且他们可以将命名空间“CRM ID”同时分配给这两个变量。

> [!TIP] 在为数据隐私API指定命名空间时，请避免使用变量的易记名称（报表UI中显示的名称）或变量的编号（如eVar12），除非它是在应用ID-DEVICE或ID-PERSON标签时指定的命名空间。 使用命名空间而不是友好名称可以使相同的用户标识块为多个报表包指定正确的变量：例如，如果某些报表包中的ID在不同的eVar中，或者友好名称不匹配（例如，当友好名称已针对特定报表包进行本地化时）。

> [!CAUTION]命名空间“visitorId”和“customVisitorId”是保留名称，用于识别 Analytics 旧版跟踪 Cookie 和 Analytics 客户的访客 ID。请勿将这些名称空间用于自定义流量或转换变量。

For more information, see [Provide a Namespace when Labeling a Variable as ID-DEVICE or ID-PERSON.](/help/admin/c-data-governance/gdpr-labels.md)
