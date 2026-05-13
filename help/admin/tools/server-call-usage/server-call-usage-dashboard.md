---
description: 如何在 Adobe Analytics 中查看当前的服务器调用使用情况。
title: 查看当前的服务器调用使用情况
feature: Server Call Usage
exl-id: 07eac732-b9d6-41ab-be34-5688eaa8166e
role: Admin
TQID: https://experienceleague.adobe.com/IXKYPEZ0Kk6UWG7RlBGYDhxoLRHBj4UkBFi4YVt-EpI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 293
ht-degree: 25%

---

# 查看当前的服务器调用使用情况

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 服务器调用使用情况]** > **[!UICONTROL 当前使用情况]**

>[!IMPORTANT]
>
>您所看到的任何使用情况和承诺使用数值是所有登录公司和报表包的累计数值。

当前使用情况仪表板

* 显示每种服务器调用类型的服务器调用消耗量和承诺量的细目。 此视图对于不同的客户可能有所不同，并且与您的合同所包括的内容一致。 例如，您可能已注册了4种不同类型的服务器调用：Web的主服务器调用和次服务器调用，以及移动设备的主服务器调用和次服务器调用。 在这种情况下，该视图将包含4个选项卡，每个类型各一个。 在每个选项卡中，您将能够查看当前使用期间的消耗量。
* 将当前使用情况（绿线）与合同使用限制（红线）进行比较。

  ![](/help/admin/tools/server-call-usage/assets/current_period.png)

* 将您当前时段的使用情况与去年的使用情况进行比较（蓝线）。 显然，仅当您的公司具有上一年的服务器调用使用情况数据时，才会显示蓝线。

  >[!NOTE]
  >
  >如果要查看前一段时间的使用情况，则必须转到[报表包使用情况](/help/admin/tools/server-call-usage/report-suite-usage.md)选项卡，并下载前一期间的使用情况数据。

* 列出已使用的调用的百分比（以百分比和原始数据表示）以及已使用的使用时段的百分比（以百分比和原始数据表示）。
* 默认情况下，每日更新，处理延迟为5天。
* 允许您折叠和展开所有缩图报表。

![](/help/admin/tools/server-call-usage/assets/server_call_dashboard.png)

| UI术语 | 定义 |
| --- | --- |
| 当前期间使用情况（绿色） | 当前时段基于[使用时段](/help/admin/tools/server-call-usage/overage-overview.md)。 |
| 上一时段使用情况（蓝色） | 上一期间定义为当前使用期间减去1年。 |
| 使用限制（红色） | 您在此使用期间的合同使用限制。 |
