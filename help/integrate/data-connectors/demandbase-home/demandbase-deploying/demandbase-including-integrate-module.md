---
description: 集成代码要求集成模块存在于您的Adobe Analytics部署中。
seo-description: 集成代码要求集成模块存在于您的Adobe Analytics部署中。
seo-title: 包括集成模块
title: 包括集成模块
uuid: e574f3db-49fa-4f72-bbcf-fd98840 d3198
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Including the Integrate Module{#including-the-integrate-module}

集成代码要求集成模块存在于您的Adobe Analytics部署中。

如果您尚未将集成模块作为部署的一部分，请根据您的实施类型完成以下步骤。

## For AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Unzip the AppMeasurement zip file that you downloaded from **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL CodeManager]**.

1. Open the file named [!DNL AppMeasurement_Module_Integrate.js].
1. Copy and paste the contents of this file into your primary [!DNL AppMeasurement.js] file.

   >[!NOTE]
   >
   >在文件内的“DO NOT ANCHANTER ANY THANY THE HANTWARE”(DO NOT ANTER任何内容)之前粘贴它。

## For Legacy Code (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. 从数据连接器UI中的“资源”区域下载集成模块(在支持选项卡下)。

   ![](assets/h_code.png)

1. Copy and paste the contents of that file into your [!DNL s_code] file.

   >[!NOTE]
   >
   >在文件内的“DO NOT ANCHANTER ANY THANY THE HANTWARE”(DO NOT ANTER任何内容)之前粘贴它。

