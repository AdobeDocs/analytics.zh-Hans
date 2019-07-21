---
description: '如果您要跟踪其他信息，但没有足够的变量来执行此操作，您现在可以访问其他eVar和成功事件 '
keywords: Analytics实施；evar；事件；evar编号；多少evar；活动数
seo-description: '如果您要跟踪其他信息，但没有足够的变量来执行此操作，您现在可以访问其他eVar和成功事件 '
seo-title: 其他eVar和事件
solution: Analytics
title: 其他eVar和事件
topic: 开发人员和实施
uuid: 6f53069b-6941-40f1-9db6-2d1839822b8f
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 其他eVar和事件

如果要跟踪其他信息，但没有足够的变量这么做，则您现在可以访问附加的 eVar 和成功事件：

>[!NOTE]
>
>JavaScript H-Code不支持这些附加的eVar和事件。

## 对自定义维度和事件的权限 {#section_869EC3D8A5614036A9C586F2B74FA7DC}

| Adobe Analytics 产品 |  |  |  |
|---|---|---|---|
| Adobe Analytics - Foundation | 75 个 prop | 200 个 eVar | 1000 个 事件 |
| Adobe Analytics - [Select](https://www.adobe.com/data-analytics-cloud/analytics/select.html) | 75 个 prop | 200 个 eVar | 1000 个 事件 |
| Adobe Analytics - [Prime](https://www.adobe.com/data-analytics-cloud/analytics/prime.html) | 75 个 prop | 200 个 eVar | 1000 个 事件 |
| Adobe Analytics - [Ultimate](https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html) | 75 个 prop | 250 个 eVar | 1000 个 事件 |

## 填充变量和事件 {#section_DEA51A22BCBB4B92BDD25814AAD296E4}

* Variables can be populated in the data collection library if you are using these versions of [!DNL AppMeasurement]:

   * AppMeasurement for JavaScript 1.4+ 版
   * AppMeasurement for Flash 3.9+ 版
   * AppMeasurement for Java 1.2.8+ 版
   * AppMeasurement for Silverlight/.NET 1.4.2+ 版
   * AppMeasurement for PHP 1.2.2+ 版

* 如果您使用更早版本的代码或 JavaScript H.*，则可以填充上下文数据并使用处理规则填充变量。
* 所有版本的数据收集代码都可填充事件 101 至 1000。
* 根据上下文数据或其他变量，可以使用处理规则填充 eVar 76 至 250。

## 常见问题 {#section_E915B03236BD47DCA065F1FC5A6E30C6}

* **所有的 Adobe Analytics 界面都可以立即访问这些新变量吗？** 这些界面将立即访问： [!UICONTROL Analysis Workspace]、 [!UICONTROL Reports&amp; Analytics]、 [!UICONTROL Report Builder]、 [!UICONTROL Ad Hoc Analysis]、API和 [!UICONTROL Data Workbench]。

* **这些附加的 eVar 和事件将会自动显示在我的数据馈送中吗？**&#x200B;在启用后，数据馈送将可以访问新的变量和事件。只有在您选择包含新的 eVar 列之后，它们才会显示。但是，新的事件在启用后即会显示在 event_list 列中，事件查找表包含这些事件 ID 对应的事件名称。请不要启用新的事件，除非您已准备在数据馈送中使用它们。

* **如何请求新的数据馈送列？**&#x200B;要请求新列，请参阅[配置数据馈送](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_configure.html)。

* **我是一名 Analytics Ultimate 客户，我想要恢复到 Analytics Prime，而且当前我启用了 200 个 eVar，我该怎么办？** Adobe 不会禁用您现有的任何一个 eVar，但将无法再启用更多的 eVar。如果您要禁用 eVar，只有当已启用的 eVar 低于 Analytics Prime 所允许的 200 这一限额时，您才能启用已禁用的 eVar。

