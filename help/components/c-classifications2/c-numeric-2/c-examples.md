---
description: 为导入数值 2 分类提供指南的示例。
seo-description: 为导入数值 2 分类提供指南的示例。
seo-title: 示例
solution: Analytics
subtopic: 分类
title: 示例
topic: 管理工具
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 示例

为导入数值 2 分类提供指南的示例。

<!-- 

c_example_1__rate.xml

 -->

在此例中，您已在[!UICONTROL 分类
转化]管理器上创建了分类，现在希望导入 1 月的值：

| 键值 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |

In January, Product1 had a cost of 20% of its revenue (shown in `~MyCost^~value~`) and Product2 had a cost of 30% of its revenue. Because you are importing a new row, `~MyCost^~id~` is blank.

## 结果 {#section_E0569289C9B34C479C7D2CD9ECBF866E}

报表输出的示例如下所示：

期间：2010 年 1 月

报表：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| 键值 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |
| 2010/02/01 - 2010/02/28 | revenue | revenue |

在 2 月，用户的 Product1 成本下降到收入的 15%；Product2 的成本下降到收入的 25%。

## 结果 {#section_23DF5353AC1B478C88647F222703352C}

报表输出的示例如下所示：

期间：2010 年 1 月

报表：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

期间：2010 年 2 月

报表：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $15,500.75 | $2325.11 |
| Product2 | $12,300.52 | $3075.13 |

期间：2010 年 1 月 1 日 - 2010 年 2 月 28 日

报表：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $25,500.98 | $4325.16 |
| Product2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

因此，您会导入以下数据：

| 键值 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## 结果 {#section_674B57ADB8284B878F9E670038C31464}

报表输出的示例如下所示：

期间：2010 年 3 月

报表：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $11,023.75 | $3000.00 |
| Product2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

在此示例中，您将 $500 的运费增加到 1 月的 Product1，将 $600 的运费添加到 2 月份。

| 键值 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | revenue | revenue |
| 2010/01/01 - 2010/01/31 | fixed | none |
| 2010/02/01 - 2010/01/31 | revenue | revenue |
| 2010/02/01 - 2010/01/31 | fixed | none |

先前导入的行会有一个 ID，表示这些行不是新的成本。

## 结果 {#section_2096084176614B9AA60F97D5853CB9EA}

报表输出的示例如下所示：

期间：2010 年 1 月

报表：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2500.05 |

>[!NOTE]
>
>此功能供高级用户使用近似值。因此，不应将结果信息视为精确值。

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

该示例的说明如下：

| 键值 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | order |

## 结果 {#section_39E24ECCC3B34C9AADC25572662750E5}

报表输出的示例如下所示：

期间：2010 年 3 月

报表：按页面显示的产品

| 按页面显示的产品 | 订购 | MyCost |
|---|---|---|
| Product1 | 1000 | $1000.00 |
| 首页 | 600 | $600 |
| 购物车 | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| 键值 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | none |
| 2010/03/01 - 2010/03/31 | fixed | none |

## 结果 {#section_7F5F5970077D4E14A5DC91495E23540D}

报表输出的示例如下所示：

期间：2010 年 3 月

报表：按页面显示的产品

| 按页面显示的产品 | 订购 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 首页 | 600 | 0 |
| 购物车 | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

在此例中，您会导入以下数据：

| 键值 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | fixed | revenue |
| 2010/03/01 - 2010/03/31 | fixed | revenue |

## 结果 {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

报表输出的示例如下所示：

期间：2010 年 3 月

报表：按页面显示的产品

| 按页面显示的产品 | 订购 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 首页 | 600 | $1800.00 |
| 购物车 | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

在此例中，您将导入以下文件数据：

| 键值 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | order | revenue |

## 结果 {#section_6E2604D9A3B0455585EFF0F80FF54127}

报表输出的示例如下所示：

期间：2010 年 3 月

报表：按页面显示的产品

| 按页面显示的产品 | 订购 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 首页 | 600 | $1,000.00 |
| 购物车 | 400 | $2,000.00 |

