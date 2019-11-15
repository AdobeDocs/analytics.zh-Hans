---
description: 当在 Adobe Analytics 中手动部署动态标签管理时插入 AppMeasurement 代码。
keywords: Dynamic Tag Management;linked accounts;linking accounts;edit code;appmeasurement;appmeasurement code
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 插入核心 AppMeasurement 代码
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 插入核心 AppMeasurement 代码

当在 Adobe Analytics 中手动部署动态标签管理时插入 AppMeasurement 代码。

1. 在 [!DNL Adobe Analytics] 工具页面中，展开&#x200B;**[!UICONTROL 常规]**&#x200B;部分，然后单击&#x200B;**[!UICONTROL 打开编辑器]**。
1. 解压缩在[部署 Adobe Analytics](/help/implement/c-implement-with-dtm/t-analytics-deploy.md) 时下载的 [!DNL AppMeasurement_JavaScript*.zip] 文件。

   如果您选择自定义库，则在打开此窗口时，该库的代码版本已经是最新的。无需从管理控制台下载 zip 文件。
1. 在文本编辑器中打开 [!DNL AppMeasurement.js]。
1. 将相关内容复制并粘贴到&#x200B;**[!UICONTROL 编辑代码]**&#x200B;窗口中。

   ![](assets/edit-code.png)

1. Adobe 建议在 *`Do Not Alter Anything Below This Line`* 上方添加以下代码：

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >如果添加此代码，建议您同时选中整体库设置中的&#x200B;**[!UICONTROL 使用下面的自定义代码设置报表包]**&#x200B;复选框。

1. 单击&#x200B;**[!UICONTROL 保存并关闭]**。

   如果您使用媒体模块、集成模块或实施插件，则也可以将它们复制到代码部分。动态标签管理中的受管代码可以完全按照典型实施中的 JavaScript 文件那样进行配置。

