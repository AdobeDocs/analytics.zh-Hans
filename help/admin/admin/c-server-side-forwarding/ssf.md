---
description: 服务器端转发专为希望将数据从Analytics实时共享到其他Experience Cloud解决方案的客户而设计。 启用服务器端转发后，Analytics还可以将数据推送到其他Experience Cloud解决方案，并让这些解决方案在数据收集过程中将数据推送到Analytics。
solution: Audience Manager
title: 服务器端转发概述
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 服务器端转发概述

服务器端转发专为希望将数据从Analytics实时共享到其他Experience Cloud解决方案的客户而设计。 启用服务器端转发后，Analytics还可以将数据推送到其他Experience Cloud解决方案，并让这些解决方案在数据收集过程中将数据推送到Analytics。

服务器端转发在数据收集方面有所改进，因为它：

* 减少页面调用。 通过服务器端转发，[!DNL Audience Manager] 客户不再需要使用 DIL 进行数据收集，因为它将从 Analytics 进行转发。删除 DIL 意味着消除 `"/event"` 调用。更少的调用有助于缩短页面加载时间，从而改善您网站上的客户体验。
* 让您充分利用Experience Cloud解决方案之间的数据共享。
* 遵守我们关于受众管理器代码实施和部署的最佳实践。

>[!TIP]
>
>当前使用 Analytics 的 Audience Manager 客户应当迁移到服务器端转发。新的 Adobe Analytics 和 Audience Manager 客户应当实施服务器端转发（而不是 DIL）作为默认的数据收集和传输方法。

>[!IMPORTANT]
>根据欧盟 Cookie 合规条例的规定，数据控制方（Analytics 客户）现在可以选择将预先同意的数据限制在 Adobe Analytics 中，并阻止将这些数据经由服务器端转发至 Adobe Audience Manager (AAM)。新的实施上下文变量可让您标记未收到同意的点击。 设置变量后，该变量将阻止在收到同意之前将这些点击发送到AAM。 For more information, see [GDPR_ePrivacy compliance and server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

要了解您的组织在实施服务器端转发方面的进展，请执行以下验证步骤：

## ![step1_icon.png 图像](assets/step1_icon.png) 验证 ECID 服务的实施情况

通过检查 [Analytics 跟踪请求](https://marketing.adobe.com/resources/help/zh_CN/mcvid/mcvid-test-verify.html)，验证是否实施了 Experience Cloud ID (ECID) 服务。

在“请求”选项卡中，验证是否设置了 ECID 值。这可让您了解是否正确实施了 Identity 服务，该服务是服务器端转发的先决条件。

* 如果您看到了 ECID 值，请继续执行步骤 2。
* 如果您没有看到 ECID 值，请先[实施 Identity 服务](https://marketing.adobe.com/resources/help/zh_CN/mcvid/mcvid-implementation-guides.html)，然后再继续执行步骤 2。

## ![step2_icon.png 图像](assets/step2_icon.png) 验证服务器端转发实施版本

通过[检查 Analytics 跟踪请求](/help/admin/admin/c-server-side-forwarding/ssf-verify.md)，验证是否已实施服务器端转发的版本。

在“响应”选项卡中，检查响应中是否包含 Audience Manager 数据。如果您看到：

* **来自 Audience Manager 的 JSON 响应，且其中包含“postbacks”或“dcs_region”之类的项目**：表示您已经启用某种形式的服务器端转发。继续执行步骤 3。
* **&quot;status&quot;:&quot;SUCCESS&quot;**：表示您已经实施了受众管理模块，但是还没有正确配置服务器端转发。继续执行步骤 3。
* 2 **x2图像**:您没有实现服务器端转发或受众管理模块。 要更正此问题，请执行以下操作：

   * **具有DIL的AAM客户**:紧密结合协调以下2个项目：

      1. 删除DIL代码并安装 [受众管理模块页](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) 码。
      1. 如步骤3所述，在Analytics管理员UI中启用服务器端转发。 在删除DIL代码之前启用此设置将重复数据并创建额外计费服务器调用至受众管理器。
   * **新的AAM客户** -安装 [受众管理模块页面代码](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) ，然后继续执行步骤3。 在步骤3中打开服务器端转发之前，数据不会发送到受众管理器。


## ![step3_icon.png 图像](assets/step3_icon.png) 验证报表包的服务器端转发实施

验证您是否在报表包级别实现了服务器端转发，而不是采用传统的跟踪服务器方法。

建议在报告包级别进行服务器端转发，而不要使用传统的跟踪服务器方法，因为您可以更精细地控制从Analytics共享的数据。 它也是此受众分析集成的先决条件。

转至 **Analytics** > **管理员** > **报表包** >（选择&#x200B;**报表包**）> **编辑设置** > **常规** > **服务器端转发**。如果复选框为：

* **不活动**（您无法进行选择或菜单不存在）：表示您没有将选定的报表包映射到 IMS 组织。请确保使用[报表包映射 UI](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/about-core-services/report-suite-mapping.html)，将适用的报表包映射到相应的 Experience Cloud 组织。
* **禁用**:您没有打开新的服务器端转发。 阅读页面上的内容，然后继续启用该功能。
* **已启用**:您已配置新的服务器端转发。 您还可以设置此受众分析集成。

>[!NOTE] 在全部完成这 3 个步骤之后，数据才会显示在其他 Experience Cloud 解决方案中，例如 [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) 或 [Audiences](https://marketing.adobe.com/resources/help/zh_CN/mcloud/audience_library.html)。这些设置在启用后需要几个小时才会生效。

