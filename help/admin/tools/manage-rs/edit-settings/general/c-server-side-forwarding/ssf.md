---
description: 服务器端转发专为希望实时将数据从Analytics共享到其他Experience Cloud解决方案的客户而设计。 启用服务器端转发后，Analytics 还可在数据收集过程中将数据推送到其他 Experience Cloud 解决方案，并且这些解决方案可将数据推送到 Analytics。
solution: Analytics
title: 服务器端转发概述
feature: Report Suite Settings
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
TQID: https://experienceleague.adobe.com/O03-5Ovxy3Lq-LZjPOseTpOlCXaS1kwD8n2ZM1yJuxY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 887
ht-degree: 68%

---

# 服务器端转发概述

服务器端转发专为希望实时将数据从Analytics共享到其他Experience Cloud解决方案的客户而设计。 启用服务器端转发后，Analytics 还可在数据收集过程中将数据推送到其他 Experience Cloud 解决方案，并且这些解决方案可将数据推送到 Analytics。

服务器端转发改进了数据收集，因为它：

* 减少页面中的调用。 通过服务器端转发，[!DNL Audience Manager] 客户不再需要使用 DIL 进行数据收集，因为它将从 Analytics 进行转发。 删除 DIL 意味着消除 `"/event"` 调用。 减少调用次数有助于缩短页面加载时间，从而让客户在您的网站上获得更好的体验。
* 让您能够利用Experience Cloud解决方案之间的数据共享。
* 遵循我们的Audience Manager代码实施和部署最佳实践。

>[!TIP]
>
>当前使用 Analytics 的 Audience Manager 客户应当迁移到服务器端转发。 新的 Adobe Analytics 和 Audience Manager 客户应当实施服务器端转发（而不是 DIL）作为默认的数据收集和传输方法。

>[!IMPORTANT]
>根据欧盟 Cookie 合规条例的规定，数据控制方（Analytics 客户）现在可以选择将预先同意的数据限制在 Adobe Analytics 中，并阻止将这些数据经由服务器端转发至 Adobe Audience Manager。 新的实施环境变量可以让您标记出在未获得同意的情况下的点击量。 设置该变量后，在收到同意之前，这些点击将不会发送到 Adobe Audience Manager。 有关详细信息，请参阅[GDPR_ePrivacy合规和服务器端转发](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)。

要了解您的组织在实施服务器端转发方面的进展，请执行以下验证步骤：

## ![step1_icon.png 图像](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step1_icon.png) 验证 ECID 服务的实施情况

通过检查 [Analytics 跟踪请求](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html)，验证是否实施了 Experience Cloud ID (ECID) 服务。

在“请求”选项卡中，验证是否设置了 ECID 值。 这可让您了解是否正确实施了身份标识服务，该服务是服务器端转发的先决条件。

* 如果您看到了 ECID 值，请继续执行步骤 2。
* 如果您没有看到 ECID 值，请先[实施身份标识服务](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html)，然后再继续执行步骤 2。

## ![step2_icon.png 图像](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step2_icon.png) 验证服务器端转发实施版本

通过[检查 Analytics 跟踪请求](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)，验证是否已实施服务器端转发的版本。

在“响应”选项卡中，检查响应中是否包含 Audience Manager 数据。 如果您看到：

* **来自 Audience Manager 的 JSON 响应，且其中包含“postbacks”或“dcs_region”之类的项目**：表示您已经启用某种形式的服务器端转发。 继续执行步骤 3。
* **&quot;status&quot;:&quot;SUCCESS&quot;**：表示您已经实施了受众管理模块，但是还没有正确配置服务器端转发。 继续执行步骤 3。
* **2 x 2图像**：您尚未实施服务器端转发或受众管理模块。 要更正此问题：

   * **拥有 DIL 的 Adobe Audience Manager 客户**：密切配合以下 2 项：

      1. 删除DIL代码并安装[受众管理模块](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html)页面代码。
      1. 在Analytics管理员UI中启用服务器端转发，如步骤3中所述。 在删除DIL代码之前启用此设置将复制数据，并创建对Audience Manager的其他计费服务器调用。

   * **新 Adobe Audience Manager 客户**：安装[受众管理模块](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html)页面代码并继续执行步骤 3。 在步骤 3 中开启了服务器端转发之后，才会将数据发送到 Audience Manager。

## ![step3_icon.png 图像](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/step3_icon.png) 验证报表包的服务器端转发实施

验证您是否已在报表包级别实施服务器端转发，而不是使用旧版跟踪服务器方法。

与旧版跟踪服务器方法相比，建议在报表包级别使用服务器端转发，因为您可以在更精细的级别控制从Analytics共享哪些数据。 此外，它还是此Audience Analytics集成的先决条件。

转至&#x200B;**“Analytics”**>**“管理员”**>**“报表包”**>（选择&#x200B;**“报表包”**）>**“编辑设置”**>**“常规”**>**“服务器端转发”**。 如果复选框为：

* **不活动**（您无法进行选择或菜单不存在）：您没有将选定的报表包映射到组织 ID。 联系客户关怀团队以确保正确映射报表包。
* **已禁用**：您未打开新的服务器端转发。 请阅读页面上的内容，然后继续启用该功能。
* **已启用**：您已配置新的服务器端转发。 您还可以设置此Audience Analytics集成。

>[!NOTE]
>
>在全部完成这 3 个步骤之后，数据才会显示在其他 Experience Cloud 解决方案中，例如 [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html) 或 [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)。 这些设置在启用后需要几个小时才会生效。
