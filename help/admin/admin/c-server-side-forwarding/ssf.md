---
description: 服务器端转发专为希望将 Analytics 中的数据实时共享到其他 Experience Cloud 解决方案的客户而设计。启用服务器端转发后，在数据收集过程中该功能还允许 Analytics 将数据推送到其他 Experience Cloud 解决方案，而对于这些解决方案，则将数据推送到 Analytics。
seo-description: 服务器端转发专为希望将 Analytics 中的数据实时共享到其他 Experience Cloud 解决方案的客户而设计。启用服务器端转发后，在数据收集过程中该功能还允许 Analytics 将数据推送到其他 Experience Cloud 解决方案，而对于这些解决方案，则将数据推送到 Analytics。
seo-title: 服务器端转发概述
solution: Audience Manager
title: 服务器端转发概述
uuid: 22ddbde5-6805-4eba-8f82-62-6277264dca
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 服务器端转发概述

服务器端转发专为希望将 Analytics 中的数据实时共享到其他 Experience Cloud 解决方案的客户而设计。启用服务器端转发后，在数据收集过程中该功能还允许 Analytics 将数据推送到其他 Experience Cloud 解决方案，而对于这些解决方案，则将数据推送到 Analytics。

服务器端转发可改进数据收集，原因是：

* 可以减少来自页面的调用。With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating an `"/event"` call. 更少的调用有助于改善页面加载时间，这会为您的网站带来更好的客户体验。
* 让您可以在各 Experience Cloud 解决方案之间利用数据共享功能。
* 符合我们为 Audience Manager 代码实施和部署提供的最佳实践。

>[!TIP]
>
>使用Analytics的当前Audience Manager客户应迁移到服务器端转发。新的 Adobe Analytics 和 Audience Manager 客户应当实施服务器端转发（而不是 DIL）作为默认的数据收集和传输方法。

>[!IMPORTANT]
>根据欧盟 Cookie 合规条例的规定，数据控制方（Analytics 客户）现在可以选择将预先同意的数据限制在 Adobe Analytics 中，并阻止将这些数据经由服务器端转发至 Adobe Audience Manager (AAM)。新的实施环境变量可以让您标记出在未获得同意的情况下的点击量。设置了该变量后，它可以阻止将这些点击量发送到 AAM，直至获得同意为止。有关更多信息，请参阅 GDPR_ePrivacy 合规和服务器端转发。

要了解您的组织在实施服务器端转发方面的进展，请执行以下验证步骤：

## ![step1_ icon. png图像](assets/step1_icon.png) 验证MID服务实现

通过检查 [Analytics 跟踪请求](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html)，验证是否实施了 Experience Cloud ID (MID) 服务。

在请求选项卡中，验证是否设置了 MID 值。这告诉您Identity Service得到正确实施，这是服务器端转发的先决条件。

* 如果您看到了 MID 值，请继续执行步骤 2。
* If you do not see a MID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![step2_ icon. png图像](assets/step2_icon.png) 验证服务器端转发实施版本

[检查Analytics跟踪请求](../../../admin/admin/c-server-side-forwarding/ssf-verify.md)，验证您是否已经有服务器端转发版本。

在“响应”选项卡中，检查响应中是否包含 Audience Manager 数据。如果您看到：

* **来自 Audience Manager 的 JSON 响应，且其中包含“postbacks”或“dcs_region”之类的项目**：表示您已经启用某种形式的服务器端转发。继续执行步骤 3。
* **"status":"SUCCESS"**：表示您已经实施受众管理模块，但是还没有正确配置服务器端转发。继续执行步骤 3。
* **2 x 2 图像**：表示您没有实施服务器端转发或受众管理模块。要纠正这一问题，请执行以下操作：

   * **具有 DIL 的 AAM 客户**：调整以下 2 个项目以使其紧密配合工作：

      1. 删除 DIL 代码并安装[受众管理模块](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)页面代码。
      1. 按照步骤 3 中所述，在 Analytics 管理员用户界面中启用服务器端转发。如果在删除 DIL 代码之前启用该设置，则将复制数据并创建对 Audience Manager 的额外计费服务器调用。
   * **新 AAM 客户** - 安装[受众管理模块](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)页面代码并继续执行步骤 3。在步骤 3 中开启了服务器端转发之后，才会将数据发送到 Audience Manager。


## ![step3_ icon. png图像](assets/step3_icon.png) 验证报告套件的服务器端转发实施

验证您是否已在报表包级别实施了服务器端转发，而不是采用旧版跟踪服务器方法。

建议采用报表包级别的服务器端转发而不是旧版跟踪服务器方法，因为这样您可以更精细地控制要从 Analytics 共享哪些数据。这也是此 Audience Analytics 集成的先决条件。

Go to **Analytics** &gt; **Admin** &gt; **Report Suites** &gt; (select **report suites**) &gt; **Edit Settings** &gt; **General** &gt; **Server Side Forwarding**. 如果复选框为：

* **不活动**（您无法进行选择或菜单不存在）：表示您没有将选定的报表包映射到 IMS 组织。请确保使用[报表包映射用户界面](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)将适用的报表包映射到相应的 IMS 组织。
* **禁用**：表示您没有开启新的服务器端转发。请阅读本页面上的内容，然后继续启用该功能。
* **启用**：表示您已设置了新的服务器端转发。您还能够设置此 Audience Analytics 集成。

<!-- Meike, check Report Suite Mapping UI link above -->

>[!NOTE]
>
>Data will not appear in other Experience Cloud solutions, such as [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) until all 3 steps are complete. 这些设置在启用后需要几个小时才会生效。

