---
description: 使用 Report Builder 和 Microsoft Power BI 时的限制。
title: 限制和规范
feature: Report Builder
role: User, Admin
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
TQID: https://experienceleague.adobe.com/L3R3ufcclrTpw-fKoFLD8Y-v56rTm4tXlXqjaTdmdoQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 631
ht-degree: 26%

---

# 限制和规范

{{legacy-arb}}

## Power BI 发布限制 {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>这些限制仅适用于“作为 Power BI 数据集表发布 Report Builder 请求”选项。

* 每个工作簿最多可以将100个Report Builder请求导出到Power BI。
* 当第101个请求到达时，计划进程将停止导出请求。
* 每个Report Builder请求仅将前10,000行Analytics数据发送到Power BI。 其余行将被忽略。

## 在发布到 Power BI 之后编辑 Report Builder 请求 {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>此规范适用于“作为 Power BI 数据集表发布所有 Report Builder 请求”和“作为 Power BI 数据集表发布工作簿中所有带格式的表”选项。

在将Report Builder请求发布到Power BI后对其进行编辑可能会导致问题。

* **用例1**：您将工作簿发布到Power BI并根据其数据创建可视化图表。 接下来，您对工作簿进行了更改，导致它引用的数据集的其中一个列消失。 然后再重新发布。 这将破坏Power BI中的可视化图表。

  **以下是可视化图表将中断的示例：**

   1. 在 Report Builder 中，使用“页面”维度和“页面查看次数”指标，创建具有一个请求的工作簿。
   2. 安排将此请求发布到 Power BI。
   3. 在Power BI中，为页面和页面查看次数创建一个可视化图表。
   4. 现在，通过从请求中删除页面查看来编辑工作簿。
   5. 使用更新后的工作簿编辑计划，并将请求重新发布到Power BI。
   6. 在将新工作簿发送到Power BI后

      1. 验证它是否覆盖了您首次发布时创建的现有数据集。
      2. 验证已使用“页面”和“访问次数”列正确更新page_1表。
      3. 验证您的可视化是否损坏，因为它引用了page_1表中不再存在的“页面查看次数”列。

  **下面是可视化图表“不会”中断的示例：**

   1. 在 Report Builder 中，使用“页面”维度和“页面查看次数”指标，创建具有一个请求的工作簿。
   2. 安排将此请求发布到 Power BI。
   3. 在Power BI中，为页面和页面查看次数创建一个可视化图表。
   4. 现在编辑 Report Builder 中的工作簿，在保留“页面”和“页面查看次数”的同时添加“访问”指标。
   5. 使用更新后的工作簿编辑计划，并将请求重新发布到Power BI。
   6. 在将新工作簿发送到Power BI后

      1. 验证它是否覆盖了您首次发布时创建的现有数据集。
      2. 验证已使用“页面”、“页面查看次数”和“访问次数”列正确更新page_1表。
      3. 验证可视化图表是否继续正常工作，因为它引用了page_1表中仍存在的两列。

* **用例2**：您将工作簿的一个部分固定到Power BI中的仪表板，随后又将该固定部分（如图表或表）从工作簿中删除。 这将破坏可视化图表。

## 更改 Power BI 报表的名称 {#section_2E7893A78B914EBFACB2B08CBD9E472E}

默认情况下，将从工作簿文件名中填充名称（不带.xlsx扩展名），但空格会被替换为下划线字符。

请记住

* 标签不能是字母和数字的组合，它们可能会被误认为行和列地址。 例如，A100不能是标签，因为它是工作表中单元格的地址。
* 以下字符是无效的标签字符：`'#', '@', '!', '$', '^', '&', '&#42;', '`&#39; 和 `'~', ' '`。 它们将被替换为下划线字符。
* 输入无效名称时，将显示警告消息，建议自动生成名称。 如果单击&#x200B;**[!UICONTROL 是]**，将使用此名称。 如果单击&#x200B;**[!UICONTROL 否]**，高级向导UI将允许您输入新名称。
