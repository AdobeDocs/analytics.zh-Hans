---
description: 使用这些过滤器可以限制报表的内容，使其包括或排除与过滤器匹配的行项目。
title: 过滤报表数据
uuid: b6dcaaf7-61f0-4793-870d-e1d156575d5a
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 232c6f69-40bf-487a-8621-d1d7d633681f
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 97%

---

# 过滤报表数据 {#concept_09DC5B986A644738B12204DAC76A90E1}

{{ra-eol}}

使用这些过滤器可以限制报表的内容，使其包括或排除与过滤器匹配的行项目。

## 简单过滤器 {#section_5C4DE873F8D5484BB77F38A4AEB57B4A}

![](/help/admin/admin/assets/filter.png)

大多数报表中都显示了简单过滤器，您可以利用它快速查找特定的行项目。简单过滤器不使用任何特殊字符，因此 `-, ", ', +` 和其他特殊字符与报表中的文字值相匹配。可以使用空格查找包含多个词语的行项目。

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

使用高级过滤器，您可以通过一组过滤器来控制搜索范围。您可以选择匹配所有过滤器，或者匹配任意过滤器。

![](assets/advanced_filter.png)

**包含**

如果在行项目的任意位置找到了相关词语，则匹配成功。它的操作方式与简单过滤器相同。

>[!NOTE]
>
>不能在过滤器中使用空格，因为空格是用作搜索内容中的分隔符

**不包含**

如果在行项目的所有位置都找不到相关词语，则匹配成功。使用“不包含”，您可以从报表中过滤出“未指定”、“无”、“关键词不可用”以及其他[特殊值](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html)。

不包含: `none`

要获得更精确的过滤器，可使用高级（特殊字符）过滤器：

* 高级（特殊字符）：`-^none$`
* 高级（特殊字符）：`-"keyword unavailable"`

例如，下面的行项目是按照“不包含”条件过滤的，而没有按照“高级（特殊字符）”条件进行过滤：

```
help:Rename the None classification key
```

**包含一个**

如果在行项目中找到用空格分隔的词语中的任何一个，则匹配成功。下面的过滤器显示所有包含“mens”或“sale”的页面。

包含一个：`mens sale`

匹配下列页面：

```
Womens
Mens
Mens:Desk & TravelJewelry & Accessories:Accessories:Hats:Mens
Sale & Values
```

**等于**

如果整个行项目（包括空格和其他字符）与指定的短语匹配，则匹配成功。

等于：`mens:desk & travel`

`Mens:Desk & Travel`

**开头**

如果行项目（包括空格和其他字符）以指定的短语开头，则匹配成功。

开始于：`mens`

匹配下列页面：

```
Mens
Mens:Desk & Travel
Mens:Apparel
Mens Perfume Spray
Mens Hemp/Bamboo Flip Flops
```

**结束**

如果行项目（包括空格和其他字符）以指定的短语结尾，则匹配成功。

结束于：`jean`

匹配下列页面：

```
Bell Bottom Jean
Velvet Dream Skinny Leg Jean
Dark Slimmer Jean
Bling Belt High Waist Jean
Ocean Blue Jean
```

## 高级（特殊字符） {#section_83DA3B6C23EB4C119DB6D74062DB501D}

使用“高级”可以执行通配符和其他复杂的搜索。

| 高级（特殊字符） | 描述 |
|--- |--- |
| `" "` | 匹配确切的短语。 |
| `*` | 通配符，属于贪婪匹配。<br>例如，`r*p` 与“Registration Signup”匹配。 |
| `^` | 开始于。<br>不要在特殊字符与搜索短语之间包括空格。 |
| `$` | 结束于。<br>不要在特殊字符与搜索短语之间包括空格。 |
| `-` | 非。<br>不要在特殊字符与搜索短语之间包括空格。 |
| `|` | 或者，<br>注意：必须在管道字符的两边各包括一个空格，即 `" | "`。 |

## 创建特定于报表的过滤器 {#task_DEBB0632411D4CA8AA0B3BA267A5B35F}

您可以为报表创建过滤器。

<!-- 

t_reports_filter_specific.xml

 -->

某些报表含有该报表特定的过滤器。例如，[!UICONTROL 购买转化漏斗]报表可让您按网页进行过滤。[!UICONTROL 地域划分]报表可让您按地域进行过滤。其他一些报表含有各自特定的过滤器。

访问这些过滤器时，您可以看到列表中指定项目的报表量度。

要创建特定于报表的过滤器，请执行以下操作：

1. 生成一个报表，如[!UICONTROL 购买报表]（**[!UICONTROL 网站量度]** > **[!UICONTROL 购买]** > **[!UICONTROL 购买转化漏斗]**）。
1.  在报表标题中，单击&#x200B;**[!UICONTROL 过滤器]**&#x200B;链接。
1.  在[!UICONTROL 过滤器选择器]页面，单击&#x200B;**[!UICONTROL 应用过滤器]**，然后选择一个过滤器类型。
1.  要搜索项目，请在&#x200B;**[!UICONTROL 搜索]**&#x200B;字段中键入字符串。
1. 单击&#x200B;**[!UICONTROL 确定]**。

## 添加关联过滤器 {#task_065042E384DA4BF3864C58AF2B88D6E2}

<!-- 

t_reports_correlation_filter.xml

 -->

某些报表可让您添加自定义关联过滤器。例如，若您正在查看将“网站区域”与女性产品页面相关联的报表包中的[!UICONTROL 页面报表]，则可创建一个过滤器规则，以生成显示“网站区域 ＝ 女性产品”的最受欢迎页面的报表。

可过滤关联报表（使用任何可用关联）中显示的数据。此示例显示添加搜索引擎关联过滤器的方法。

要添加关联过滤器，请执行以下操作：

1. 运行支持关联的报表。（请参阅[运行划分报表](/help/analyze/reports-analytics/reports-customize/breakdowns.md#task_F685624830E64C829C8BE6435A107F69)。）
1. 在报表标题中，单击&#x200B;**[!UICONTROL 关联过滤器]**&#x200B;链接。
1. 在[!UICONTROL “过滤器规则生成器”]下，选择要与某项目关联的类别。
1. 单击&#x200B;**[!UICONTROL “确定”]**。
