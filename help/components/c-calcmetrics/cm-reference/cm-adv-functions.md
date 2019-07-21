---
description: 选中“函数”下拉列表中的“显示高级”，可访问这些函数。
seo-description: 选中“函数”下拉列表中的“显示高级”，可访问这些函数。
seo-title: 引用高级函数
title: 引用高级函数
uuid: 7d1071b9-1737-4b7c-b318-87907de5619
translation-type: tm+mt
source-git-commit: ff46935f6ec38c8981e4a1fffdbdc637bdf557db

---


# 参考：高级函数

<!-- 

cm_adv_functions.xml

 -->

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## table 函数与 row 函数 {#section_8977BE40A47E4ED79EB543A9703A4905}

在 table 函数中，输出对于表中的每一行都是相同的。在 row 函数中，输出对于表中的每一行都是不同的。

## Include-Zeros 参数的含义 {#section_C7A2B05929584C65B308FD372CB8E8E3}

它可告知计算中是否包含零。零有时表示“无”，有时又十分重要。

例如，如果您有收入量度，然后又将页面查看次数量度添加到报表中，则您的收入会突然多出一些全部为零的行。您也许不希望这影响到收入列中已有的任何 MEAN、MIN、QUARTILE 等计算。在这种情况下，您需要检查 include-zeros 参数。

另一方面，如果您有两个感兴趣的量度，则因为其中一个量度的某些行是零而说该量度具有更高的平均值或最小值，这是不合理的，因此，在这种情况下，您不需要检查参数是否包含零。

## 和 {#concept_E14513FE464F4491AD0D4130D4EE621C}

返回其参数的值。使用 NOT 确保值不等于某一特定值。

>[!NOTE]
>
>0(零)表示虚假，任何其他值为True。

```
AND(logical_test1,[logical_test2],...)
```

| 参数 | 描述 |
|---|---|
| *logical_test1* | 必选。任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *logical_test2* | 可选。您希望计算为 TRUE 或 FALSE 的其他条件 |

## 非重复近似计数（维度）{#concept_000776E4FA66461EBA79910B7558D5D7}

返回适用于所选维度的维度项目的非重复近似计数。该函数使用非重复近似计数的 HyperLogLog (HLL) 方法。该函数已配置为保证该值在 95% 的实际值的 5% 以内。

```
Approximate Count Distinct (dimension)
```

| 参数 |  |
|---|---|
| *维度* | 您想要的非重复近似项目计数的维度 |

## 用例示例 {#section_424E3FC5092948F0A9D655F6CCBA0312}

Approximate Count Distinct (customer ID eVar) 是此函数的常见用例。

新“近似客户”计算度量的定义：

![](assets/approx-count-distinct.png)

以下表示在报告中使用“近似客户”度量的方式：

![](assets/approx-customers.png)

## 超出的独特数 {#section_9C583858A9F94FF7BA054D1043194BAA}

Count()、RowCount() 和 Approximate Count Distinct() 会受到[“超出的独特数”限制](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html)的约束。如果维度在特定月份内达到“超出的独特数”限制，则该值将计数为 1 个维度项目。

## 比较计数函数 {#section_440FB8FB44374459B2C6AE2DA504FC0B}

Approximate Count Distinct() 是对 Count() 和 RowCount() 函数所做出的改进，因为创建的度量可用于任何维度报表，以呈现单独维度项目的近似计数。例如，“移动设备类型”报表中使用的客户 ID 计数。

由于 Approximate Count Distinct() 使用了 HLL 方法，而 Count() 和 RowCount() 属于精确计数，因而此函数的准确性要略小于 Count() 和 RowCount()。

## 反余弦 (Row) {#concept_1DA3404F3DDE4C6BAF3DBDD655D79C7B}

返回某量度的反余弦。反余弦是一个其余弦为数字的角。返回的角为范围在 0（零）到 pi 之间的弧度。如果要将结果从弧度转换为角度，请将其乘以 180/PI( )。

```
ACOS(metric)
```

| 参数 |  |
|---|---|
| *metric* | 所需角的余弦，其范围介于 -1 到 1 之间。 |

## 反正弦 (Row) {#concept_90F00DEC46BA47F8A21493647D9668CD}

返回某数字的反正弦。反正弦是一个其正弦为数字的角。返回的角为范围在 -pi/2 到 pi/2 之间的弧度。要以角度表示反正弦，请将结果乘以 180/PI( )。

```
ASIN(metric) 
```

