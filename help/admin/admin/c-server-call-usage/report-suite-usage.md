---
description: “报表包使用情况”选项卡提供与您的账单公司关联的所有登录公司所具有的各个报表包在当前使用时段内的服务器调用使用情况数据。
title: 查看报表包使用情况
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 99%

---

# 查看报表包使用情况

“报表包使用情况”选项卡提供与您的账单公司关联的所有登录公司所具有的各个报表包在当前使用时段内的服务器调用使用情况数据。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 服务器调用使用情况]** > **[!UICONTROL 报表包使用情况]**

>[!IMPORTANT]
>
>如果报表包未关联到 Experience Cloud 组织，则该功能板中将不会反映此报表包的使用情况数据。此外，一个账单 ID 可同时与多个 Experience Cloud 绑定；组织和账单 ID 之间并不总是一一对应的关。

“报表包使用情况”功能板

* 可显示您的 Experience Cloud 组织中的各个报表包在当前使用时段内的服务器调用使用情况（所有调用、主调用、次级调用、移动设备主调用、移动设备次级调用）。
* 显示每个服务器调用类别的使用量在总使用量中所占的百分比。
* 每日更新。
* 可下载。
* 允许您访问&#x200B;**[!UICONTROL 管理警报]** UI。

![](/help/admin/admin/c-server-call-usage/assets/report-suite-usage.png)

## 仪表板设置 {#settings}

| 栏目 | 定义 |
|--- |--- |
| 报表包名称 | 报表包的友好名称 |
| 所有调用（占总数的 %） | 当前使用时段内的所有服务器调用。 |
| 主调用 (%) | 当前使用时段内发起的所有主服务器调用（及其占总数的百分比）。 |
| 次级调用 (%) | 当前使用时段内发起的所有次级服务器调用（及其占总数的百分比）。 |
| 移动设备主调用 (%) | 当前使用时段内发起的所有移动设备主服务器调用（及其占总数的百分比）。 |
| 移动设备次级调用 (%) | 当前使用时段内发起的所有移动设备次级服务器调用（及其占总数的百分比）。 |

{style="table-layout:auto"}

## 下载“使用情况”报表 {#download}

此选项允许您下载当前使用时段内的数据，及之前的时间段内（最早可达 2015 年 1 月）的数据。此报表将下载为 .csv 文件。

1. 请至少选择一个报表包。
1. 单击&#x200B;**[!UICONTROL 下载报表]**。

   ![](/help/admin/admin/c-server-call-usage/assets/download_report.png)

| 报表元素 | 描述 |
|--- |--- |
| 文件名 | 硬编码名称：使用情况报表 `day and time of report creation.csv` |
| 包含的报表包 | 此列表中将包含您在“报表服务器使用情况”页面上选择的任何报表包。 |
| 包含的调用类型 | 指定以下选项的任一组合：所有调用（默认）、主调用、次级调用、移动设备主调用、移动设备次级调用。 |
| 时间范围 | 您可以选择当前使用时段，也可以指定自定义的时间范围。对于自定义的时间范围，请指定范围起始时间和范围结束时间。<br>**注意：**&#x200B;您不能下载 2015 年 1 月之前的使用情况数据。</br> |

{style="table-layout:auto"}

1. 单击&#x200B;**[!UICONTROL 下载]**。

以下是下载的 .csv 文件内容的屏幕截图。它包括报表包 ID 的列。报表包 ID 指定了只能包含字母数字字符的唯一 ID。创建报表包后，无法更改此 ID。

![](/help/admin/admin/c-server-call-usage/assets/download-usage.png)
