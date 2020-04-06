---
description: 提供有关导入数字2分类的指导的示例。
subtopic: Classifications
title: 示例
topic: Admin tools
uuid: 0553d07f-87c1-4372-90ce-7118a6393a01
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 示例

提供有关导入数字2分类的指导的示例。

<!-- 

c_example_1__rate.xml

 -->

在这种情况下，您为管理者创建了分 [!UICONTROL Classification Conversion] 类，并要导入January值：

| 键 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` |  | `.2` |
| Product2 | Text2 | `Cost2_jan_var` |  | `.3` |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | 收入 | 收入 |
| 2010/01/01 - 2010/01/31 | 收入 | 收入 |

在 1 月，Product1 的成本为其收入的 20%（如 `~MyCost^~value~` 中所示）；Product2 的成本为其收入的 30%。由于您正在导入一个新行，因此，`~MyCost^~id~` 为空白。

## 结果 {#section_E0569289C9B34C479C7D2CD9ECBF866E}

此处显示了报表输出示例：

期间：2010年1月

报告：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

<!-- 

c_example_2__rate.xml

 -->

| 键 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product2 | Text2 | `Cost2_jan_var` | 2 | .3 |
| Product1 | Text1 | `Cost1_feb_var` |  | .15 |
| Product2 | Text2 | `Cost2_feb_var` |  | .25 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | 收入 | 收入 |
| 2010/01/01 - 2010/01/31 | 收入 | 收入 |
| 2010/02/01 - 2010/02/28 | 收入 | 收入 |
| 2010/02/01 - 2010/02/28 | 收入 | 收入 |

在 2 月，用户的 Product1 成本下降到收入的 15%；Product2 的成本下降到收入的 25%。

## 结果 {#section_23DF5353AC1B478C88647F222703352C}

此处显示了报表输出示例：

期间：2010年1月

报告：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2000.05 |
| Product2 | $9,000.04 | $2700.01 |

期间：2010年2月

报告：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $15,500.75 | $2325.11 |
| Product2 | $12,300.52 | $3075.13 |

期间：2010年1月1日至2010年2月28日

报告：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $25,500.98 | $4325.16 |
| Product2 | $21,300.56 | $5,775.14 |

<!-- 

c_example_3__fixed.xml

 -->

因此，您应导入以下数据：

| 键 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_jan_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 固定 | 无 |
| 2010/03/01 - 2010/03/31 | 固定 | 无 |

## 结果 {#section_674B57ADB8284B878F9E670038C31464}

此处显示了报表输出示例：

期间：2010年3月

报告：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $11,023.75 | $3000.00 |
| Product2 | $8,000.12 | $2000.00 |

<!-- 

c_example_4__(advanced)_multiple_row_per_time_period.xml

 -->

在此示例中，您在1月份向Product1添加了500美元的运费，在2月份添加了600美元的运费。

| 键 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_jan_var` | 1 | .2 |
| Product1 | Text1 | `Cost2_jan_fixed` |  | 500 |
| Product1 | Text1 | `Cost1_feb_var` | 2 | .15 |
| Product1 | Text1 | `Cost2_feb_fixed` |  | 600 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/01/01 - 2010/01/31 | 收入 | 收入 |
| 2010/01/01 - 2010/01/31 | 固定 | 无 |
| 2010/02/01 - 2010/01/31 | 收入 | 收入 |
| 2010/02/01 - 2010/01/31 | 固定 | 无 |

以前导入的行有一个ID，表示它们不是新成本。

## 结果 {#section_2096084176614B9AA60F97D5853CB9EA}

此处显示了报表输出示例：

期间：2010年1月

报告：产品

| 产品 | 收入 | MyCost |
|---|---|---|
| Product1 | $10,000.23 | $2500.05 |

>[!NOTE] 此功能可为高级用户产生近似值。因此，不应将结果信息视为精确值。

<!-- 

c_example_5__identical_rate_hinge.xml

 -->

以下说明了此示例：

| 键 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_var` |  | 1 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 订购 | 订购 |

## 结果 {#section_39E24ECCC3B34C9AADC25572662750E5}

此处显示了报表输出示例：

期间：2010年3月

报告：产品（按页面）

| 产品（按页面） | 订购 | MyCost |
|---|---|---|
| Product1 | 1000 | $1000.00 |
| 主页 | 600 | $600 |
| 购物车 | 400 | $400 |

<!-- 

c_example_5__fixed_no_hinge.xml

 -->

| 键 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 固定 | 无 |
| 2010/03/01 - 2010/03/31 | 固定 | 无 |

## 结果 {#section_7F5F5970077D4E14A5DC91495E23540D}

此处显示了报表输出示例：

期间：2010年3月

报告：产品（按页面）

| 产品（按页面） | 订购 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 主页 | 600 | 0 |
| 购物车 | 400 | 0 |

<!-- 

c_example_7__fixed_hinge.xml

 -->

在这种情况下，您应导入以下数据：

| 键 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | `Cost1_mar_fixed` |  | 3000.00 |
| Product2 | Text2 | `Cost2_mar_fixed` |  | 2000.00 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 固定 | 收入 |
| 2010/03/01 - 2010/03/31 | 固定 | 收入 |

## 结果 {#section_5953BB6FD0CE4EF69D1D60B8B1203431}

此处显示了报表输出示例：

期间：2010年3月

报告：产品（按页面）

| 产品（按页面） | 订购 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 主页 | 600 | $1800.00 |
| 购物车 | 400 | $1200.00 |

<!-- 

c_example_7_continued__different_rate_hinge.xml

 -->

在这种情况下，您将导入以下文件数据：

| 键 | MyText | `~MyCost` | `~MyCost^~id~` | `~MyCost^~value~` |
|---|---|---|---|---|
| Product1 | Text1 | Cost1_mar_fixed |  | 3 |

| `~MyCost^~period~` | `~MyCost^~rate~` | `~MyCost^~hinge~` |
|---|---|---|
| 2010/03/01 - 2010/03/31 | 订购 | 收入 |

## 结果 {#section_6E2604D9A3B0455585EFF0F80FF54127}

此处显示了报表输出示例：

期间：2010年3月

报告：产品（按页面）

| 产品（按页面） | 订购 | MyCost |
|---|---|---|
| Product1 | 1000 | $3000.00 |
| 主页 | 600 | $1,000.00 |
| 购物车 | 400 | $2,000.00 |

