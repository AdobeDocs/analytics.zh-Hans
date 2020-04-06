---
description: 分类规则会定期查找未分类的术语。 如果找到规则匹配项，则规则会自动将这些术语添加到您的分类数据表。 您还可以使用分类规则覆盖现有键。
subtopic: Classifications
title: 分类规则
topic: Admin tools
uuid: 08685919-216d-448b-b886-3adf5ff5405e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 分类规则

分类规则会定期查找未分类的术语。 如果找到规则匹配项，则规则会自动将这些术语添加到您的分类数据表。 您还可以使用分类规则覆盖现有键。

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

通过规则生成器，您可以创建 *`classification rule set`*，这是一个 *`classification rules`* 列表。规则与您指定的条件匹配，然后执行操作。

分类规则方便：

* **电子邮件** 和展 **示广告**:创建分类规则以对各个展示广告活动进行分组，以便您了解展示广告活动对电子邮件活动的效果。

* **跟踪代码**:创建分类规则以对跟踪代码中从字符串派生的键值进行分类，并将它们与您定义的特定条件相匹配。
* **搜索词**:使用 [常规表达式](/help/components/c-classifications2/crb/classification-quickstart-rules.md) 和通配符可简化搜索词的分类。 例如，如果搜索词包含 *`baseball`*，则可以将 *`Sports League`* 分类设置为 *`MLB`*。

例如，假设电子邮件促销活动 ID 的跟踪代码为：

`em:Summer:2013:Sale`。

您可以在规则集中设置三条规则来识别字符串的各个部分，然后对值进行分类：

| 选择规则类型 | 输入匹配条件 | 设置分类 | 至 |
|---|---|---|---|
| Starts With | em: | Channel | 电子邮件 |
| Ends With | 销售 | 类型 | 销售 |
| 包含 | 2013 | 年 | 2013 |

## 如何处理规则 {#how-rules-are-processed}

有关如何处理分类规则的重要信息。

<!-- 

about_classification_rules.xml

 -->