| 参数 |  |
|---|---|
| *metric* | 所需角的余弦，其范围介于 -1 到 1 之间。 |

## 反正切 (Row) {#concept_3408520673774A10998E9BD8B909E90C}

返回某数字的反正切。反正切是一个其正切为数字的角。返回的角为范围在 -pi/2 到 pi/2 之间的弧度。要以角度表示反正切，请将结果乘以 180/PI( )。

```
ATAN(metric)
```

| 参数 |  |
|---|---|
| *metric* | 所需角的余弦，其范围介于 -1 到 1 之间。 |

## 指数回归：预测的 Y (Row) {#concept_25615693312B4A7AB09A2921083502AD}

计算预测的 Y 值 (metric_Y)，假定已知的 X 值 (metric_X) 使用“最小二乘法”计算基于  ) 的最佳拟合直线。

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## Cdf-T {#concept_4E2F2673532A48B5AF786521DE428A66}

返回在 n 自由度的学生 t 分布下，其 Z 分数小于 x 的值的百分比。

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z {#concept_99C97ACC40A94FADBCF7393A17BC2D12}

返回在正态分布下，其 Z 分数小于 x 的值的百分比。

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## 向上取整 (Row) {#concept_A14CDB1E419B4AA18D335E5BA2548346}

返回不小于给定值的最小整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 CEILING(*Revenue*) 可将收入向上舍入为最接近的美元数 $570。

```
CEILING(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 要舍入的量度。 |

## 余弦 (Row) {#concept_DD07AA1FB08145DC89B69D704545FD0A}

返回给定角的余弦。如果角以角度表示，则将该角乘以 PI( )/180。

```
COS(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求余弦的弧度角。 |

## 立方根 {#concept_BD93EFA45DF7447A8F839E1CA5B5F795}

返回某数字的正立方根。某数字的立方根是该数字三分之一次幂的值。

```
CBRT(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求立方根的量度。 |

## 累积 {#concept_3D3347797B6344CE88B394C3E39318ED}

返回最后 N 行的 x 总和（按维度排序，将哈希值用于基于字符串的字段）。

如果 N &lt;= 0，则使用所有之前的行。由于它是按维度排序的，因此它仅对于具有自然顺序的维度（例如日期或路径长度）有用。

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## 累积平均数 {#concept_ABB650962DC64FD58A79C305282D3E61}

返回最后 N 行的平均数。

如果 N &lt;= 0，则使用所有之前的行。由于它是按维度排序的，因此它仅对于具有自然顺序的维度（例如日期或路径长度）有用。

>[!NOTE]
>
>这并不像您对收入/访客之类的速率指标所期望的那样工作：它会降低收入，而不是在最后N的收入上累计收入，并将访客分配给最后N位访客。它使用的是

```
cumul(revenue)/cumul(visitor)
```

## 等于 {#concept_A3B97152B5F74E04A97018B35734BEEB}

返回与某一数字或字符串值完全匹配的项目。

## 指数回归_ 相关系数 (Table) {#concept_C18BBFA43C1A499293290DF49566D8D8}

Returns the correlation coefficient, *r*, between two metric columns ( *metric_A* and *metric_B*) for the regression equation .

```
CORREL.EXP(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 指数回归：截距 (Table) {#concept_0047206C827841AD936A3BE58EEE1514}

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 指数回归：斜率 (Table) {#concept_230991B0371E44308C52853EFA656F04}

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 向下取整 (Row) {#concept_D368150EC3684077B284EE471463FC31}

返回不大于给定值的最大整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 FLOOR(*Revenue*) 可将收入向下舍入为最接近的美元数 $569。

```
FLOOR(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望舍入的量度。 |

## 大于 {#concept_A83734A0C0C14646B76D2CC5E677C644}

返回数字计数大于输入值的项目。

## 大于或等于 {#concept_8CA6DF1F84784D50849BF1C566AE1D37}

返回数字计数大于或等于输入值的项目。

## 双曲余弦 (Row) {#concept_79DD5681CE9640BDBA3C3F527343CA98}

返回某数字的双曲余弦。

```
COSH(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求双曲余弦的弧度角。 |

## 双曲正弦 (Row) {#concept_96230731600C45E3A4E823FE155ABA85}

返回某数字的双曲正弦。

```
SINH(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求双曲正弦的弧度角。 |

## 双曲正切 (Row) {#concept_BD249013732F462B9863629D142BCA6A}

返回某数字的双曲正切。

```
TANH(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求双曲正切的弧度角。 |

## IF (Row) {#concept_6BF0F3EAF3EF42C288AEC9A79806C48E}

IF 函数可在您指定的条件计算为 TRUE 时返回一个值，在该条件计算为 FALSE 时返回另一个值。

```
IF(logical_test, [value_if_true], [value_if_false])
```

| 参数 | 描述 |
|---|---|
| *logical_test* | 必选。任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *[value_if_true]* | 您希望在 *logical_test* 参数计算为 TRUE 时返回的值。（如果未包含此参数，则此参数默认为 0。） |
| *[value_if_false]* | 您希望在 *logical_test* 参数计算为 FALSE 时返回的值。（如果未包含此参数，则此参数默认为 0。） |

## 小于 {#concept_A4A85C0FDF944AACAD4B8B55699D1B11}

返回数字计数小于输入值的项目。

## 小于或等于 {#concept_99D12154DE4848B1B0A6327C4322D288}

返回数字计数小于或等于输入值的项目。

## 线性回归_ 相关系数 {#concept_132AC6B3A55248AA9C002C1FBEB55C60}

Y = a X + b。返回相关系数

## 线性回归_ 截距 {#concept_E44A8D78B802442DB855A07609FC7E99}

Y = a X + b。返回 b。

## 线性回归_ 预测的 Y {#concept_9612B9BF106D4D278648D2DF92E98EFC}

Y = a X + b。返回 Y。

## 线性回归_ 斜率 {#concept_12352982082A4DDF824366B073B4C213}

Y = a X + b。返回 a。

## 以 10 为底的对数 (Row) {#concept_4C65DF9659164261BE52AA5A95FD6BC1}

返回某数字以 10 为底数的对数。

```
LOG10(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求以 10 为底数的对数的正实数。 |

## 对数回归：相关系数 (Table) {#concept_F3EB35016B754E74BE41766E46FDC246}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. 它是使用 CORREL 方程式计算的。

```
CORREL.LOG(metric_X,metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 对数回归：截距 (Table) {#concept_75A3282EDF54417897063DC26D4FA363}

返回截距 *b* 作为最小二乘法回归，它介于回归方程式 *的两个量度列（* metric_X *和* metric_Y[!DNL Y = a ln(X) + b]）之间。它是使用 INTERCEPT 方程式计算的。

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 对数回归：预测的 Y（行）{#concept_5F3A9263BBB84E6098160A4DFB9E3607}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. 该值使用 ESTIMATE 方程式进行计算。

在回归分析中，此函数计算预测的 [!DNL y] 值 (*metric_Y*)，假定已知的 [!DNL x] 值 (*metric_X*) 使用对数计算 [!DNL Y = a ln(X) + b] 的最佳拟合直线。[!DNL a] 值对应每个 x 值，而 [!DNL b] 则是一个常数值。

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 对数回归：斜率 (Table) {#concept_B291EFBE121446A6B3B07B262BBD4EF2}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. 它是使用 SLOPE 方程式计算的。

```
SLOPE.LOG(metric_A, metric_B)
```

| 参数 | 描述 |
|---|---|
| *metric_A* | 您希望指定为因变量数据的量度。 |
| *metric_B* | 您希望指定为自变量数据的量度。 |

## 自然对数 {#concept_D3BE148A9B84412F8CA61734EB35FF9E}

返回某数字的自然对数。自然对数以常数 *e* (2.71828182845904) 为底数。LN 是 EXP 函数的反函数。

```
LN(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求自然对数的正实数。 |

## NOT {#concept_BD954C455A8148A3904A301EC4DC821E}

如果数字为 0，则返回 1；如果为其他数字，则返回 0。

```
NOT(logical)
```

| 参数 | 描述 |
|---|---|
| *logical* | 必选。可被计算为 TRUE 或 FALSE 的值或表达式。 |

使用 NOT 时，需要知道表达式（&lt;、&gt;、=、&lt;&gt; 等）返回值 0 还是 1。

## 不等于 {#concept_EC010B7A9D2049099114A382D662FC16}

返回不包含输入值的完全匹配项的所有项目。

## 或 (Row) {#concept_AF81A33A376C4849A4C14F3A380639D2}

如果有任何参数为 TRUE，则返回 TRUE；如果所有参数均为 FALSE，则返回 FALSE。

>[!NOTE]
>
>0(零)表示虚假，任何其他值为True。

```
OR(logical_test1,[logical_test2],...)
```

| 参数 | 描述 |
|---|---|
| *logical_test1* | 必选。任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *logical_test2* | 可选。您希望计算为 TRUE 或 FALSE 的其他条件 |

## Pi {#concept_41258789660D4A33B5FB86228F12ED9C}

返回常数 PI (3.14159265358979)，精确到 15 位数字。

```
PI()
```

[!DNL PI] 函数没有参数。

## 幂回归：相关系数 (Table) {#concept_91EC2CFB5433494F9E0F4FDD66C63766}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 幂回归：截距 (Table) {#concept_7781C85597D64D578E19B212BDD1764F}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 幂回归：预测的 Y (Row) {#concept_CD652C0A921D4EFBA8F180CB8E486B18}

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 幂回归：斜率 (Table) {#concept_5B9E71B989234694BEB5EEF29148766C}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 二次回归：相关系数 (Table) {#concept_9C9101A456B541E69BA29FCEAC8CD917}

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 二次回归：截距 (Table) {#concept_69DC0FD6D38C40E9876F1FD08EC0E4DE}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 二次回归：预测的 Y (Row) {#concept_2F1ED70B1BDE4664A61CC09D30C39CBB}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| 参数 | 描述 |
|---|---|
| *metric_A* | 您希望指定为因变量数据的量度。 |
| *metric_B* | 您希望指定为因变量数据的量度。 |

## 二次回归：斜率 (Table) {#concept_0023321DA8E84E6D9BCB06883CA41645}

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 倒数回归：相关系数 (Table) {#concept_EBEC509A19164B8AB2DBDED62F4BA2A5}

返回相关系数 *r*，它介于 *的两个量度列（* metric_X *和* metric_Y[!DNL Y = a/X+b]）之间。

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 倒数回归：截距 (Table) {#concept_2DA45B5C69F140EC987649D2C88F19B3}

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 倒数回归：预测的 Y (Row) {#concept_2CF4B8F417A84FE98050FE488E227DF8}

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 倒数回归：斜率 (Table) {#concept_8A8B68C9728E42A6BFDC6BD5CBDCCEC5}

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为相关数据的量度。 |
| *metric_Y* | 要指定为独立数据的量度。 |

## 正弦 (Row) {#concept_21C8C3AA835947A28B53A4E756A7451E}

返回给定角的正弦。如果角以角度表示，则将该角乘以 PI( )/180。

```
SIN(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求正弦的弧度角。 |

## T 分数 {#concept_80D2B4CED3D0426896B2412B4FC73BF7}

Z 分数的别名，即由平均值偏差除以标准偏差

## T 测试 {#concept_A1F78F4A765348E38DBCAD2E8F638EB5}

通过 col 的 t 分数和 n 自由度，执行以 m 结尾的 t 测试。

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

其中，`m` 为尾数，`n` 为自由度。这些应为数字（整个报表的常量，即不按行发生变化）。

`X` 为 t 测试统计数据，通常是基于量度的公式（例如 zscore），每行都将对其进行评估。

返回值是指在给定自由度和尾数的情况下，获得测试统计数据 x 的几率。

**示例：**

1. 使用它查找异常值：

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## 正切 {#concept_C25E00CB17054263AB0460D9EF94A700}

返回给定角的正切。如果角以角度表示，则将该角乘以 PI( )/180。

```
TAN (metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求正切的弧度角。 |

## Z 分数 (Row) {#concept_96BEAC79476C49B899DB7E193A5E7ADD}

返回基于正态分布的 Z 分数，或正态分数。Z 分数是一个标准偏差数，观测分数来自平均值。Z 分数为 0（零）表示分数与平均值相同。Z 分数可以为正数或负数，用于指示该分数在平均值之上还是之下，以及依据多少个标准偏差。

Z 分数的方程式为：

![](assets/z_score.png)

其中，[!DNL x] 为原始分数，[!DNL μ] 为群体平均值，[!DNL σ] 为群体标准偏差。

>[!NOTE]
>
>[!DNL μ] (mu)和[!DNL σ] (sigma)会根据量度自动计算。

Z得分(指标)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> <p> 返回其首个非零参数的值。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Z 测试 {#concept_2A4ADD6B3AEB4A2E8465F527FAFC4C23}

通过 A 的 Z 分数，执行以 n 结尾的 Z 测试。

返回当前行在列中偶然可见的几率。

>[!NOTE]
>
>假定这些值通常是分布的。

