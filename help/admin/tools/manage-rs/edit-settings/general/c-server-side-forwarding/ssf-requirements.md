---
description: 您必须满足这些CX Enterprise解决方案、服务和代码要求才能实施服务器端转发。 这些要求还包括有关如何检查代码版本以及在何处获取最新代码库的说明。
solution: Analytics
title: 服务器端转发要求
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: 'https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 52%

---

# 服务器端转发要求

您必须满足这些CX Enterprise解决方案、服务和代码要求才能实施服务器端转发。 这些要求还包括有关如何检查代码版本以及在何处获取最新代码库的说明。

## 解决方案要求

服务器端转发适用于 [Analytics](https://www.adobe.com/cn/data-analytics-cloud/analytics.html)、[Audience Manager](https://www.adobe.com/cn/data-analytics-cloud/audience-manager.html) 和/或 [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)。

## 服务要求

服务器端转发需要[身份标识服务](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 Identity Service提供了一个通用ID ，用于在CX Enterprise的所有解决方案中标识站点访客。 您需要先实施该 ID 服务，然后服务器端转发才能正常工作。

## 代码版本

服务器端转发需要以下列出的代码库版本1.5（或更高版本）。 作为最佳实践，我们建议使用最新版本，而不是使用要求的最低版本。

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### 确定您的代码库版本

任何用于监视浏览器发起的 HTTP 请求的工具，都可以显示您的 AppMeasurement 和访客 API 代码的版本号。 `AppMeasurement_Module_AudienceManagement.js` 不包含或不会返回版本 ID。 以下示例向您显示了 `AppMeasurement.js` 和 `VisitorAPI.js` 代码版本 ID 的显示格式。

* `AppMeasurement.js`：[Adobe 调试器](/help/implement/validate/debugger.md)会返回如下的 AppMeasurement 版本：`Version of Code | JS-1.5.1`。 其他工具可能使用不同的标签，但值始终遵循模式 `JS-X.X.X`，其中 `X` 为版本号。
* `VisitorAPI.js`：查找 `d_visid_ver` 参数。 它将以如下形式显示访客 ID 服务：`d_visid_ver: 1.5.5`。 早于版本1.5.2的访客API代码不包含版本号。 如果您的监视结果未返回版本号，则可能是使用旧版代码库（需要升级）。
