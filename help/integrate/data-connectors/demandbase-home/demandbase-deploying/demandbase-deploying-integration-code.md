---
description: 完成集成向导后，您必须将集成代码部署到Adobe Analytics部署代码(s_ code)。
seo-description: 完成集成向导后，您必须将集成代码部署到Adobe Analytics部署代码(s_ code)。
seo-title: 部署集成代码
title: 部署集成代码
uuid: b3fbda0b-4ed3-4967-84ee-6c66564606e7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Deploying the Integration Code{#deploying-the-integration-code}

完成集成向导后，您必须将集成代码部署到Adobe Analytics部署代码(s_ code)。

>[!NOTE]
>
>如果使用Adobe TagManager或Dynamic Tag Management部署Adobe Analytics，则可以使用其中一种工具轻松添加集成代码。

1. Go to the **[!UICONTROL Support]** tab and download and save the `integration code v2_0_1` resource from the Resources area of the integration.

1. If applicable, make any necessary modifications to the code For more information, see [Modifying the Integration Code](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855).
1. 如果您的Adobe Analytics部署代码中没有集成模块，请包含集成模块。For more information, see [Including the Integrate Module](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e).
1. 使用以下方法之一部署代码：

   * 使用Adobe TagManager或Dynamic Tag Management添加代码。
   * 或者，向负责更新Adobe Analytics部署代码的组织资源发送代码。

>[!IMPORTANT]
>
>在部署到生产环境之前，确保您在开发/阶段环境中测试了此集成的部署。

