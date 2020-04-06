---
description: 您要能够搜索的每个ID都会被分配一个命名空间，该ID是一个自定义字符串，用于在所有报表包中使用的任何变量中标识该ID。
title: 命名空间
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 命名空间

您要能够搜索的每个ID都会被分配一个命名空间，该ID是一个自定义字符串，用于在所有报表包中使用的任何变量中标识该ID。

命名空间字符串用于识别您在数据隐私请求中提供 ID 时要搜索的字段。在提交数据隐私请求后，该请求将包含一个 JSON 部分，以指定要用于该请求的数据主体 ID。多个ID可作为数据主体的单个请求的一部分包含在内。 JSON包括：

* 包含命名空间字符串的“命名空间”字段。
* 对于大多数Adobe Analytics请求，“类型”字段都包含值“analytics”。
* 一个“值”字段，其中包含Analytics应在每个报表包的关联命名空间变量中搜索的ID。

有关更多详细信息，请参阅 [Experience Cloud 数据隐私 API 文档](https://www.adobe.io/apis/experienceplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/technical_overview/privacy_service_overview/privacy_service_overview.md)。

## Cookie ID

旧版 Analytics 跟踪 Cookie，又称为 Adobe Analytics ID (AAID)：

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

该值必须指定为两个以短划线分隔的十六进制数字。 所有字母字符的十六进制数字都必须使用大写来指定。 十六进制值不应具有任何前导零（请注意与在已弃用表单中指定的相同值的差异，该表单中要求前导零）。

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

该值应指定为两个16位十六进制数字或两个19位十进制数字。 数字应以短划线、下划线或冒号分隔。 如果任一数字没有足够的位数，则需在开头补零。

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

>[!NOTE] Experience Cloud ID (ECID) 以前称为 Marketing Cloud ID (MCID)，在一些现有的文档中依然会采用这种旧称。
>
>这些 ID 是 Analytics 支持的唯一 ID，使用“type”值而不是“analytics”值。

若任何这些 Cookie ID 的值格式与规定的该 ID 格式不符，则数据隐私请求会失败，并出现“值格式不正确”的错误消息。

通常，您将会使用新的[隐私 JavaScript](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm) 收集这些 Cookie ID，该 JavaScript 将为这些 JSON ID 自动提供所有相关的密钥/值对。

除了上面所列的字段（“namespace”、“type”、“value”）以外，该 JavaScript 代码还会在 JSON 中填充其他密钥/值对，但是上面列出的字段对于 Analytics 数据隐私处理来说最为重要，而且在您以其他方式收集 ID 时，只需提供上述字段。

## 自定义访客 ID

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

命名空间也为自定义访客ID预定义。

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

对于自定义流量或转化变量（prop 或 eVar）中的 ID，您应当为变量设置 ID-DEVICE 或 ID-PERSON 标签，然后将您自己的命名空间名称分配给此类型的 ID。请参阅[为变量设置 ID-DEVICE 或 ID-PERSON 标签时提供命名空间。](gdpr-labels.md)

您还可以查看之前为其他变量或报表包定义的命名空间，并重复使用其中一个变量，以便同一命名空间可轻松用于存储该类型ID的所有报表包。 还可以为报表包中的多个变量分配相同的命名空间。 例如，一些客户将CRM ID存储在流量变量和转换变量中（取决于页面，它有时存储在一个或两个变量中），他们可以将命名空间“CRM ID”分配给这两个变量。

>[!TIP]在为数据隐私 API 指定命名空间时，请避免使用变量的友好名称（报表 UI 中显示的名称）或变量的编号（如 eVar12），除非该友好名称或变量编号也是您在应用 ID-DEVICE 或 ID-PERSON 标签时指定的命名空间。使用命名空间而不是友好名称可以使相同的用户标识块为多个报表包指定正确的变量：例如，当 ID 在某些报表包中位于不同的 eVar 中时，或者友好名称不匹配时（例如，友好名称已在特定的报表包中本地化）。

>[!CAUTION]命名空间“visitorId”和“customVisitorId”是保留名称，用于识别 Analytics 旧版跟踪 Cookie 和 Analytics 客户的访客 ID。请勿将这些命名空间用于自定义流量或转换变量。

有关更多信息，请参阅[为变量设置 ID-DEVICE 或 ID-PERSON 标签时提供命名空间。](/help/admin/c-data-governance/gdpr-labels.md)
