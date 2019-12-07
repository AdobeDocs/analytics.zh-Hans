---
description: 您无需在每次跟踪代码变更时维护并上载分类，您可以创建自动、基于规则的分类并将这些分类应用在多个报表包中。根据分类相关的流量数目，定期处理规则。
subtopic: Classifications
title: 分类规则生成器工作流程
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 分类规则生成器工作流程

您无需在每次跟踪代码变更时维护并上载分类，您可以创建自动、基于规则的分类并将这些分类应用在多个报表包中。根据分类相关的流量数目，定期处理规则。

## 开始前的重要注意事项

在开始使用分类规则之前，请牢记以下几点：

* 我们当前的分类系统一次最多只能导出 1000 万行数据。
* 当分类规则生成器 (CRB) 请求导出时，它会同时提取已分类和未分类的值，并且未分类的值会在导出结束时完成分类。这意味着，随着时间的推移，您最多可以填充 1000 万个已分类的值，而不会获取未分类的值。
* 由于架构的设置方式是 CRB 可从“n”个服务器中提取值，这可能导致在从哪些服务器提取值以及按什么顺序提取值方面出现不一致。因此，很难获得未分类的值。

对于维度超过 1000 万个已分类值的用户，可使用以下&#x200B;**解决方法**：您需要通过 FTP，以每批 1000 万的数量导出未分类值，然后手动对这些值进行分类。

## 分类规则快速入门 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理员]** &gt; **[!UICONTROL 分类规则生成器]**

下面简要介绍在实施分类规则时所需执行的步骤：

| 步骤 | 执行位置 | 描述 |
|--- |--- |--- |
| 步骤 1（先决条件）：[设置分类架构](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html)。 | [!UICONTROL 管理员] &gt; [!UICONTROL 报表包] &gt; [!UICONTROL 编辑设置] &gt; &lt;流量分类或转化分类&gt; | 选择一个变量并定义要用于该变量的分类。<br>变量必须至少创建了一个分类列，才可在规则中使用。<br>在启用分类后，可以使用导入器和规则生成器来分类特定值。 |
| 步骤 2：[创建规则集](/help/components/c-classifications2/crb/classification-rule-set.md)。 | [!UICONTROL 管理员] &gt; [!UICONTROL 分类规则生成器] &gt; [!UICONTROL 添加规则集] | 规则集是特定变量的一组分类规则。 |
| 步骤 3：配置报表包和变量。 | [!UICONTROL 分类规则生成器] &gt; &lt;您的规则集&gt; | 将规则集应用于报表包和变量。 |
| 步骤 4：[将分类规则添加到规则集](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。 | [!UICONTROL 分类规则生成器] &gt; &lt;您的规则集&gt; | 将条件与分类进行匹配，然后指定要为规则采取的操作。熟悉[如何处理规则](/help/components/c-classifications2/crb/classification-quickstart-rules.md)中的相关信息。 |
| 步骤 5：[测试分类规则集](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。 | [!DNL Testing Page] | 您将需要通过在草稿模式下编辑规则，来测试规则的有效性。在草稿模式下，规则无法运行。<br>使用[正则表达式](/help/components/c-classifications2/crb/classification-quickstart-rules.md)时，此步骤很重要。 |
| 步骤 6：[激活有效规则](/help/components/c-classifications2/crb/classification-rule-definitions.md)。 | [!DNL Rules Page] | 在规则有效后，激活规则集。如有必要，您可以覆盖现有键值。请参阅[如何处理规则](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。 |
| 步骤 7（可选）：[删除不需要的规则](/help/components/c-classifications2/crb/classification-rule-definitions.md)。 | [!DNL Rules Page] | 从规则集中删除不需要的规则。<br>注意：删除规则时不会删除上载的分类数据。如果需要删除分类数据，请参阅[删除分类数据](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md)。 |

>[!NOTE]
>
>有权使用分类导入工具的群组可以使用分类规则。请参阅[如何处理规则](/help/components/c-classifications2/crb/classification-quickstart-rules.md)，以了解重要的处理信息。

**其他资源**

**博客**：如需有关此功能的详细信息，请参阅数字营销博客：[基于规则的分类](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)。

**视频**：访问 [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I)，观看[!UICONTROL 分类概述]视频。
