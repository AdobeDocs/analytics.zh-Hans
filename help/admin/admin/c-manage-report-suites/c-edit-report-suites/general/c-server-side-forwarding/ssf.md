---
description: 服务器端转发专为希望将 Analytics 中的数据实时共享到其他 Experience Cloud 解决方案的客户而设计。启用服务器端转发后，Analytics 还可在数据收集过程中将数据推送到其他 Experience Cloud 解决方案，并且这些解决方案可将数据推送到 Analytics。
solution: Analytics
title: 服务器端转发概述
feature: Report Suite Settings
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 100%

---

# 服务器端转发概述

服务器端转发专为希望将 Analytics 中的数据实时共享到其他 Experience Cloud 解决方案的客户而设计。启用服务器端转发后，Analytics 还可在数据收集过程中将数据推送到其他 Experience Cloud 解决方案，并且这些解决方案可将数据推送到 Analytics。

服务器端转发可改进数据收集，原因是：

* 可以减少来自页面的调用。通过服务器端转发，[!DNL Audience Manager] 客户不再需要使用 DIL 进行数据收集，因为它将从 Analytics 进行转发。删除 DIL 意味着消除 `"/event"` 调用。更少的调用有助于改善页面加载时间，这会为您的网站带来更好的客户体验。
* 让您可以在各 Experience Cloud 解决方案之间利用数据共享功能。
* 符合我们为 Audience Manager 代码实施和部署提供的最佳实践。

>[!TIP]
>
>当前使用 Analytics 的 Audience Manager 客户应当迁移到服务器端转发。新的 Adobe Analytics 和 Audience Manager 客户应当实施服务器端转发（而不是 DIL）作为默认的数据收集和传输方法。

>[!IMPORTANT]
>根据欧盟 Cookie 合规条例的规定，数据控制方（Analytics 客户）现在可以选择将预先同意的数据限制在 Adobe Analytics 中，并阻止将这些数据经由服务器端转发至 Adobe Audience Manager。新的实施环境变量可以让您标记出在未获得同意的情况下的点击量。设置该变量后，在收到同意之前，这些点击将不会发送到 Adobe Audience Manager。有关更多信息，请参阅 [GDPR_ePrivacy 合规和服务器端转发](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)。

要了解您的组织在实施服务器端转发方面的进展，请执行以下验证步骤：

## ![step1_icon.png 图像](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) 验证 ECID 服务的实施情况

通过检查 [Analytics 跟踪请求](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=zh-Hans)，验证是否实施了 Experience Cloud ID (ECID) 服务。

在“请求”选项卡中，验证是否设置了 ECID 值。这可让您了解是否正确实施了 Identity 服务，该服务是服务器端转发的先决条件。

* 如果您看到了 ECID 值，请继续执行步骤 2。
* 如果您没有看到 ECID 值，请先[实施 Identity 服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=zh-Hans)，然后再继续执行步骤 2。

## ![step2_icon.png 图像](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) 验证服务器端转发实施版本

通过[检查 Analytics 跟踪请求](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)，验证是否已实施服务器端转发的版本。

在“响应”选项卡中，检查响应中是否包含 Audience Manager 数据。如果您看到：

* **来自 Audience Manager 的 JSON 响应，且其中包含“postbacks”或“dcs_region”之类的项目**：表示您已经启用某种形式的服务器端转发。继续执行步骤 3。
* **&quot;status&quot;:&quot;SUCCESS&quot;**：表示您已经实施了受众管理模块，但是还没有正确配置服务器端转发。继续执行步骤 3。
* **2 x 2 图像**：表示您没有实施服务器端转发或受众管理模块。要纠正这一问题，请执行以下操作：

   * **拥有 DIL 的 Adobe Audience Manager 客户**：密切配合以下 2 项：

      1. 删除 DIL 代码并安装[受众管理模块](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=zh-Hans)页面代码。
      1. 按照步骤 3 中所述，在 Analytics 管理员用户界面中启用服务器端转发。如果在删除 DIL 代码之前启用该设置，则将复制数据并创建对 Audience Manager 的额外计费服务器调用。

   * **新 Adobe Audience Manager 客户**：安装[受众管理模块](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=zh-Hans)页面代码并继续执行步骤 3。在步骤 3 中开启了服务器端转发之后，才会将数据发送到 Audience Manager。

## ![step3_icon.png 图像](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) 验证报表包的服务器端转发实施

验证您是否已在报表包级别实施了服务器端转发，而不是采用旧版跟踪服务器方法。

建议采用报表包级别的服务器端转发而不是旧版跟踪服务器方法，因为这样您可以更精细地控制要从 Analytics 共享哪些数据。这也是此 Audience Analytics 集成的先决条件。

转至&#x200B;**“Analytics”**>**“管理员”**>**“报表包”**>（选择&#x200B;**“报表包”**）>**“编辑设置”**>**“常规”**>**“服务器端转发”**。如果复选框为：

* **不活动**（您无法进行选择或菜单不存在）：您没有将选定的报表包映射到组织 ID。联系客户关怀团队以确保正确映射报表包。
* **禁用**：表示您没有开启新的服务器端转发。请阅读本页面上的内容，然后继续启用该功能。
* **启用**：表示您已设置了新的服务器端转发。您还能够设置此 Audience Analytics 集成。

>[!NOTE]
>
>在全部完成这 3 个步骤之后，数据才会显示在其他 Experience Cloud 解决方案中，例如 [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html?lang=zh-Hans) 或 [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=zh-Hans)。这些设置在启用后需要几个小时才会生效。
