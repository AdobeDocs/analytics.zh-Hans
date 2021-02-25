---
description: 了解有关用户同意在设备或浏览器上存储或阅读非必需cookie的准则和建议。
title: 有关用户同意的CNIL准则和Cookie
translation-type: tm+mt
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# CNIL同意豁免

2020年10月1日，法国数据保护局(“CNIL”)发布了修订版Cookie准则（“准则”）及其关于获取用户同意在用户设备或浏览器(“Recommendations”)上存储或读取非必需Cookie及类似技术的最终建议。

准则对同意要求提供有限豁免（“同意豁免”）。 “同意豁免”适用于分析Cookie，其用途仅限于代表Web发布者评估网站或应用程序的受众。 准则规定，要适用同意豁免，必须满足以下条件：

* 最多25个月的数据保留期  您可以在“Analytics”>“Admin”>“Data Governance”下查看当前的数据保留设置。  [数据保留](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* 13个月Cookie限制。  您可以使用`cookieLifetime`变量覆盖分析Cookie过期。  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* 范围有限。 Cookie的范围必须限于单个站点或应用程序。 [浏览器Cookie](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;third-party-cookie-implementations)
* 匿名化. 匿名化IP地址的最后八位字节。 [一般帐户设置](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* 隐藏访客ID以免报告。  默认情况下，访客ID在Adobe Workspace和Adobe Reports and Analytics中不可见。  访客ID在数据馈送和Data warehouse中可用。  访问Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;任务_040673FE3E3E429B9531FBCB8B6A4391)中的[访问权限可以限制对数据馈送和Data warehouse的访问
* 地理位置参数。 地理位置不能比邮政编码级别更精确。 [Zip选](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip-in-adobe-experience-platform-launch) 项和一 [般帐户设置](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* 设置选择加入选项。  通过选择加入服务，您可以设置访客协议，以确定您在访问站点时是否可以在用户设备或浏览器上设置Cookie。 [选择加入服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* 防止数据共享。  要阻止与Adobe Audience Manager共享数据，请使用[隐私报告](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;变量)的`opt.dmp`上下文变量阻止共享点击。
* 访问和删除功能。 利用访问和删除请求的Privacy Service。 [分析与Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## 数据收集的其他注意事项

还有以下其他注意事项：

* 未经事先同意，不得在网站或应用程序外进行测量，例如不得在网站外活动、电子邮件活动或iFrames。
* 未经同意，不得收集变量中的个人信息。
* 数据仅用于生成匿名统计数据，而不与其他数据结合。
* 数据不用于交叉引用操作。
* 未收集GPS地理定位数据。

有关详细信息，请参阅[CNIL Cookie Exemption](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications)网站。
