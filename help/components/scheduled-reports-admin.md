---
description: 让管理员级别的用户能够跨组织查看和管理计划报表。
title: 计划报告队列
feature: Admin Tools
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
exl-id: 7287e6c7-e354-48a0-9343-35dccfc46e63
role: Admin
TQID: https://experienceleague.adobe.com/HL78cbB5NqKCjv4NvZ5OiqjfbwBjI0KAC8hEr8Afd2U
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 54%

---

# 计划报告队列

让管理员级别的用户能够跨组织查看和管理计划报表。

**[!UICONTROL Analytics]** > **[!UICONTROL 组件]** > **[!UICONTROL 所有组件]** > **[!UICONTROL 已安排的报表]**

计划报表管理器中的管理员级别功能包括：

* [显示组织中所有计划报告](/help/components/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690)的选项。
* 在整个组织内[高级筛选功能](/help/components/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275)。
* 新的[报告队列](/help/components/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B)选项卡列出了在报告服务器上排队等待执行的所有报告。
* 在报表队列界面上公布[计划 ID](/help/components/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1)。

## 显示所有计划报告 {#section_3F167CAAEEC24140B476CF95B7402690}

在&#x200B;**[!UICONTROL 报表列表]**&#x200B;选项卡上，除了个人安排的报表之外，还可&#x200B;**[!UICONTROL 显示您组织中所有已安排的报表]**。

>[!NOTE]
>
>**[!UICONTROL 报表名称]**&#x200B;列显示所安排的报表的名称，而&#x200B;**[!UICONTROL 文件名称]**&#x200B;列显示您在“高级提交选项”中设置的任何自定义文件名。 因此，如果您计划了同一报告类型的多个报告，并为每个报告指定自定义名称，则计划报告管理器将显示多个具有相同报告名称但文件名不同的条目。 这是因为计划的后端报表是相同的，因此“报表名称”列的所有报表名称（自定义文件名除外）都是相同的。

![](assets/show_all_scheduled_reports.png)

## 高级过滤功能 {#section_206A52A85DE84947AAB3AD082FBF6275}

例如，如果要过滤所有安排每小时生成一次的报表，可在&#x200B;**[!UICONTROL 高级]**&#x200B;过滤器中指定&#x200B;**[!UICONTROL 频率等于每小时]**，然后单击&#x200B;**[!UICONTROL 应用]**：

![](assets/advanced_filtering_schedl_reports.png)

## 报表队列 {#section_03C866115D354BB182E90BF4D52F1E0B}

通过此队列，您可以管理并可能删除队列中“堵塞”的任何计划报告。 （通常，报表会在4小时后超时。）

![](assets/scheduled_reports_2.png)

通过报表队列，您还可以“跳过一次计划报表”。 只需单击&#x200B;**[!UICONTROL 管理]**&#x200B;列中的蓝色图标。

## 计划 ID {#section_568B70F4228C4229977CB85D2DCD53A1}

当需要与 Adobe 客户关怀部门联系以解决安排报表得问题时，在“报表队列”界面中公开&#x200B;**[!UICONTROL 计划 ID]** 将很有帮助。

![](assets/schedule_id.png)
