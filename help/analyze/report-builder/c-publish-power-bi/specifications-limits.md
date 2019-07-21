---
description: 'null'
seo-description: 'null'
seo-title: 限制和规范
title: 限制和规范
uuid: 6717b6ea-7e01-49b8-8f6e-fb733 a03 b687
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 限制和规范

## Power BI publishing restrictions {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>这些限制仅适用于“将报告生成器请求作为Power BI数据集表发布”选项。

* 对于每个工作簿，最多可向 Power BI 导出 100 个 Report Builder 请求。
* 在达到 101 个请求时，计划过程将停止导出请求。
* 对于每个 Report Builder 请求，只有前 10,000 行 Analytics 数据将被发送到 Power BI。剩余的行将被忽略。

## Edit a Report Builder request after publishing to Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>此规范适用于以下选项：“将所有Report Builder请求作为Power BI数据集表发布”和“将工作簿中的所有格式化表格发布为Power BI数据集表”选项。

在发布到 Power BI 之后编辑 Report Builder 请求，可能会引发问题。

* **案例 1**：您将工作簿发布到 Power BI 并基于其数据创建可视化。接下来，您对工作簿进行更改，从而导致它所引用的某一列数据集消失。然后重新发布。这将中断 Power BI 中的可视化。

   **以下是一个有关可视化将如何中断的示例：**

   1. 在 Report Builder 中，使用“页面”维度和“页面查看次数”量度，创建具有一个请求的工作簿。
   1. [计划此请求](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463)以将其发布到 Power BI。
   1. 在 Power BI 中，为页面和页面查看次数创建可视化。
   1. 现在，通过从请求中删除页面查看次数，编辑工作簿。
   1. 编辑涉及更新工作簿的计划，并将请求重新发布到 Power BI。
   1. 在新工作簿发送到 Power BI 之后

      1. 验证它覆盖了首次发布时创建的现有数据集。
      1. 验证 page_1 表已正确地更新了“页面”和“访问次数”列。
      1. 验证您的可视化已中断，因为它引用了 page_1 表中不再存在的“页面查看次数”列。
   **以下是一个有关如何不中断可视化的示例：**

   1. 在 Report Builder 中，使用“页面”维度和“页面查看次数”量度，创建具有一个请求的工作簿。
   1. [计划此请求](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463)以将其发布到 Power BI。
   1. 在 Power BI 中，为页面和页面查看次数创建可视化。
   1. 现在编辑 Report Builder 中的工作簿，在保留“页面”和“页面查看次数”的同时添加“访问”量度。
   1. 编辑涉及更新工作簿的计划，并将请求重新发布到 Power BI。
   1. 在新工作簿发送到 Power BI 之后

      1. 验证它覆盖了首次发布时创建的现有数据集。
      1. 验证 page_1 表已正确地更新了“页面”、“页面查看次数”和“访问次数”列。
      1. 验证您的可视化可以继续正常工作，因为它引用了 page_1 表中依然存在的两个列。


* **案例 2**：您将工作簿的某一部分固定到 Power BI 中的功能板，随后又从工作簿中删除固定的部分（例如一个图表或一个表）。这将中断可视化。

## Change the name of a Power BI report {#section_2E7893A78B914EBFACB2B08CBD9E472E}

默认情况下，将从工作簿文件名填充名称（不含 .xlsx 扩展），但空格由下划线字符替代。

请记住以下事项

* 标签不能是可被误认为行和列地址的字母和数字组合。例如，A100 不能用作标签，因为它是工作表中一个单元格的地址。
* 以下字符不是有效的标签字符：“#”、“@”、“!”、“$”、“^”、“&amp;”、“*”、“`”、“~”、“ ”。它们将由一个下划线字符替代。
* 如果您输入一个无效名称，将显示一则警告消息，并向您推荐一个自动生成的名称。If you click **[!UICONTROL Yes]**, this name will be used. If you click **[!UICONTROL No]**, the Advanced Wizard UI will let you enter the new name.

