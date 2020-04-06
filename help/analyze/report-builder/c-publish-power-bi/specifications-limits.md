---
description: 'null'
title: 限制和规范
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 限制和规范

## Power BI 发布限制 {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE] 这些限制仅适用于选项“作为 Power BI 数据集表发布 Report Builder 请求”。

* 每个工作簿最多可将100个Report Builder请求导出到Power BI。
* 当到达第101个请求时，计划进程将停止导出请求。
* 每个Report Builder请求仅向Power BI发送前10,000行Analytics数据。 其余行将被忽略。

## 在发布到 Power BI 之后编辑 Report Builder 请求 {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE] 此规范适用于选项“作为 Power BI 数据集表发布所有 Report Builder 请求”和“作为 Power BI 数据集表发布工作簿中所有带格式的表”。

在将Report Builder请求发布到Power BI后编辑该请求可能会导致问题。

* **案例1**:您将工作簿发布到Power BI，并根据其数据创建可视化。 然后，您对工作簿进行更改，导致其引用的数据集的某列消失。 然后重新发布。 这将打破Power BI中的可视化。

   **以下是可视化WILL如何中断的示例：**

   1. 在Report Builder中，使用页面维度和页面视图量度创建一个包含一个请求的工作簿。
   1. [计划要发布到](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) Power BI的此请求。
   1. 在Power BI中，为页面和页面视图创建可视化。
   1. 现在，通过从请求中删除页面视图，编辑工作簿。
   1. 使用更新的工作簿编辑计划，并将请求重新发布到Power BI。
   1. 将新工作簿发送到Power BI后

      1. 验证它是否覆盖了您首次发布时创建的现有数据集。
      1. 验证page_1表是否已正确更新“页面”和“访问”列。
      1. 验证您的可视化是否已中断，因为它引用了page_1表中不再存在的“页面视图”列。
   **以下是可视化如何不中断的示例：**

   1. 在Report Builder中，使用页面维度和页面视图量度创建一个包含一个请求的工作簿。
   1. [计划要发布到](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section) Power BI的此请求。
   1. 在Power BI中，为页面和页面视图创建可视化。
   1. 现在，在Report Builder中编辑工作簿，在保留页面和页面视图的同时添加访问量度。
   1. 使用更新的工作簿编辑计划，并将请求重新发布到Power BI。
   1. 将新工作簿发送到Power BI后

      1. 验证它是否覆盖了您首次发布时创建的现有数据集。
      1. 验证page_1表是否已正确更新“页面”、“页面视图”和“访问”列。
      1. 验证您的可视化是否继续正常工作，因为它引用了两个仍在page_1表中的列。


* **案例二**:您将工作簿的某个部分固定到Power BI中的仪表板，然后从工作簿中删除该固定的部分（如图表或表）。 这将破坏可视化。

## 更改 Power BI 报表的名称 {#section_2E7893A78B914EBFACB2B08CBD9E472E}

默认情况下，该名称将从工作簿文件名中填充（不带。xlsx扩展名），但空格将替换为下划线字符。

记住

* 标签不能是字母和数字的组合，它们可能被误认为行和列地址。 例如，A100不能是标签，因为它是工作表中单元格的地址。
* 以下字符不是有效的标签字符：&#39;#&#39;, &#39;@&#39;, &#39;!&#39;, &#39;$&#39;, &#39;^&#39;, &#39;&amp;&#39;, &#39;*&#39;, &#39;`&#39;, &#39;~&#39;, &#39;&#39;。 它们将替换为下划线字符。
* 当您输入无效名称时，将显示一条警告消息，提示自动生成的名称。 如果单击 **[!UICONTROL Yes]**，则将使用此名称。 如果单击 **[!UICONTROL No]**，则高级向导UI将允许您输入新名称。

