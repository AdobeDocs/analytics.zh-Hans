---
description: “报表包使用情况”选项卡提供与您的账单公司关联的所有登录公司所具有的各个报表包在当前使用时段内的服务器调用使用情况数据。
title: 查看报表包使用情况
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
role: Admin
TQID: 'https://experienceleague.adobe.com/sA3dNQtSIT-j0SnIWh7nPtbRBwk-jQ1z01NoEuReTys'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: f73667dc-d296-4875-8975-ac3fdc3adc42id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c9d85838-8d05-4bc7-9f18-30ec779251bc
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 43%

---

# 查看报表包使用情况

“报表包使用情况”选项卡提供与您的账单公司关联的所有登录公司所具有的各个报表包在当前使用时段内的服务器调用使用情况数据。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 服务器调用使用情况]** > **[!UICONTROL 报表包使用情况]**

>[!IMPORTANT]
>
>如果报表包未关联到CX Enterprise组织，则该功能板中将不会反映此报表包的使用情况数据。 另外，一个账单ID可以绑定到多个CX Enterprise组织；一个组织与账单ID之间并不总是有1:1关系。

报表包使用情况仪表板

* 显示CX Enterprise组织中每个报表包的当前使用时段的服务器调用使用情况（所有调用、主要、次要、移动设备主要、移动设备次要）。
* 显示每个服务器调用类别的整体使用率的百分比。
* 每日更新。
* 可下载。
* 允许您访问&#x200B;**[!UICONTROL 管理警报]** UI。

![](/help/admin/tools/server-call-usage/assets/report-suite-usage.png)

## 仪表板设置 {#settings}

| 列 | 定义 |
|--- |--- |
| 报表包名称 | 报表包的友好名称 |
| 所有调用（占总调用的%） | 在当前使用时段内发生的所有服务器调用。 |
| 主要呼叫(%) | 在当前使用时段中发生的所有主服务器调用（及其占总数的百分比）。 |
| 二次调用(%) | 在当前使用时段中发生的所有次服务器调用（及其占总数的百分比）。 |
| 主要移动设备(%) | 当前使用时段内发生的所有移动设备主服务器调用（及其占总数的百分比）。 |
| 移动辅助(%) | 当前使用时段内发生的所有移动设备次级服务器调用（及其占总数的百分比）。 |

{style="table-layout:auto"}

## 下载使用情况报表 {#download}

通过此选项，可下载当前使用情况数据，以及当前使用时段（追溯到2015年1月）之前的时段中的数据。 报告将下载为.csv文件。

1. 至少选择一个报表包。
1. 单击&#x200B;**[!UICONTROL 下载报表]**。

   ![](/help/admin/tools/server-call-usage/assets/download_report.png)

| 报表元素 | 描述 |
|--- |--- |
| 文件名 | 硬编码名称：使用情况报表 `day and time of report creation.csv` |
| 包含的报告包 | 您在“报表服务器使用情况”页面上选择的任何报表包都包含在此列表中。 |
| 包含的调用类型 | 指定以下选项的任一组合：所有调用（默认）、主调用、次级调用、移动设备主调用、移动设备次级调用。 |
| 时间范围 | 您可以选择当前使用时段，也可以指定自定义的时间范围。  对于自定义的时间范围，请指定范围起始时间和范围结束时间。 <br>**注意：**&#x200B;您不能下载 2015 年 1 月之前的使用情况数据。</br> |

{style="table-layout:auto"}

1. 单击&#x200B;**[!UICONTROL 下载]**。

以下是下载的 .csv 文件内容的屏幕截图。 它包括报表包 ID 的列。 报表包 ID 指定了只能包含字母数字字符的唯一 ID。 创建报表包后，无法更改此 ID。

![](/help/admin/tools/server-call-usage/assets/download-usage.png)
