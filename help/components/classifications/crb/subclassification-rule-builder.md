---
description: 将子分类与分类规则生成器一起使用。
title: 子分类和规则生成器
feature: Classifications
exl-id: 745d6149-bcb1-48ad-abbe-63a9d009fa27
TQID: https://experienceleague.adobe.com/Qlqt3scXHVUv6EODq57zzaF2007Vvf5x324CHjrsNE0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 403
ht-degree: 41%

---

# 子分类和规则生成器（旧版）

{{classification-rulebuilder-deprecation}}

如果确保每个子分类都有父值，则可以将分类规则生成器与子分类结合使用。

结合使用分类规则生成器和子分类可以简化分类管理和减少所需的规则数量。 如果您的跟踪代码中包含需要单独分类的代码，您可能需要此功能。

请参阅[子分类](/help/components/classifications/importer/subclassifications.md)，了解子分类的概念信息。

## 示例

假定以下跟踪代码：

`channel:broad_campaign:creative`

使用分类层次结构可以将分类应用到分类（称为 *`sub-classification`*)。 这意味着，您可以使用导入器，就像使用具有多个表的关系数据库一样。 一个表将完整的跟踪代码映射到键，另一个表将这些键映射到其他表。

![](assets/sub_class_table.png)

建立此结构后，可以使用[分类规则生成器](/help/components/classifications/crb/classification-rule-builder.md)上载只更新查找表（上图中的绿色和红色表）的小文件。 然后，您可以使用规则生成器来使主分类表保持最新。

以下任务介绍了如何完成此操作。

## 使用规则生成器设置子分类

描述如何使用规则生成器上载子分类的示例步骤。

1. 在分类管理器中创建分类和子分类。

   示例：

   ![步骤信息](/help/admin/tools/assets/sub_class_create.png)

1. 在[分类规则生成器](/help/components/classifications/crb/classification-rule-builder.md)中，从原始跟踪代码中对子分类键值进行分类。

   可使用正则表达式执行此操作。 在此示例中，要填充&#x200B;*`Broad Campaign code`*&#x200B;的规则将使用此正则表达式：

   | `#` | 规则类型 | 匹配 | 设置分类 | 至 |
   |---|---|---|---|---|
   |   | 正则表达式 | `[^\:]:([^\:]):([^\:])` | 广泛促销活动代码 | `$1` |
   |   | 正则表达式 | `[^\:]:([^\:]):([^\:])` | 创作代码 | `$2` |

   >[!NOTE]
   >
   >此时，您无需填充子分类 *`Campaign Type`* 和 *`Campaign Director`*。

1. 上载仅包含指定子分类的分类文件。

   请参阅[多级别分类](/help/components/classifications/importer/subclassifications.md)。

   示例：

   | 键 | 渠道 | 广泛促销活动代码 | 广泛促销活动代码&amp;Hat；促销活动类型 | 广泛促销活动代码&amp;Hat；促销活动主管 | ... |
   |---|---|---|---|---|---|
   | &#42; |  | 111 | 品牌 | 苏桑 |  |
   | &#42; |  | 222 | 品牌 | 弗兰克 |  |

1. 要维护查找表，请上载一个小文件（如上方所示）。

   例如，当引入新 *`Broad Campaign code`* 时，您需要上载此文件。 此文件将应用于以前分类的值。 同样，如果您创建新的子分类（如&#x200B;*`Creative Theme`*&#x200B;作为&#x200B;*`Creative code`*&#x200B;的子分类），则只上载子分类文件，而不是上载整个分类文件。

   要报告这些子分类，其功能与顶级分类完全相同。 这减少了使用它们所需的管理负担。
