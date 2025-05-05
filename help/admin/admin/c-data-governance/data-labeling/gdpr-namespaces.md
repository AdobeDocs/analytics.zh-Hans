---
description: 您希望能够搜索的每个 ID 均分配有一个命名空间；命名空间是一个自定义字符串，用于在所有报告包之间使用的任何变量中识别该 ID。
title: 命名空间
feature: Data Governance
role: Admin
exl-id: 421572c2-2789-48bc-b530-d48216799724
source-git-commit: 79f650a7168e0cc44194445f3164a3f981e39a91
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 94%

---

# 命名空间

您希望能够搜索的每个 ID 均分配有一个命名空间；命名空间是一个自定义字符串，用于在所有报告包之间使用的任何变量中识别该 ID。

命名空间字符串用于识别您在数据隐私请求中提供 ID 时要搜索的字段。在提交数据隐私请求后，该请求将包含一个 JSON 部分，以指定要用于该请求的数据主体 ID。一位数据主体的一个请求中，可以包含多个 ID。JSON 包括：

* “namespace”字段，其中包含命名空间字符串。
* “type”字段，它在大部分 Adobe Analytics 请求中包含值“analytics”。
* “value”字段，其中包含 Analytics 应在每个报告包的关联命名空间变量中搜索的 ID。

有关更多详细信息和[标准身份命名空间列表](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/privacy/api/appendix#standard-namespaces)，请参阅[Experience Cloud数据隐私API文档](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hans)。 请参阅为示例请求创建访问/删除作业[&#128279;](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/privacy/api/privacy-jobs#access-delete)。

## Cookie ID

旧版 Analytics 跟踪 Cookie，又称为 Adobe Analytics ID (AAID)：

```json
{
   "namespace": "AAID",
   "type": "standard",
   "value": "2CCEEAE88503384F-1188000089CA"
}
```

该值必须指定为两个十六进制数字，并使用短横线进行分隔。十六进制数中的所有字母字符都必须指定为使用大写字母。十六进制值不得以零开头（请注意，这与弃用版本中指定相同值的要求不同，弃用版本中要求该值以零开头）。

此外，也可以转而使用 `"namespaceId": 10` 作为 `"namespace": "AAID"` 的代替或补充，您可能会看到其他一些 Adobe 产品使用该表单。

## 旧版 Analytics 跟踪 Cookie：弃用形式

```json
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

该值应指定为两个 16 位十六进制数或两个 19 位十进制数。数字之间应使用短横线、下划线或冒号进行分隔。如果任一数字没有足够的位数，则需在开头补零。

## 身份识别服务 Cookie

```json
{
   "namespace": "ECID",
   "type": "standard",
   "value": "00497781304058976192356650736267671594"
}
```

该值必须指定为一个 38 位十进制数。如果您要从数据馈送或 Data Warehouse 报告的 mcvisid\_high/low 或 post\_msvisid\_high/low 两列中提取该数字，则必须将这两个数字都补零为 19 位，然后先将它们与高值连接起来。

此外，也可以转而使用 `"namespaceId": 4` 作为 `"namespace": "ECID"` 的代替或补充，您可能会看到其他一些 Adobe 产品使用该表单。

>[!NOTE]
>
>Experience Cloud ID (ECID) 以前称为 Marketing Cloud ID (MCID)，在一些现有的文档中依然会采用这种旧称。
>
>这些 ID 是 Analytics 支持的唯一 ID，使用“type”值而不是“analytics”值。

若任何这些 Cookie ID 的值格式与规定的该 ID 格式不符，则数据隐私请求会失败，并出现“值格式不正确”的错误消息。

通常，您将会使用新的[隐私 JavaScript](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 收集这些 Cookie ID，该 JavaScript 将为这些 JSON ID 自动提供所有相关的密钥/值对。

除了上面所列的字段（“namespace”、“type”、“value”）以外，该 JavaScript 代码还会在 JSON 中填充其他密钥/值对，但是上面列出的字段对于 Analytics 数据隐私处理来说最为重要，而且在您以其他方式收集 ID 时，只需提供上述字段。

## 自定义访客 ID

```json
{
    "namespace": "customVisitorID",
    "type": "analytics",
    "value": "<ID>"
}
```

还会为自定义访客 ID 预定义命名空间。

## 自定义变量中的 ID

```json
{
"namespace":"Email Address",
"type": "analytics", 
"value": "john@xyz.com" 
}, 
{
    "namespace": "CRM ID", 
    "type": "analytics",
    "value": "123456-ABCD" 
}
```

对于自定义流量或转化变量（prop 或 eVar）中的 ID，您应当为变量设置 ID-DEVICE 或 ID-PERSON 标签，然后将您自己的命名空间名称分配给此类型的 ID。请参阅[为变量设置 ID-DEVICE 或 ID-PERSON 标签时提供命名空间。](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md)

您还可以查看之前为其他变量或报告包定义的命名空间并重复使用其中之一，以便轻松地将相同的命名空间用于存储此类型 ID 的所有报告包。另外，还可以将相同的命名空间分配给一个报告包内的多个变量。例如，某些客户将 CRM ID 存储在流量变量和转化变量中（根据页面，有时存储在其中任一变量中，有时同时存储在这两个变量中），并且他们可以将命名空间“CRM ID”同时分配给这两个变量。

>[!TIP]
>
>在为数据隐私 API 指定命名空间时，请避免使用变量的友好名称（报告 UI 中显示的名称）或变量的编号（如 eVar12），除非该友好名称或变量编号也是您在应用 ID-DEVICE 或 ID-PERSON 标签时指定的命名空间。使用命名空间而不是友好名称可以使相同的用户标识块为多个报告包指定正确的变量：例如，当 ID 在某些报告包中位于不同的 eVar 中时，或者友好名称不匹配时（例如，友好名称已在特定的报告包中本地化）。

>[!CAUTION]
>
>命名空间`visitorId`和`customVisitorId`是保留名称，用于识别Analytics旧版跟踪Cookie和Analytics客户的访客ID。 请勿将这些命名空间用于自定义流量或转换变量。

有关更多信息，请参阅[为变量设置 ID-DEVICE 或 ID-PERSON 标签时提供命名空间。](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md)
