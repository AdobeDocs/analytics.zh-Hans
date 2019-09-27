---
description: 您无需在每次跟踪代码变更时维护并上载分类，您可以创建自动、基于规则的分类并将这些分类应用在多个报表包中。根据分类相关的流量数目，定期处理规则。
seo-description: 您无需在每次跟踪代码变更时维护并上载分类，您可以创建自动、基于规则的分类并将这些分类应用在多个报表包中。根据分类相关的流量数目，定期处理规则。
seo-title: 分类规则生成器工作流程
solution: Analytics
subtopic: 分类
title: 分类规则生成器工作流程
topic: 管理工具
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 分类规则生成器工作流程

您无需在每次跟踪代码变更时维护并上载分类，您可以创建自动、基于规则的分类并将这些分类应用在多个报表包中。根据分类相关的流量数目，定期处理规则。

## 重要注意事项

在开始使用分类规则之前，请牢记以下几点：

* 我们现有的分类系统一次只能导出1000万行。
* 当分类规则构建器(CRB)请求导出时，它会同时提取已分类的AND未分类的值，并且未分类的值在导出结束时会到达。 这意味着，随着时间的推移，你可以填充1000万个分类值，而不会达到未分类的值。
* 由于架构的设置方式是CRB可从“n”个服务器中提取，因此，这可能导致在哪些服务器被选取以及按什么顺序被选取时出现不一致。 因此，很难获得非分类的价值。

对于维 **度的分类值** 1000万以上的用户，这是解决方法：您需要通过FTP以1000万个批次导出未分类的值，并手动对它们进行分类。

## 分类规则快速入门 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理员]** &gt;分 **[!UICONTROL 类规则生成器]**

以下是您为实施分类规则而采取的高级步骤：

| 步骤 | 执行位置 | 描述 |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL 管理员] &gt;报 [!UICONTROL 表包] &gt;编辑设置  &gt; &lt;流量分类或转化分类&gt; | 选择一个变量并定义要用于该变量的分类。<br>变量必须至少创建了一个分类列，才可在规则中使用。<br>在启用分类后，可以使用导入器和规则生成器来分类特定值。 |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL 管理员] &gt; [!UICONTROL 分类规则生成器] &gt; [!UICONTROL 添加规则集] | 规则集是特定变量的一组分类规则。 |
| 第3步：配置报表包和变量。 | [!UICONTROL 分类规则生成器] &gt; &lt;您的规则集&gt; | 将规则集应用于报表包和变量。 |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL 分类规则生成器] &gt; &lt;您的规则集&gt; | 将条件与分类进行匹配，然后指定要为规则采取的操作。熟悉规则处理 [方式中的信息](../../../components/c-classifications2/crb/classification-quickstart-rules.md)。 |
| 第5步：测 [试分类规则集](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | 您将需要通过在草稿模式下编辑规则，来测试规则的有效性。在草稿模式下，规则无法运行。<br>使用正则表达式时，此步 [骤很重要](../../../components/c-classifications2/crb/classification-quickstart-rules.md)。 |
| 第6步：激 [活有效规则](../../../components/c-classifications2/crb/classification-rule-definitions.md)。 | [!DNL Rules Page] | 在规则有效后，激活规则集。如有必要，您可以覆盖现有键值。请参阅 [如何处理规则](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 从规则集中删除不需要的规则。<br>注意：删除规则时不会删除上载的分类数据。See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>Groups with permissions to use the classification import tool can use classification rules. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**其他资源**

**博客**:有关此功能的其他信息，请参阅数字营销博客：基 [于规则的分类](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)。

**视频**:访 [问YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) ，查看“分 [!UICONTROL 类概述] ”视频。
