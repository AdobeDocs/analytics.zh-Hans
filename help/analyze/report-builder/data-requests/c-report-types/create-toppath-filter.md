---
description: 描述如何创建带有预定义过滤器的路径报表。
title: 通过添加从属请求过滤路径报表
topic: Report builder
uuid: dd1294f8-a26b-4254-a9f6-1365b2912adf
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 通过添加从属请求过滤路径报表

描述如何创建带有预定义过滤器的路径报表。

Marketing Reports &amp; Analytics优惠了几份独立报告，这些报告是主要路径报告与预定义过滤器, [!UICONTROL Next] 如 [!UICONTROL Previous Site Section] 和报告、条目 [!UICONTROL Exit Site Section] 和报告以及 [!UICONTROL Single Site Section] 报告。

Report Builder does not offer these as standalone reports, but you can create them through the **[!UICONTROL Add dependent request]** > **[!UICONTROL Path]** context menus. 下面提供了可创建的报表：

* “路径”>“页面流失”
* “路径”>“登入路径”
* “路径”>“退出路径”
* “路径”>“下一页”
* “路径”>“登入路径”>“下一页”
* “路径”>“上一页”
* “路径”>“退出路径”>“上一页”
* “路径”>“登入路径”>“作为登入页”
* “路径”>“退出路径”>“作为退出页”

1. 从现有请求中选择多行，然后右键单击 **[!UICONTROL Add Dependent Request]** > **[!UICONTROL Path]**。

   (Note that you have to select at least 3 rows if you want to see the **[!UICONTROL Page Fallout]** menu item.)

   ![](assets/dependen_request.png)

1. Select the predefined filter, for example **[!UICONTROL Previous Page]**.

   此时会出现“请求向导”，其中已选定“上一页”量度。1. 继续在“请求向导”中优化并生成您的请求。
