---
description: 完成集成向导后，您必须激活要连接的每个Qualtrics调查的集成。
seo-description: 完成集成向导后，您必须激活要连接的每个Qualtrics调查的集成。
seo-title: 启用Qualtrics Research Suite中的集成
solution: Analytics
subtopic: Qualtrics
title: 启用Qualtrics Research Suite中的集成
topic: Data connectors
uuid: 2cc6a4a-d17 e-4560-bd5 b-1790851d6274
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Enabling the Integration in Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

完成集成向导后，您必须激活要连接的每个Qualtrics调查的集成。

1. 登录Qualtrics Research Suite。
1. On the **[!UICONTROL My Surveys]** tab, click the **[!UICONTROL Edit]** button for the survey that you want to integrate.
1. Click the **[!UICONTROL Advanced Options]** menu and select **[!UICONTROL Adobe Analytics]**. (如果您看不到此选项，请询问管理员获取所需权限)。

   ![](assets/advanced_options.png)

1. Select the Adobe Analytics Configuration, then click **[!UICONTROL Save]**. 如果没有可用的配置，您可能还没有完成Adobe集成向导。
   1. **[!UICONTROL “包含部分答复”]** 复选框可用于表示您希望在每个部分调查屏幕完成后将数据捕获到Adobe Analytics。如果未选中，则仅对完全完成的调查传输数据。
   1. The **[!UICONTROL Send Timestamp With Beacon]** checkbox should be used only when integrating with a Report Suite that is configured to receive time-stamped data (not common).
   ![](assets/integration_config.png)

