---
description: 使用 Report Builder 和 Microsoft Power BI 时的限制。
title: 限制和规范
feature: Report Builder
role: User, Admin
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 100%

---

# 限制和规范

{{legacy-arb}}

## Power BI 发布限制 {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>这些限制仅适用于“作为 Power BI 数据集表发布 Report Builder 请求”选项。

* 对于每个工作簿，最多可向 Power BI 导出 100 个 Report Builder 请求。
* 在达到 101 个请求时，计划过程将停止导出请求。
* 对于每个 Report Builder 请求，只有前 10,000 行 Analytics 数据将被发送到 Power BI。剩余的行将被忽略。

## 在发布到 Power BI 之后编辑 Report Builder 请求 {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>此规范适用于“作为 Power BI 数据集表发布所有 Report Builder 请求”和“作为 Power BI 数据集表发布工作簿中所有带格式的表”选项。

在发布到 Power BI 之后编辑 Report Builder 请求，可能会引发问题。

* **案例 1**：您将工作簿发布到 Power BI 并基于其数据创建可视化。接下来，您对工作簿进行更改，从而导致它所引用的某一列数据集消失。然后重新发布。这将中断 Power BI 中的可视化。

  **以下是一个有关可视化将如何中断的示例：**

   1. 在 Report Builder 中，使用“页面”维度和“页面查看次数”指标，创建具有一个请求的工作簿。
   2. 安排将此请求发布到 Power BI。
   3. 在 Power BI 中，为页面和页面查看次数创建可视化。
   4. 现在，通过从请求中删除页面查看次数，编辑工作簿。
   5. 编辑涉及更新工作簿的计划，并将请求重新发布到 Power BI。
   6. 在新工作簿发送到 Power BI 之后

      1. 验证它覆盖了首次发布时创建的现有数据集。
      2. 验证 page_1 表已正确地更新了“页面”和“访问次数”列。
      3. 验证您的可视化已中断，因为它引用了 page_1 表中不再存在的“页面查看次数”列。

  **以下是一个有关如何不中断可视化的示例：**

   1. 在 Report Builder 中，使用“页面”维度和“页面查看次数”指标，创建具有一个请求的工作簿。
   2. 安排将此请求发布到 Power BI。
   3. 在 Power BI 中，为页面和页面查看次数创建可视化。
   4. 现在编辑 Report Builder 中的工作簿，在保留“页面”和“页面查看次数”的同时添加“访问”指标。
   5. 编辑涉及更新工作簿的计划，并将请求重新发布到 Power BI。
   6. 在新工作簿发送到 Power BI 之后

      1. 验证它覆盖了首次发布时创建的现有数据集。
      2. 验证 page_1 表已正确地更新了“页面”、“页面查看次数”和“访问次数”列。
      3. 验证您的可视化可以继续正常工作，因为它引用了 page_1 表中依然存在的两个列。

* **案例 2**：您将工作簿的某一部分固定到 Power BI 中的功能板，随后又从工作簿中删除固定的部分（例如一个图表或一个表）。这将中断可视化。

## 更改 Power BI 报表的名称 {#section_2E7893A78B914EBFACB2B08CBD9E472E}

默认情况下，将从工作簿文件名填充名称（不含 .xlsx 扩展），但空格由下划线字符替代。

请记住以下事项

* 标签不能是可被误认为行和列地址的字母和数字组合。例如，A100 不能用作标签，因为它是工作表中一个单元格的地址。
* 以下字符是无效的标签字符：`'#', '@', '!', '$', '^', '&', '&#42;', '`&#39; 和 `'~', ' '`。它们将被替换为下划线字符。
* 如果您输入一个无效名称，将显示一则警告消息，并向您推荐一个自动生成的名称。如果单击&#x200B;**[!UICONTROL 是]**，将会使用此名称。如果单击&#x200B;**[!UICONTROL 否]**，高级向导 UI 将让您输入新名称。