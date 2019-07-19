---
description: 计算量度生成器允许您将统计和数学函数应用于生成高级计算量度。
seo-description: 计算量度生成器允许您将统计和数学函数应用于生成高级计算量度。
seo-title: 参考基本函数
title: 参考基本函数
uuid: 5c2b4a0e-613c-4b27-95b8-01d480aab78
translation-type: tm+mt
source-git-commit: a4ccd3503d9d8e5e5367bb1ebd149262c5cb925a

---


# 参考：基本函数

<!-- 

cm_functions.xml

 -->

计算量度生成器允许您将统计和数学函数应用于生成高级计算量度。

这里有一个按字母顺序排列的函数及其定义列表。

>[!NOTE]
>
>Where [!DNL metric] is identified as an argument in a function, other expressions of metrics are also allowed. For example, [!DNL MAXV(metrics)] also allows for [!DNL MAXV(PageViews + Visits).]

## table 函数与 row 函数 {#section_8977BE40A47E4ED79EB543A9703A4905}

在 table 函数中，输出对于表中的每一行都是相同的。在 row 函数中，输出对于表中的每一行都是不同的。

## 绝对值 (Row) {#concept_4CC47884F7CA49D5B84AC898EA596673}

返回某数字的绝对值。某数字的绝对值是一个具有正值的数字。

```
ABS(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求绝对值的量度。 |

## 列最大值 {#concept_B25518D717D24F82B65CDE49A153D3A3}

返回某量度列的一组维度元素中的最大值。MAXV 可以在一个列（量度）内跨维度元素垂直估值。

```
MAXV(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望计算的量度。 |

## 列最小值 {#concept_5B1033F8ACE9485F9AD3CDC0D146391B}

返回某量度列的一组维度元素中的最小值。MINV 可以在一个列（量度）内跨维度元素垂直估值。

```
MINV(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望计算的量度。 |

## 列总和 {#concept_391F04FBC3CC43368CA0C5AACE74D4B1}

添加列中某量度的所有数字值（跨维度元素）。

```
SUM(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求总值或总和的量度。 |

## 计数 (Table) {#concept_2C6ED2B88AB74481BD130969FB071A41}

返回列中某量度的非零值的数量或计数（某个维度内报告的独特元素数）。

```
COUNT(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望计数的量度。 |

## 指数 (Row) {#concept_17554F9D234449FB8DDEE895816B3FF1}

返回 *e* 的给定次幂。常数 *e* 等于 2.71828182845904，它是自然对数的底数。EXP 是 LN 的反函数，LN 是某数字的自然对数。

```
EXP(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 应用于底数 *e* 的指数。 |

## 求幂 {#concept_941578534F1E4583B1BEB067C8113A21}

幂运算符

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)
</pre>

## 平均值 (Table) {#concept_F4FF950580304D0B99DA7FBB5DB8730A}

返回列中某量度的算术平均值或平均数。

```
MEAN(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求平均数的量度。 |

## 中间值 (Table) {#concept_183EC31208524EDB8463D986DE2E895F}

返回列中某量度的中间值。中间值是指位于一组数字正中间的那个数字，也就是说有一半数字的值大于或等于该中间值，还有一半数字的值小于或等于该中间值。

```
MEDIAN(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求中间值的量度。 |

## 取模 {#concept_DE0825D7A51643219CB01F59667EA352}

使用欧几里得除法求得 col1 / col2 的余数。

返回 x 除以 y 之后的余数。

```
x = floor(x/y) + modulo(x,y)
```

返回值具有与输入值相同的符号（或为零）。

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

要始终获得正数，请使用

```
modulo(modulo(x,y)+y,y)
```

## 百分位数 (Table) {#concept_51DF57B606D14F898E5010DBA61CA979}

返回某量度的 k-th 百分位数形式的值。您可以使用此函数确立一个接受阈值。例如，您可以决定检查得分高于90%的维度元素。

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> 用于定义相对位置的量度列。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> 介于 0 到 100 之间（包括 0 和 100）的百分位数值。 </td> 
  </tr> 
 </tbody> 
</table>

## 四分位数 (Table) {#concept_BFD37F0F23A24AD181407142233FA151}

返回某量度的四分位数形式的值。例如，四分位数可用于查找在获得的收入方面排名前 25% 的产品。当 quart 分别等于 0（零）、2 和 4 时，MINV、MEDIAN 和 MAXV 可返回与 QUARTILE 相同的值。

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> 您希望求四分位数值的量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> 指示要返回哪个*值。 </td> 
  </tr> 
 </tbody> 
</table>

*如果 *quart* = 0，则 QUARTILE 返回最小值。If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). 如果 *quart* = 4，则 QUARTILE 返回最大值。

## 轮次 {#concept_2F12F2A6ACD445A0A8FF648AE4D4CB9E}

返回给定值的最接近整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 Round(*Revenue*) 可将收入四舍五入为最接近的美元数 $569。报告 $569.51 的产品将四舍五入为最接近的美元数 $570。

```
ROUND(metric)
```

| 参数 | 描述 |
|---|---|
| *number* | 您希望舍入的量度。 |

在没有位数参数的情况下四舍五入，与在位数参数为 0 的情况下四舍五入是相同的，都会四舍五入为最接近的整数。使用位数参数，可在小数点右侧返回多位数字。如果位数为负，则在小数点左侧返回 0。

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## 行计数 {#concept_0DBF5995881C47CF95F793125F3A0E2B}

返回给定列的行计数（一个维度中报告的独特元素计数）。将“超出的独特数”计为 1。

## 行最大值 {#concept_984D045D7EDD4A1ABED454CDF2EC23C5}

每行列数的最大值。

## 行最小值 {#concept_A6FB9E72C70A43D0B31565E70B8122BD}

每行列数的最小值。

## 行总和 {#concept_E9EAB0FC5233498F907E7A078698A98E}

每行列数的总值。

## 平方根 (Row) {#concept_6460DFA51EC24527A2317970FB76D404}

返回某数字的正平方根。某数字的平方根是该数字二分之一次幂的值。

```
SQRT(metric)
```

| 参数 | 描述 |
|---|---|
| *number* | 您希望求平方根的量度。 |

## 标准偏差 (Table) {#concept_A383A8BCC6FA42D7B73F7C83997D782A}

基于数据的抽样群体，返回变量的标准偏差或平方根。

STDEV 的方程式为：

![](assets/std_dev.png)

其中，x 为抽样平均值 (*metric*)，*n* 为抽样大小。

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> 参数</b> </td> 
   <td> <b> 描述</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> 您希望求标准偏差的量度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 变量 (Table) {#concept_269751EDC5A34E689112AE16E04A11B0}

基于数据的抽样群体返回变量。

VARIANCE 的方程式为：

![](assets/variance_eq.png)

其中，x 为抽样平均值 MEAN(*metric*)，*n* 为抽样大小。

```
VARIANCE(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求变量的量度。 |

为了计算变量，需要查看整列数字。首先，从该数字列表计算平均值。得出平均值后，浏览每个条目，然后执行以下操作：

1. 从数字中减去平均值。

2. 获得结果。

3. 将其添加到总计。

对整列进行迭代后，您将得到一个总数。然后，将该总数除以列中的项目数。得出的数值就是列变量。它是单个数字。但它会显示为一列数字。

例如，假定有一列，其中包含三个项目：

1

2

3

此列的平均值为 2。列的方差将为((-2)²+(2-2)²+(-2)²/=2/3。在 Ad Hoc Analysis 中，它将显示如下：

1 2/3

2 2/3

3 2/3
