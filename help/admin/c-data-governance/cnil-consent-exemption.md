---
description: 了解关于用户准许在设备或浏览器上存储或读取非必要 Cookie 的准则和建议。
title: 关于用户准许和 Cookie 的 CNIL 准则是什么
feature: Data Governance
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
source-git-commit: 0d3cdf77089ee5e80daa511c29217c911e2eb955
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 75%

---

# CNIL 准许豁免

2020年10月1日，法国数据保护局(“CNIL”)发布了其Cookie准则（“准则”）的修订版本，以及关于获取用户同意在用户设备或浏览器(“Recommendations”)上存储或读取非必需Cookie及类似技术的最终建议。

准则对同意要求提供了有限的豁免（“同意豁免”）。 准许豁免适用于只是为了代表 Web 发布者度量网站或应用程序的受众的 Analytics Cookie。准则规定，要适用准许豁免，必须满足以下条件：

* 数据保留期最长为 25 个月。您可以在 [!UICONTROL Analytics] > [!UICONTROL 管理员] > [!UICONTROL 数据管理].  [数据保留](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=zh-Hans)
* 在 ECID 中禁用第三方 Cookie。[disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html#id-service-api?lang=zh-Hans)、[disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html#id-service-api?lang=zh-Hans) 和 [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html#id-service-api?lang=zh-Hans)
* Cookie 有效期最长为 13 个月。可使用 `cookieLifetime` 变量取代 Analytics Cookie 有效期。Experience Cloud Cookie（包括 Analytics 和 ECID）会随着每次访问而延长 Cookie 过期日期。要设置静态的非滚动 Cookie 到期时间，您可以：(1) 编写自定义代码以设置删除 Cookie 的日期，或者 (2) 使用 CMP 来控制 Cookie 的重置日期。[cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=zh-Hans) 和 [Experience Cloud Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html#ec-cookies?lang=zh-Hans)
* 范围有限。Cookie 的范围必须限制在单个网站或应用程序。[浏览器 Cookie](https://experienceleague.adobe.com/docs/analytics/technotes/cookies/cookies.html#third-party-cookie-limitations)
* 匿名化。将 IP 地址的最后一个八位字节数匿名化。[常规帐户设置](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
* 从报表中隐藏访客 ID。默认情况下访客 ID 在 Adobe Workspace 和 Adobe Reports and Analytics 中不可见。可在数据馈送和 Data Warehouse 中找到访客 ID。[Admin Console 中的“访问权限”](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-Hans)可限制对数据馈送和 Data Warehouse 的访问 和[数据馈送列参考](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html#columns%2C-descriptions%2C-and-data-types?lang=zh-Hans)
* 地理位置参数。地理位置再精确，也达不到邮编级别。[邮编选项](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=zh-Hans)和[常规帐户设置](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=zh-Hans)
* 设置选择加入选项。选择加入服务允许您设置访客协议，以确定在用户访问网站时是否可以在用户的设备或浏览器上设置Cookie。 [选择加入服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hans)
* 阻止数据共享。要阻止将数据共享到 Adobe Audience Manager，请将 `opt.dmp` 上下文变量用于[隐私报表](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)以阻止共享点击。
* 访问和删除功能。将 Privacy Service 用于访问和删除请求。[Analytics 和 Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=zh-Hans)

## 关于数据收集的其他注意事项

另外还涉及以下这些注意事项：

* Adobe Analytics 在美国、英国和新加坡设有数据处理中心，以便为所有客户提供灵活的区域性数据收集、处理和存储。配置Adobe Analytics的初始设置时，客户可以选择其所需的数据处理中心位置。 客户数据最终会存储在其选定区域中，以供核心Analytics产品使用。
* 请考虑在 Analytics 变量中收集选择加入状态，以便将选择加入数据与选择退出数据分离，以供分段、虚拟报表包或路由到单独的端点。
* 未经事先许可，不得在网站或应用程序之外进行度量，例如不得进行站外营销活动、电子邮件营销活动或嵌入 iframe。
* 未经许可，不允许收集变量中的个人信息。[在用户同意的基础上控制 Experience Cloud 活动](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html#implementing-opt-in-on-the-page)
* 数据只能用于生成匿名的统计数据，而不得与其他数据一起使用。
* 数据不得用于交叉引用操作。
* 不得收集 GPS 地理位置数据。
* 当最终用户同意后，可修改上述设置并放松限制。

>[!IMPORTANT]
>
>本文档不是作为法律或法规建议提供的，也不构成本Adobe的任何担保或合同承诺。 我们鼓励客户就与本主题相关的问题，就客户的法律和法规义务寻求独立的法律建议。


有关详细信息，请参阅 [CNIL Cookie 豁免](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)网站。

