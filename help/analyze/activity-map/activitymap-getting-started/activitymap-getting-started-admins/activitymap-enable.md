---
description: 解释分析管理员需要完成以启用[!DNL Activity Map]链接集合和用户下载的步骤。
seo-description: 解释分析管理员需要完成以启用[!DNL Activity Map]链接集合和用户下载的步骤。
seo-title: 启用[!DNL Activity Map]
solution: Analytics
title: 启用[!DNL Activity Map]
topic: Activity Map
uuid: 3043319-d0e6-4977-951a-4492b356e1f2
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# 启用[!DNL Activity Map]{#enable-activity-map}

Explains the steps the Analytics Admin needs to complete to enable [!DNL Activity Map] link collection and user download.

## 步骤 1. Update Your AppMeasurement (Javascript) Code to v1.6 (or higher) {#section_5D1586289DF2489289B1B6C1C80C300D}

The [!DNL Activity Map] module is part of the AppMeasurement.js file (located at the top of the file). The AppMeasurement library will load the [!DNL Activity Map] module when instantiated.

[!DNL Activity Map]除非您更新至 AppMeasurement 的这个版本（或更高版本），否则无法收集 数据。

1. Download the latest AppMeasurement code (AppMeasurement_Javascript-1.6.zip) by going to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]** and [implement it](https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html).

   我们已经提供了一些[实现代码样例](../../../../analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-sample-implementation-code.md#concept_EC27DA8A62F5411EBED51284CB7E1734)，以帮助您直观地了解在添加 模块后代码产生的变化。[!DNL Activity Map]

1. 验证实现情况：

   1. 点击可点击的元素后，数据就会存储到名为 s_sq 的 Cookie 中。
   1. The [!DNL Activity Map] data can be seen in the query-string on the tracking call. 例如：

      ```
      …&c.&a.&[!DNL Activity Map].&link=My%20Link&region=My%20Region&page=My%20Page&.[!DNL Activity Map]&.a&.c&...
      ```

1. Break this report down by **[!UICONTROL [!DNL Activity Map]Link by Region]** to see the link/region for that page:  ![](assets/am_breakdown.png){width="400px"}

## 步骤 2. 启用报 [!DNL Activity Map] 告 {#section_D14F15D2FC0346FCAD8B3B87E6DD33D4}

First, you need to enable [!DNL Activity Map] reports at a report-suite level.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin &gt; Report Suites &gt;[select report suite]&gt; Edit Settings &gt;[!DNL Activity Map]]** &gt; **[!UICONTROL [!DNL Activity Map]Reporting]** .
1. [!DNL Activity Map] 在报告中收集链接 [!DNL Activity Map] 数据。 For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable[!DNL Activity Map]Reports]**.

   该步骤会添加您收集数据所需的所有维度。

1. After about an hour, check the [[!DNL Activity Map] Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), which shows all the pages where users clicked on a link.

## 步骤 3. Add users to [!DNL Activity Map] access group {#section_4C7A47BB7DEF4AFFBC276392467F9675}

1. Click **[!UICONTROL Add Users to Group]**.

   这会把您带入“管理控制台”中的群组管理页面。

1. [将用户添加到此组](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) ，并 **[!UICONTROL 保存组]**。

1. This allow your Admin users to download [!DNL Activity Map] from  **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Tools]** &gt; **[!UICONTROL ActivityMap]** .

<note>
  如果您希望非管理员用户下载[!DNL Activity Map]，您需要创建一个新用户组，该用户组提供“工具” <span class="uicontrol"> &gt;“ </span> 旧版ClickMap安装”权限 <span class="uicontrol"></span>。 然后，您可以将非管理员用户添加到此组。 此权限级别与[!DNL Activity Map]访问权限相结合将提供下载和使用该工具的全面权限。 
</note>
