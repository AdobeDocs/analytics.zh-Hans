---
description: 'null'
seo-description: 'null'
seo-title: 工作区限制，Analysis Workspace中的已知限制
title: Analysis Workspace中的已知限制
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Analysis Workspace中的已知限制

以下是Analysis Workspace及其相关组件中的已知限制列表：

## 表格

* 将日期范围或度量用作表的行时，无法添加日期比较列。
* 当区段用作表的行时，将禁用从选择创建度量。 此外，“从选择创建量度”不应应用于日期对齐列。
* 细分行的条件格式不能使用自定义范围。
* 当应用行值设置求和计算总计时（通常与静态行项一起使用），表总行数不能趋势化。
* [!UICONTROL 贡献分析] (Contribution Analysis)只能以每 [!UICONTROL 日] 粒度 _运行_。 它不能针对每小 [!UICONTROL 时]、 [!UICONTROL 每周]等数据运行。

## 可视化

* 利用细分的可视化，如 [!UICONTROL Flow]、 [!UICONTROL Flow]、Chootr [!UICONTROL Shitogram]、Chootram [!UICONTROL 等，]不能接受计算指标作为输入。
* [!UICONTROL 流程]:进入／退出维度(如进入页 [!UICONTROL 面])不能在流中使用。
* [!UICONTROL 同期群]:非整数不能用作同期群标准。

## 面板

* 细分比较：如果  在初始放置区中使用区段模板，则不会创建其他所有人区段。

## “组件”&gt;“区段”

* 某些指标和维度不可细分，如 [!UICONTROL 发生次数]、 [!UICONTROL 唯一访客]，等等。
* 如果从Workspace创建区段（而不是从“组件”&gt;“区段”创建区段），则某些组件和运 [!UICONTROL 算符将不可用]。 例如，IP地址。

## “组件”&gt;“计算量度”

* 计算量度不能用于某些可视化。 请参阅上面的“可视化”。
* 计算的度量不能在“归因”面 [!UICONTROL 板中使用] ，因为计算的度量本身可以包括单独的归因模型。
* 如果从Workspace创建了计算量度（而不是从“组件”&gt;“区段”创建），则某些组件和操作符 [!UICONTROL 将不可用]。 例如， [!UICONTROL IP地址]。

## “组件”&gt;“日期范围”

* 自定义日期范围不支 [!UICONTROL 持去年的今天], [!UICONTROL 上个月的这一天]，等等。

## “组件”&gt;“虚拟报告套件”

* 启用报告时间处理后，某些组件不受支持。 有关完整列表，请参阅报 [告时间处理](/help/components/vrs/vrs-report-time-processing.md)。

## “组件”&gt;“报告设置”

* “报告设置”页面上的 [!UICONTROL 某些设置] 不适用。 Analysis Workspace只使用底 [!UICONTROL 部的“语言／货币] /编码”设置：千 [!UICONTROL 位分隔符]、计 [!UICONTROL 划报表编码]、 [!UICONTROL CSV分隔符]。

## 归因 IQ

* 归因IQ中不支持度量的 [!UICONTROL 子集]。 有关完整列表，请参阅归因 [IQ常见问题解答](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md)。