* [关于规则的重要信息](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [规则何时不对密钥分类？](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [关于规则优先级](/help/components/c-classifications2/crb/classification-quickstart-rules.md)

>[!NOTE] 不支持 [!UICONTROL Rule Builder] 数字2分类。

## 关于规则的重要信息

* 为中 [的分类](https://marketing.adobe.com/resources/help/zh_CN/reference/groups.html) ，指定组权限 [!UICONTROL Admin Tools]。

* **正则表达式**：[分类规则中的正则表达式](/help/components/c-classifications2/crb/classification-quickstart-rules.md)下提供了相关帮助。

* **报表包**:在至少选择一个报表包之前，您无法选择分类。 只有在创建规则集并分配了变量后，才能应用报表包。

   在测试规则集时，请使用报表中的键（要分类的变量）来查看规则集将如何影响它们。 (The [key](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md) is the variable being classified, or the first column in the classification upload table.)

* **规则优先级**:如果键与设置相同分类的多个规则（在列中）相 [!UICONTROL Set Classification] 匹配，则使用与分类匹配的最后一个规则。 See [About Rule Priority](/help/components/c-classifications2/crb/classification-quickstart-rules.md).

* **规则数量限制**:对于可创建的规则数，不存在设置限制。 但是，大量规则可能会影响浏览器性能。
* **处理**:规则会根据与分类相关的流量以频繁的间隔进行处理。

   活动规则每四小时处理一次，通常检查一个月的分类数据。 规则会自动检查新值，并使用导入程序上传分类。

* **覆盖现有分类**：请参阅[规则何时不会对键值进行分类？](/help/components/c-classifications2/crb/classification-quickstart-rules.md)如有必要，您可以使用导入器删除或移除现有分类。

## 规则何时不对密钥分类？

激活规则时，您可以覆盖现有分类。 在以下情况下，分类规则不会在以下情况下对键 [](/help/components/c-classifications2/c-classifications-importer/c-saint-data-files.md)（变量）进行分类：

* 密钥已分类，但您不选择覆盖 [分类](/help/components/c-classifications2/crb/classification-rule-definitions.md)。

   在添加和激活规则 [时](/help/components/c-classifications2/crb/classification-quickstart-rules.md) ，以及激活数据连接器集成时，可以覆盖分类。 (对于数据连接器，规则由开发中心的合作伙伴创建并显示在 [!UICONTROL Classification Rule Builder]中。)

* 在覆盖键时指定的时间段后，即使在启用覆盖分类后，分类的键也不会显示在数 [据中](/help/components/c-classifications2/crb/classification-rule-definitions.md)。
* 在大约一个月前时间范围开始后，没有对键值进行分类，并且键值从未传递到 [!DNL Adobe Analytics]。

   >[!NOTE]
   >
   >在报表中，当存在键值时，分类适用于指定的任何时间范围。报表的日期范围不会影响报表。

![](assets/overwrite_keys.png)

## 分类规则中的正则表达式 {#regex-in-classification-rules}

使用常规表达式将格式一致的字符串值与分类相匹配。 例如，您可以根据跟踪代码中的特定字符创建分类。 您可以匹配特定字符、单词或字符模式。

<!-- 

regex_classification_rules.xml

 -->

* [正则表达式 - 跟踪代码示例](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_2EF7951398EB4C2F8E52CEFAB4032669)
* [常规表达式-对特定字符进行分类](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_5D300C03FA484BADACBFCA983E738ACF)
* [正则表达式 - 匹配不同长度的跟踪代码](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2)
* [正则表达式 -“不包含”示例](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_FCA88A612A4E4B099458E3EF7B60B59C)
* [正则表达式 - 参考表](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716)

>[!NOTE] 作为最佳实践，正则表达式最适合使用分隔符的跟踪代码。

## 正则表达式 - 跟踪代码示例 {#section_2EF7951398EB4C2F8E52CEFAB4032669}

>[!NOTE] 如果跟踪代码采用 URL 编码，它将&#x200B;**不会**&#x200B;由规则生成器分类。

在此示例中，假设您要对以下促销活动 ID 进行分类：

[!UICONTROL Sample Key]: `em:JuneSale:20130601`

您要分类的跟踪代码包含以下部分：

* `em` = 电子邮件
* `JuneSale` = 促销活动名称
* `20130601` = 日期

[!UICONTROL Regular Expression]: `^(.+)\:(.+)\:(.+)$`

常规表达式如何与活动ID关联：

![](assets/regex.png)

[!UICONTROL Match Groups]:显示常规表达式与活动ID字符的对应方式，以便对活动ID中的位置进行分类。

![](assets/regex_tracking_code.png)

此示例说明了促销活动日期 `20140601` 位于第三组 `(.+)` 且由 `$3` 标识的规则。

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| 选择规则类型 | 输入匹配条件 | 设置分类 | 至 |
|---|---|---|---|
| 正则表达式 | &amp;Hat;(.+)\:(.+)\:(.+)$ | 活动日期 | $3 |

**语法**

| 正则表达式 | 字符串或匹配结果 | 对应的匹配组 |
|--- |--- |--- |
| `^(.+)\:(.+)\:(.+)$` | em:JuneSale:20130601 | `$0`：em:JuneSale:20130601  `$1`：em  `$2`：JuneSale  `$3`：20130601 |
| 构建语法 | `^` = 开始此行  () = 将字符分组并让您提取括号中的匹配字符。`(.+)` = 捕获一个 ( . ) 字符，以及再捕获 ( + )  \ = 字符串的开头。`$` = 指示前面的字符（或字符组）位于行的最后。 |

请参 [阅常规表达式-参考表](/help/components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716) ，以了解有关常规表达式中字符的含义的信息。

## 常规表达式-对特定字符进行分类 {#section_5D300C03FA484BADACBFCA983E738ACF}

使用常规表达式的一种方法是将特定字符分为字符串。 例如，假定以下跟踪代码包含两个重要字符：

[!UICONTROL Sample Key]: `4s3234`

* `4` = 品牌名称
* `s` = 标识搜索引擎，例如 Google

![](assets/regex_char_position.png)

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| 选择规则类型 | 输入匹配条件 | 设置分类 | 至 |
|--- |--- |--- |--- |
| 正则表达式 | `^.(s).*$` | 品牌和引擎 | `$0`（为品牌名称和搜索引擎捕获前两个字符。） |
| 正则表达式 | `^.(s).*$` | 搜索引擎 | `$1`（为 Google 捕获第二个字符。） |

## 正则表达式 - 匹配不同长度的跟踪代码 {#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2}

此示例说明了当跟踪代码长度不同时如何识别冒号分隔符之间的特定字符。 Adobe建议对每个跟踪代码使用一个常规表达式。

示例关键值:

* `a:b`
* `a:b:c`
* `a:b:c:d`

**语法**

![](assets/regex_b.png)

![](assets/regex_varying_length.png)

**[!UICONTROL Rule Builder]**

In the [!UICONTROL Rule Builder], configure the rule as follows:

| 选择规则类型 | 输入匹配条件 | 设置分类 | 至 |
|--- |--- |--- |--- |
| 匹配字符串 a:b 的正则表达式 | `^([^\:]+)\:([^\:]+)$` | a | `$1` |
| 匹配字符串 a:b 的正则表达式 | `^([^\:]+)\:([^\:]+)$` | b | `$2` |
| 匹配字符串 a:b:c 的正则表达式 | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | a | `$1` |
| 匹配字符串 a:b:c 的正则表达式 | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | b | `$2` |
| 匹配字符串 a:b:c 的正则表达式 | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | c | `$3` |
| 匹配字符串 a:b:c:d 的正则表达式 | `^([^\:]+)\:([^\:]+)\:([^\:]+)\:([^\:])$` | d | `$4` |

## 正则表达式 -“不包含”示例 {#section_FCA88A612A4E4B099458E3EF7B60B59C}

此示例提供的正则表达式匹配不包含特定字符（在此例中为 `13`）的任意字符串。

正则表达式：

`^(?!.*13.*).*$`

测试字符串：

```
a:b:
a:b:1313
c:d:xoxo
c:d:yoyo
```

匹配结果：

```
a:b:
c:d:xoxo
c:d:yoyo
```

在此结果中，`a:b:1313` 不表示匹配项。

## 正则表达式 - 参考表 {#section_0211DCB1760042099CCD3ED7A665D716}

| 表达式 | 描述 |
|---|---|
| `(?ms)` | 使整个常规表达式与多行输入匹配，从而允许。 通配符与任何换行符匹配 |
| (`?i`) | 使整个正则表达式区分大小写 |
| [`abc`] | 单个字符：a、b 或 c |
| [`^abc`] | 除以下字符外的任意单个字符：a、b 或 c |
| [`a-z`] | a 到 z 之间的任意单个字符 |
| [`a-zA-Z`] | a 到 z 或 A 到 Z 之间的任意单个字符 |
| `^` | 行的开始（匹配行的开始） |
| `$` | 匹配行的结尾（或在结尾新行的前面） |
| `\A` | 字符串的开始 |
| `\z` | 字符串的结尾 |
| `.` | 匹配任意字符（不包括新行） |
| `\s` | 任意空白字符 |
| `\S` | 任意非空白字符 |
| `\d` | 任意数字 |
| `\D` | 任意非数字 |
| `\w` | 任意单词字符（字母、数字、下划线） |
| `\W` | 任意非单词字符 |
| `\b` | 任意单词边界 |
| `(...)` | 捕获包含的任何内容 |
| `(a|b)` | a 或 b |
| `a?` | 零个或一个 a |
| `a*` | 零个或多个 a |
| `a+` | 一个或多个 a |
| `a{3}` | 恰好 3 个 a |
| `a{3,}` | 3 个或更多 a |
| `a{3,6}` | 3 到 6 个 a |

测试正则表达式有效性的一个有用资源是 https://rubular.com/。

## 关于规则优先级

如果一个键与多个规则匹配，并且它设置了列中显示的相同分类列，则 [!UICONTROL Set Classification] 会使用最后一个规则。 因此，您可能希望将规则集中最重要的排在最后一位。

<!-- 

rule_priority.xml

 -->

如果您创建多个不共享同一分类的规则，则处理顺序无关紧要。

搜索词规则示例对运动员的搜索类型进行分类，其后是什么？

| 规则编号 | 规则类型 | 匹配 | 设置分类 | 至 |
|---|---|---|---|---|
| 1 | 包含 | 牛仔 | 搜索类型 | 团队 |
| 2 | 包含 | 幻想 | 搜索类型 | 幻想 |
| 3 | 包含 | Romo | 搜索类型 | 中间接触 |

If a user searches for *`Cowboys fantasy Tony Romo`*, the term *`Player`* is classified, because it matches the last given classification shown in the Set Classification column.

同样，假设您在以下搜索词的集合中设置了两个规则：

| 规则编号 | 规则类型 | 匹配 | 设置分类 | 至 |
|---|---|---|---|---|
| 1 | 包含 | 牛仔 | 城市 | 达拉斯 |
| 2 | 包含 | 野马 | 城市 | 丹佛 |

用户搜索 *`Cowboys vs. Broncos`*。 如果规则生成器发现规则匹配存在冲突，则第二条规则的分类 (Denver) 将应用到此搜索。

## 将分类规则添加到规则集 {#add-classification-to-rule-set}

<!-- 

t_classification_rule.xml

 -->

描述如何添加或编辑分类规则的步骤。

通过将条件与分类匹配并指定操作来添加规则。

>[!NOTE]
>
>在此过程中，必须将规则应用到一个或多个报表包。尽管没有限制，但建议每个规则集的规则数介于500到1000之间。 如果您有100多个规则，请考虑使用子分类来简化 [规则集](/help/components/c-classifications2/c-sub-classifications.md)。

1. [创建分类规则集](/help/components/c-classifications2/crb/classification-rule-set.md)。
1. On the rule set page, click **[!UICONTROL Add Rule]**.

   ![](assets/add_rule.png)

1. Next to **[!UICONTROL Report Suites]**, click **[!UICONTROL Add Suites]** to specify one or more report suites to assign to this rule set.

   此时 **[!UICONTROL Select Report Suites]** 将显示页面。

   >[!NOTE]
   *`only`*&#x200B;仅 () 当满足以下条件时，才会在此页面上显示报表包：>

   * 在中，报表包至少为该变量定义了一个分类 [!UICONTROL Admin Tools]。
   (See *`Variable`* in [Classification Rule Sets](/help/components/c-classifications2/crb/classification-rule-set.md) for an explanation about this prerequisite.)

   * You selected the report suite on the **[!UICONTROL Available Report Suites]** page, which displays after you click [Add Rule Set](/help/components/c-classifications2/crb/classification-rule-set.md) to create the rule set.


1. 指定是否覆盖现有的值：

   | **规则会覆盖任何现有的值** | （默认设置）始终覆盖现有分类密钥，包括通过导入程序(SAINT)上传的分类。 |
   |---|---|
   | **规则仅会覆盖未设置的值** | 仅填充空白（未设置）单元格。 不会更改现有分类。 |

1. [定义一条或多条规则](/help/components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529)。

   ![步骤结果](assets/classification_rules_page.png)

   有关构建规则的示例，请参阅[分类规则生成器](/help/components/c-classifications2/crb/classification-rule-builder.md)和[分类规则中的正则表达式](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。

   >[!NOTE]
   >
   >如果一个键值匹配多条规则，而这些规则设置了相同的分类（在“设置分类”列中），则将使用匹配分类的最后一条规则。请参阅上述&#x200B;**关于规则优先级**，以了解有关对规则进行排序的详细信息。

1. [测试规则集](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。
1. After testing, click **[!UICONTROL Active]** to validate and activate the rule.

   激活规则会自动构建文件并进行上载。

   字段定义：请参阅[分类规则生成器](/help/components/c-classifications2/crb/classification-rule-definitions.md)，以了解此页面上界面选项的完整定义。

## 测试分类规则集

<!-- 

t_classifications_test_rule.xml

 -->

描述如何测试分类规则或规则集的步骤。 运行测试将检查集中的所有规则。

1. [创建分类规则集](/help/components/c-classifications2/crb/classification-rule-set.md)。
1. 在中， [!UICONTROL Classification Rule Builder]单击规则集名称。
1. 确保该规则集已与报表包相关联。
1. On the rule editor, click **[!UICONTROL Test Rule Set]**.

   ![步骤结果](assets/classification_test_rule_set.png)

1. Type or paste test keys in the [!UICONTROL Sample Keys] field.

   示例密钥包括：

   * 跟踪代码
   * 搜索关键字或短语
   See [Regular Expressions in Classification Rules](/help/components/c-classifications2/crb/classification-quickstart-rules.md) for information about testing regular expressions.
1. 单击 **[!UICONTROL Run Test]**.

   Rules that match are displayed in the [!UICONTROL Results] table.
1. (Optional) Click **[!UICONTROL Activate]** to activate the rule, and to overwrite existing classifications.

   请参阅有关使用规则覆盖现有分类的详细信息。

## 验证和激活分类规则

<!-- 

t_validate_rules.xml

 -->

描述如何验证和激活分类规则的步骤。

1. [创建分类规则集](/help/components/c-classifications2/crb/classification-rule-set.md)，然后向规则集中[添加分类规则](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。
1. On the rule editor, click **[!UICONTROL Activate]**.

   ![](assets/overwrite_keys.png)

1. （可选）要覆盖分类，请启用 **[!UICONTROL Overwrite classifications for]***`<selection>`*。

   通过此选项，您可以覆盖受影响密钥的现有分类。

   有关 [此选项的定义](/help/components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529) ，请参阅规则页。
