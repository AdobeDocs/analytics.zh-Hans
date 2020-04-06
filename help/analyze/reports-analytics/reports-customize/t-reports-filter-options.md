---
description: 使用这些过滤器可以限制报表的内容，使其包括或排除与过滤器匹配的行项目。
title: 过滤报表数据
topic: Reports and analytics
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 过滤报表数据 {#concept_09DC5B986A644738B12204DAC76A90E1}

使用这些过滤器可以限制报表的内容，使其包括或排除与过滤器匹配的行项目。

## 简单滤镜 {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](assets/filter.png)

大多数报表中都显示了简单过滤器，您可以利用它快速查找特定的行项目。简单过滤器不使用任何特殊字符，因此 `-, ", ', +` 和其他特殊字符与报表中的文字值相匹配。您可以使用空格查找包含多个术语的行项目。

例如：

```
help search
```

匹配下列页面：

```
help:Search
help:Paid Search Detection
help:Configure paid search detection
help:Search Keywords Report
help:Internal Search Term
```

## 高级过滤器 {#section_E016626C084640E8A066B2FDA5B932BF}

高级过滤器允许您使用一组过滤器来控制搜索范围。 您可以选择匹配所有过滤器或任何过滤器。

![](assets/advanced_filter.png)

**包含**

如果在行项目中的任意位置找到该术语，则匹配。 此操作与简单滤镜相同。

>[!NOTE] 不能在过滤器中使用空格，因为空格是用作搜索内容中的分隔符

**不包含**

如果在行项目中的任何位置都找不到该术语，则匹配。 使用“不包含”，您可以从报表中过滤出“未指定”、“无”、“关键词不可用”以及其他[特殊值](https://marketing.adobe.com/resources/help/zh_CN/reference/none-unspecified-unknown-other.html)。

不包含: `none`

要获得更准确的过滤器，您可以使用高级（特殊字符）过滤器：

* 高级（特殊字符）：`-^none$`
* 高级（特殊字符）：`-"keyword unavailable"`

例如，以下行项目按“不包含”条件筛选，但不按“高级（特殊字符）”条件筛选：

```
help:Rename the None classification key
```

**包含一个**

如果在行项目中找到任何以空格分隔的术语，则匹配。 以下筛选器显示包含“mens”或“sale”的所有页面：

包含一个：`mens sale`

匹配下列页面：

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**等于**

如果整个行项目（包括空格和其他字符）与指定的短语匹配，则匹配。

等于：`mens:desk & travel`

`Mens:Desk & Travel`

**Starts With**

如果行项（包括空格和其他字符）与指定短语开始，则匹配。

开始于：`mens`

匹配下列页面：

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**Ends With**

如果行项目（包括空格和其他字符）以指定的短语结尾，则匹配。

结束于：`jean`

匹配下列页面：

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## 高级（特殊字符）{#section_83DA3B6C23EB4C119DB6D74062DB501D}

高级允许您执行通配符和其他复杂搜索。

| 高级（特殊字符） | 描述 |
|--- |--- |
| `" "` | 匹配确切的短语。 |
| `*` | 通配符，属于贪婪匹配。<br>例如，`r*p` 与“Registration Signup”匹配。 |
| `^` | 开始于. <br>不要在特殊字符与搜索短语之间包括空格。 |
| `$` | 结束于. <br>不要在特殊字符与搜索短语之间包括空格。 |
| `-` | 非. <br>不要在特殊字符与搜索短语之间包括空格。 |
| `|` | 或者，<br>注意：必须在管道字符的两边各包括一个空格，即 `" | "`。 |

## 创建特定于报表的过滤器 {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

描述如何为报告创建过滤器的步骤。

<!-- 

t_reports_filter_specific.xml

 -->

某些报告包含特定于该报告的过滤器。 例如，您可 [!UICONTROL Purchase Conversion Funnel Report] 以通过网页进行筛选。 A允许您 [!UICONTROL Geosegmentation Report] 按地理区域进行筛选。 其他报告具有这些报告特有的其他过滤器。

访问这些过滤器时，您可以看到列表中指定项目的报告量度。

**创建特定于报表的过滤器**

1. 生成报表，如 [!UICONTROL Purchase Report] ( **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Purchase Conversion Funnel]**)。
1. In the report header, click the **[!UICONTROL Filter]** link.
1. 在页面 [!UICONTROL Filter Selector] 上，单击， **[!UICONTROL Apply a Filter]**&#x200B;然后选择筛选器类型。
1. To search for an item, type a character string in the **[!UICONTROL Search]** field.
1. 单击 **[!UICONTROL OK]**.

## 添加关联过滤器 {#task_065042E384DA4BF3864C58AF2B88D6E2}

描述如何添加关联过滤器的步骤。

<!-- 

t_reports_correlation_filter.xml

 -->

某些报表允许您添加自定义关联过滤器。 例如，如果您查看的报表包的“网站区域”与“女性”页面相关联，则可以创建一个筛选器规则，该规则生成一个在“网站区域=女性”时显示最受欢迎页面的报表。 [!UICONTROL Pages Report]

您可以使用任何可用的关联来过滤关联报告中显示的数据。 此处的示例显示如何添加搜索引擎关联过滤器。

**添加关联过滤器**

1. 运行支持关联的报表。（请参阅[运行划分报表](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69)。）
1. In the report header, click the **[!UICONTROL Correlation Filter]** link.
1. 在下 [!UICONTROL Filter Rule Creator]面，选择要与项目关联的类别。
1. 单击 **[!UICONTROL OK.]**
