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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 包括集成模块{#including-the-integrate-module}

集成代码要求集成模块存在于您的Adobe Analytics部署中。

如果您尚未将集成模块作为部署的一部分，请根据您的实施类型完成以下步骤。

## 对于AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. 解压缩您从 **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL CodeManager下载的AppMeasurement zip文件]**。

1. 打开命名 [!DNL AppMeasurement_Module_Integrate.js]的文件。
1. 将此文件的内容复制并粘贴到主 [!DNL AppMeasurement.js] 文件中。

   >[!NOTE]
   >
   >在文件内的“DO NOT ANCHANTER ANY THANY THE HANTWARE”(DO NOT ANTER任何内容)之前粘贴它。

## 对于旧版代码(H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. 从数据连接器UI中的“资源”区域下载集成模块(在支持选项卡下)。

   ![](assets/h_code.png)

1. 将该文件的内容复制并粘贴到 [!DNL s_code] 文件中。

   >[!NOTE]
   >
   >在文件内的“DO NOT ANCHANTER ANY THANY THE HANTWARE”(DO NOT ANTER任何内容)之前粘贴它。

