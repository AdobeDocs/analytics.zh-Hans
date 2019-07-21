---
description: 您无需在每次跟踪代码变更时维护并上载分类，您可以创建自动、基于规则的分类并将这些分类应用在多个报表包中。根据分类相关的流量数目，定期处理规则。
seo-description: 您无需在每次跟踪代码变更时维护并上载分类，您可以创建自动、基于规则的分类并将这些分类应用在多个报表包中。根据分类相关的流量数目，定期处理规则。
seo-title: 分类规则生成器工作流程
solution: Analytics
subtopic: 分类
title: 分类规则生成器工作流程
topic: 管理工具
uuid: edb1f07e-fa86-4055-8f4 b-cce2 d370 edbb
translation-type: tm+mt
source-git-commit: e71c24fa4762d7f0bc80fc7133ca1cd79dfaf7c5

---


# 分类规则生成器工作流程

您无需在每次跟踪代码变更时维护并上载分类，您可以创建自动、基于规则的分类并将这些分类应用在多个报表包中。根据分类相关的流量数目，定期处理规则。

## 开始之前重要通知

在开始使用分类规则之前，请牢记这一点：

* 我们当前的分类系统一次只能导出多达10000000行。
* 当分类规则构建器(CRB)请求导出时，它将提取分类和未分类的值，并在导出结束时通过未分类的值进行提取。这意味着，随着时间的推移，您可能会填补10000000个分类的值-而不会获得未分类的值。
* 由于架构是以CRM的“n”服务器为基础设置的，因此这可能会导致哪些服务器被选取并按什么顺序进行选择。因此，很难获得未分类的值。

This is the **workaround** for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.

## 分类规则快速入门 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理员]** &gt; **[!UICONTROL 分类规则生成器]**

下面是执行分类规则所采取的高级步骤：

| 步骤 | 执行位置 | 描述 |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/?f=c_classifications). | [!UICONTROL 管理员] &gt; [!UICONTROL 报表包] &gt; [!UICONTROL 编辑设置] &gt;&lt;流量分类或转换分类&gt; | 选择一个变量并定义要用于该变量的分类。<br>变量必须至少创建了一个分类列，才可在规则中使用。<br>在启用分类后，可以使用导入器和规则生成器来分类特定值。 |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL 管理员] &gt; [!UICONTROL 分类规则生成器] &gt; [!UICONTROL 添加规则集] | 规则集是特定变量的一组分类规则。 |
| 步骤3：配置报表包和变量。 | [!UICONTROL 分类规则生成器] &gt;&lt;您的规则集&gt; | 将规则集应用于报表包和变量。 |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL 分类规则生成器] &gt;&lt;您的规则集&gt; | 将条件与分类进行匹配，然后指定要为规则采取的操作。Be familiar with the information in  [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | 您将需要通过在草稿模式下编辑规则，来测试规则的有效性。在草稿模式下，规则无法运行。<br>此步骤在使用 [正则表达式](../../../components/c-classifications2/crb/classification-quickstart-rules.md)时很重要。 |
| Step 6: [Activate valid rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 在规则有效后，激活规则集。如有必要，您可以覆盖现有键值。请参阅 [如何处理规则](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 从规则集中删除不需要的规则。<br>注意：删除规则时不会删除上载的分类数据。See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>具有使用分类导入工具权限的组可以使用分类规则。See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**其他资源**

**博客**：有关此功能的其他信息，请参阅数字营销博客： [基于规则的分类](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)。

**视频**：访问 [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) 以查看 [!UICONTROL “分类概述] ”视频。
