---
description: 您必须满足以下 Experience Cloud 解决方案、服务和代码要求，才能实施服务器端转发。这些要求还包括有关如何检查代码版本以及从何处获取最新代码库的说明。
seo-description: 您必须满足以下 Experience Cloud 解决方案、服务和代码要求，才能实施服务器端转发。这些要求还包括有关如何检查代码版本以及从何处获取最新代码库的说明。
seo-title: 服务器端转发要求
solution: Audience Manager
title: 服务器端转发要求
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# 服务器端转发要求

您必须满足以下 Experience Cloud 解决方案、服务和代码要求，才能实施服务器端转发。这些要求还包括有关如何检查代码版本以及从何处获取最新代码库的说明。

## 解决方案要求

服务器端转发适用于 [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html)、[Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) 和/或 [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html)。

## 服务要求

服务器端转发需要 [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)。 标识服务提供通用ID，可在Experience cloud中的所有解决方案中标识网站访客。 您需要先实施该 ID 服务，然后服务器端转发才能正常工作。

## 代码版本

服务器端转发需要下列代码库的 1.5（或更高）版本。作为最佳实践，我们建议使用最新版本，而不是这些要求的最低版本。

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### 确定您的代码库版本

任何用于监视浏览器发起的 HTTP 请求的工具，都可以显示您的 AppMeasurement 和访客 API 代码的版本号。The `AppMeasurement_Module_AudienceManagement.js` does not contain or return a version ID. 以下示例向您显示了 `AppMeasurement.js` 和 `VisitorAPI.js` 代码版本 ID 的显示格式。

* `AppMeasurement.js`:Adobe [Debugger会返回AppMeasurement版本](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) ，如下所示： `Version of Code | JS-1.5.1`. 其他工具可能使用不同的标签，但值始终遵循模式 `JS-X.X.X`，其中 `X` 为版本号。
* `VisitorAPI.js`:查找该参 `d_visid_ver` 数。 It will show you the Visitor ID service like this: `d_visid_ver: 1.5.5`. 早于版本 1.5.2 的访客 API 代码不包含版本号。如果您的监视结果没有返回版本号，则表示您可能使用的是较早的代码库（需要升级）。
