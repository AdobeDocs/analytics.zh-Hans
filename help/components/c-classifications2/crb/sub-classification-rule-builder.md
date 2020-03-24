---
description: 您不能将分类规则构建器与子分类合并。
title: 子分类和规则构建器
translation-type: tm+mt
source-git-commit: 0e97e28ffb2bf94acfb382c3f97ff30b31321467

---


# 子分类和规则构建器

如果确保每个子分类都有父级值，则可以将分类规则构建器与子分类合并。

将分类规则构建器与子分类相结合可以简化分类管理并减少所需的规则数。 如果您的跟踪代码包含要单独分类的代码，您可能希望这样做。

请参阅[子分类](/help/components/c-classifications2/c-sub-classifications.md)，了解子分类的概念信息。

## 示例

假定以下跟踪代码：

`channel:broad_campaign:creative`

使用分类层次结构可以将分类应用到分类（称为 *`sub-classification`*)。 这意味着，您可以像关系数据库一样将导入程序与多个表一起使用。 一个表将完整跟踪代码映射到键，另一个表将这些键映射到其他表。

![](assets/sub_class_table.png)

在具有此结构后，您可以使用“分类规则生成器” [](/help/components/c-classifications2/crb/classification-rule-builder.md) ，上传仅更新查找表的小文件（上图中的绿色和红色表）。 然后，您可以使用规则构建器使主分类表保持最新。

以下任务介绍如何完成此操作。

## 使用规则生成器设置子分类{#task_2D9016D8B4E84DBDAF88555E5369546F}

描述如何使用规则生成器上载子分类的示例步骤。

>[!NOTE]
>
>以下步骤描述如何完成[子分类和规则生成器](/help/components/c-classifications2/crb/sub-classification-rule-builder.md)中所述的用例。

1. 在[分类管理器](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html)中创建分类和子分类。

   示例：

   ![步骤信息](assets/sub_class_create.png)

1. 在[分类规则生成器](/help/components/c-classifications2/crb/classification-rule-builder.md)中，从原始跟踪代码中对子分类键值进行分类。

   使用正则表达式执行此操作。 在此示例中，填充规则将 *`Broad Campaign code`* 使用以下正则表达式：

   | `#` | 规则类型 | 匹配 | 设置分类 | 至 |
   |---|---|---|---|---|
   |  | 正则表达式 | `[^\:]:([^\:]):([^\:]`) | 广泛促销活动代码 | `$1` |
   |  | 正则表达式 | `[^\:]:([^\:]):([^\:]`) | 创作代码 | `$2` |

   >[!NOTE]
   >
   >此时，您无需填充子分类 *`Campaign Type`* 和 *`Campaign Director`*。

1. 上载仅包含指定子分类的分类文件。

   请参阅[多级别分类](/help/components/c-classifications2/c-sub-classifications.md)。

   示例：

   | 键 | Channel | 广泛促销活动代码 | 广泛促销活动代码&amp;Hat;促销活动类型 | 广泛促销活动代码&amp;Hat;促销活动主管 | ... |
   |---|---|---|---|---|---|
   | * |  | 111 | 品牌 | 苏珊娜 |  |
   | * |  | 222 | 品牌 | Frank |  |

1. 要维护查找表，请上载一个小文件（如上方所示）。

   例如，当引入新 *`Broad Campaign code`* 时，您需要上载此文件。此文件将应用于以前分类的值。 同样，如果您创建新的子分类(如的子分类 *`Creative Theme`**`Creative code`*)，则只上传子分类文件，而不上传整个分类文件。

   用于报告这些子分类的功能与顶级分类功能完全相同。 这减少了使用它们所需的管理负担。-->
