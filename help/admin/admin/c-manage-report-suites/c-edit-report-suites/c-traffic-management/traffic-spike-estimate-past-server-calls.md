---
description: 比如说，您可以了解去年特定时间范围内的每日服务器调用平均值，以及服务器调用量在今年的预期增加量。随后可根据此乘数系数安排流量尖峰。
title: 评估过去的服务器调用并安排流量尖峰
feature: Traffic Management
exl-id: 1076ffbf-95a7-478c-a597-04bb3890e4a0
source-git-commit: 6f7f46b0fee46e572a65f639ea511478c0118f4e
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 100%

---

# 评估过去的服务器调用并安排流量尖峰

比如说，您可以了解去年特定时间范围内的每日服务器调用平均值，以及服务器调用量在今年的预期增加量。随后可根据此乘数系数安排流量尖峰。

1. 以管理员身份登录到 Analytics，然后转到&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 流量管理]**。

1. 单击&#x200B;**[!UICONTROL 展开]**&#x200B;以展开报表包列表，然后单击&#x200B;**[!UICONTROL 选择报表包]**&#x200B;以选择多个报表包。

1. 单击&#x200B;**[!UICONTROL 计划尖峰]**。
1. 在&#x200B;**[!UICONTROL 过去的服务器调用数]**&#x200B;下，选择选定报表包的开始日期和结束日期。

   此时会生成“高峰日”、“高峰日服务器调用数”和“每天平均服务器调用数”的数量。

1. 输入乘数因子的值，然后单击&#x200B;**[!UICONTROL 单击以求积并设置]**。

   此时每个报表包都会对其中每列的值进行乘法运算。

1. 在&#x200B;**[!UICONTROL 设置尖峰参数]**&#x200B;下，提交选定报表包的尖峰参数。

   现在已为每个选定的报表包计划了尖峰。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/assets/past_server_calls.png)