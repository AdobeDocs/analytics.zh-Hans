---
description: 服务器端转发专为希望将 Analytics 中的数据实时共享到其他 Experience Cloud 解决方案的客户而设计。启用服务器端转发后，在数据收集过程中该功能还允许 Analytics 将数据推送到其他 Experience Cloud 解决方案，而对于这些解决方案，则将数据推送到 Analytics。
solution: Audience Manager
title: 服务器端转发概述
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 服务器端转发概述

服务器端转发专为希望将 Analytics 中的数据实时共享到其他 Experience Cloud 解决方案的客户而设计。启用服务器端转发后，在数据收集过程中该功能还允许 Analytics 将数据推送到其他 Experience Cloud 解决方案，而对于这些解决方案，则将数据推送到 Analytics。

服务器端转发可改进数据收集，原因是：

* 可以减少来自页面的调用。With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. 删除DIL意味着消除呼 `"/event"` 叫。 更少的调用有助于改善页面加载时间，这会为您的网站带来更好的客户体验。
* 让您可以在各 Experience Cloud 解决方案之间利用数据共享功能。
* 符合我们为 Audience Manager 代码实施和部署提供的最佳实践。

>[!TIP]
>
>当前使用Analytics的Audience manager客户应迁移到服务器端转发。 新的 Adobe Analytics 和 Audience Manager 客户应当实施服务器端转发（而不是 DIL）作为默认的数据收集和传输方法。

>[!IMPORTANT]
>根据欧盟 Cookie 合规条例的规定，数据控制方（Analytics 客户）现在可以选择将预先同意的数据限制在 Adobe Analytics 中，并阻止将这些数据经由服务器端转发至 Adobe Audience Manager (AAM)。新的实施环境变量可以让您标记出在未获得同意的情况下的点击量。设置了该变量后，它可以阻止将这些点击量发送到 AAM，直至获得同意为止。有关更多信息，请参阅 GDPR_ePrivacy 合规和服务器端转发。

要了解您的组织在实施服务器端转发方面的进展，请执行以下验证步骤：

## ![step1_icon.png图像验证](assets/step1_icon.png) MID服务实现

通过检查 [Analytics 跟踪请求](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html)，验证是否实施了 Experience Cloud ID (MID) 服务。

在请求选项卡中，验证是否设置了 MID 值。这告诉您，Identity service已正确实施，这是服务器端转发的先决条件。

* 如果您看到了 MID 值，请继续执行步骤 2。
* If you do not see a MID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![step2_icon.png图像验证服务器端转发实施版本](assets/step2_icon.png) ,

通过检查Analytics跟踪请求，验证您是否已实施服 [务器端转发版本](/help/admin/admin/c-server-side-forwarding/ssf-verify.md)。

在“响应”选项卡中，检查响应是否包含Audience manager数据。 如果您看到：

* A **JSON response from Audience Manager that includes items such as "postbacks" or "dcs_region"**: you have some form of server-side forwarding already enabled. 继续执行步骤 3。
* The **"status":"SUCCESS"**: you have the Audience Management Module implemented, but do not have server side forwarding properly configured. 继续执行步骤 3。
* **2 x 2 图像**：表示您没有实施服务器端转发或受众管理模块。要纠正这一问题，请执行以下操作：

   * **具有 DIL 的 AAM 客户**：调整以下 2 个项目以使其紧密配合工作：

      1. 删除 DIL 代码并安装[受众管理模块](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)页面代码。
      1. 按照步骤 3 中所述，在 Analytics 管理员用户界面中启用服务器端转发。如果在删除 DIL 代码之前启用该设置，则将复制数据并创建对 Audience Manager 的额外计费服务器调用。
   * **新 AAM 客户** - 安装[受众管理模块](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html)页面代码并继续执行步骤 3。在步骤 3 中开启了服务器端转发之后，才会将数据发送到 Audience Manager。


## ![step3_icon.png图像](assets/step3_icon.png) ，验证报表包的服务器端转发实现

验证您是否已在报表包级别实施了服务器端转发，而不是采用旧版跟踪服务器方法。

建议采用报表包级别的服务器端转发而不是旧版跟踪服务器方法，因为这样您可以更精细地控制要从 Analytics 共享哪些数据。这也是此 Audience Analytics 集成的先决条件。

Go to **Analytics** &gt; **Admin** &gt; **Report Suites** &gt; (select **report suites**) &gt; **Edit Settings** &gt; **General** &gt; **Server Side Forwarding**. 如果复选框为：

* **不活动**（您无法进行选择或菜单不存在）：表示您没有将选定的报表包映射到 IMS 组织。请确保使用[报表包映射用户界面](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)将适用的报表包映射到相应的 IMS 组织。
* **禁用**：表示您没有开启新的服务器端转发。请阅读本页面上的内容，然后继续启用该功能。
* **启用**：表示您已设置了新的服务器端转发。您还能够设置此 Audience Analytics 集成。

<!-- Meike, check Report Suite Mapping UI link above -->

> [!NOTE] 在所有3个步骤均完成之前，数据不会显示在其 [他Experience cloud解决方案中](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) ，如 [Audience Manager或Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) 。 这些设置在启用后需要几个小时才会生效。

