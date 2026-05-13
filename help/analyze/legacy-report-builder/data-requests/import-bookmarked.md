---
description: 现在，所有标为书签的报表和功能板报表都作为维度列在“请求向导”的第1步中，并且可以作为Report Builder请求导入。
title: 导入加入书签的报告和功能板小型报告
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
TQID: https://experienceleague.adobe.com/dnOYs7eOvv15K73EPrfRegz1vH9-B5p8xI8d86vPYe4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 241
ht-degree: 26%

---

# 导入加入书签的报告和功能板小型报告

{{legacy-arb}}

现在，所有标为书签的报表和功能板报表都作为维度列在“请求向导”的第1步中，并且可以作为Report Builder请求导入。

当您选择标为书签的报表时，“请求向导”会填充用于定义此标为书签的报表的所有维度和指标。 日期范围、粒度和选定的区段也会根据选定的书签进行更新。

下面显示了“请求向导：第1步”中的功能板及其缩图报表：

![屏幕截图显示“请求向导”第1步（共2步），突出显示检索您的功能板和检索您的书签。](assets/import_dashboard_reportlet.png)

当您单击&#x200B;**[!UICONTROL 检索您的仪表板]**&#x200B;或&#x200B;**[!UICONTROL 检索您的书签]**&#x200B;时，将检索您现有的仪表板和/或书签数据并将其粘贴到工作表中。

>[!NOTE]
>
>仅导入数据，因此，如果书签包含图表或功能板缩图报表仅由图表组成，则仅导入用于填充该图表的数据。

在导入功能板缩图报表（或书签）创建请求后，请求将关联到该缩图报表（或书签）的主要维度。 因此，如果您编辑请求，则树视图将不再选择功能板缩图报表树视图节点（或书签节点）：而是会选择其主要维度。

