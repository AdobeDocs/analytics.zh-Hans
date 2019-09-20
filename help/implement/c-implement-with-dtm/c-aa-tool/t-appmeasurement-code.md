---
description: 当在 Adobe Analytics 中手动部署动态标签管理时插入 AppMeasurement 代码。
keywords: 动态标签管理；链接帐户；链接帐户；编辑代码；appmeasurement;appmeasurement代码
seo-description: 当在 Adobe Analytics 中手动部署动态标签管理时插入 AppMeasurement 代码。
seo-title: 插入核心 AppMeasurement 代码
solution: Experience Cloud，分析，目标，动态标签管理
title: 插入核心 AppMeasurement 代码
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 插入核心 AppMeasurement 代码

当在 Adobe Analytics 中手动部署动态标签管理时插入 AppMeasurement 代码。

1. On the [!DNL Adobe Analytics] tool page, expand the **[!UICONTROL General]** section, then click **[!UICONTROL Open Editor]**.
1. Unzip the [!DNL AppMeasurement_JavaScript*.zip] file you downloaded in [deploy Adobe Analytics](../../../implement/c-implement-with-dtm/t-analytics-deploy.md#task_3A00639CADF14C9C844F962222077E4E).

   如果您选择自定义库，则在打开此窗口时，该库的代码版本已经是最新的。无需从管理控制台下载 zip 文件。
1. Open [!DNL AppMeasurement.js] in a text editor.
1. Copy and paste the contents into the **[!UICONTROL Edit Code]** window.

   ![](assets/edit-code.png)

1. Adobe recommends adding the following code above the *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >If you add this code, it is recommended that you also select the **[!UICONTROL Set report suites using custom code below]** checkbox in the overall library settings.

1. Click **[!UICONTROL Save and Close]**.

   如果您使用媒体模块、集成模块或实施插件，则也可以将它们复制到代码部分。动态标签管理中的受管代码可以完全按照典型实施中的 JavaScript 文件那样进行配置。

