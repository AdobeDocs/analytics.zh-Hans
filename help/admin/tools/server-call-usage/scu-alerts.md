---
description: 添加或管理服务器所有使用情况警报。 设置警报后，该警报将应用于账单公司旗下的所有登录公司所具有的全部报表包。
title: “服务器调用使用情况”警报
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
role: Admin
TQID: https://experienceleague.adobe.com/aF3SxS36Y1xQN-saS6NTRJoN6H5XwgCx2iRmWPvUPm0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 5e560c5a1c241a297a7bc876978f2996e793e1ea
workflow-type: tm+mt
source-wordcount: 517
ht-degree: 44%

---

# 服务器调用使用情况警报

设置警报后，该警报将应用于账单公司旗下的所有登录公司所具有的全部报表包。

服务器调用使用情况警报是[警报](/help/components/alerts/alert-manager.md)用户界面的一部分。

该界面中已预填充了 **1 个默认警报**，该默认警报将显示在有权访问“服务器调用使用情况”功能的任何登录公司中。 如果满足了以下任一条件，此警报将触发一条发送给所有登录公司管理员的通知消息：

* 对于您有权使用的任何服务器调用类型，“任何”服务器调用使用量“高于或等于”100%，或者
* 对于您有权使用的任何服务器调用类型，“任何”服务器调用使用量“高于或等于”90%，或者
* 对于您有权使用的任何服务器调用类型，“任何”服务器调用使用情况“高于或等于”75%，并且“所用时间段”低于或等于使用时段的75%。

![](/help/admin/tools/server-call-usage/assets/alerts.png)

您可以通过两种方式访问服务器调用使用情况警报：

* 单击“当前使用情况”选项卡或“报表包使用情况”选项卡右上角的&#x200B;**[!UICONTROL 管理警报]**；或
* 在 Adobe Analytics 中导航到&#x200B;**[!UICONTROL 组件]** > **[!UICONTROL 警报]**。

## 创建服务器调用使用情况警报 {#create}

要创建更多警报，请

1. 单击 **[!UICONTROL + 添加]**，然后选择&#x200B;**[!UICONTROL “服务器调用使用情况”警报]**。

   ![](/help/admin/tools/server-call-usage/assets/server_call_alert.png)

1. 定义警报。

   ![](/help/admin/tools/server-call-usage/assets/sc_alert.png)

   * **标题**：指定描述性名称。 如果没有名称，您将无法保存警报。
   * **时间粒度**：指查看警报的频率。 *目前仅支持“每周”粒度。* 这意味着将每周检查一次警报，并且将从当前使用时段回看数据。
   * **收件人**：指定当警报触发指定的阈值时，组织中应接收电子邮件的人员。
   * **过期日期**：默认情况下，警报会在创建日期一年以后过期。
   * **发送警报时间**：

      * 以下任何一个量度触发器
添加服务器调用类型作为量度，然后选择限定条件以及阈值，从而指定警报触发条件：
         * 大于或等于
         * 小于或等于
      * 使用
指定所用使用时段的阈值和条件（“大于或等于”或者“小于或等于”）。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 管理“服务器调用使用情况”警报 {#manage}

![](/help/admin/tools/server-call-usage/assets/alert_mgmt.png)

要管理警报，请执行以下操作：

1. 选中一个或多个警报旁边的复选框。 警报管理操作显示在顶部。
1. 完成以下一项或多项操作：

   | 操作 | 定义 |
   |--- |--- |
   | + 添加 | 通过单击 [!UICONTROL + 添加]访问[警报生成器](/help/admin/tools/server-call-usage/scu-alerts.md)。 |
   | 标记 | 标记警报以组织警报以便于使用。 |
   | 删除 | 您可以删除默认警报以外的所有警报。 |
   | 重命名 | 您可以重命名默认警报以外的所有警报。 |
   | 批准 | 批准警报以使其“官方”。 |
   | 启用/禁用 | 您可以启用或禁用所有警报，甚至默认警报。 |
   | 续订 | 选择一个或多个警报后，可以续订它们。 这会将它们的过期日期延长一年的时间（从单击[!UICONTROL 续订]之日算起，而不考虑它们的原始过期日期）。 |
   | 导出到 CSV | 查看[下载使用情况报告](/help/admin/tools/server-call-usage/report-suite-usage.md) |

   {style="table-layout:auto"}
