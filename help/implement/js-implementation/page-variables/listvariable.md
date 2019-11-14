---
description: 页面变量可以直接填充报表，例如 pageName、列表属性、列表变量，等等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 页面变量
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# 列表变量

也称为 List Var（列表变量）。与“列表属性”的功能类似，“列表变量”允许在同一图像请求中包含多个值。它们的作用也与 eVar 类似，可独立于定义它们的图像请求之外存在。您可以使用这些变量来查看单一页面上多个元素（例如，产品列表、请求列表、搜索调整列表或展示广告列表）之间的因果关系。

<!-- 

listN.xml

 -->

**注意事项**

* 列表变量可通过引用访客浏览器中的 VisitorID Cookie，记住其特定值。
* 每个访客每次最多可存储 250 个值。如果超出了每个访客 250 个值的限制，则使用最后的 250 个值。这些值的过期设置取决于为变量配置的过期设置。
* 每一个分隔值可包含最多 255 个字符（如果使用多字节字符，则更少）。这是每个元素的最大长度。
* 此变量内的字符数量没有限制。此限制的唯一例外是在旧版 Internet Explorer 浏览器中，所有 URL 请求均有 2083 字符限制。
* 每个报表包均可使用总共三个列表变量。
* 使用列表变量需要 H23 或更高版本的代码。
* 列表 Var 可进行分类。
* 如果在同一个图像请求中定义了重复值，列表变量会删除这些重复值的所有实例。
* 可划分区段的最详细列表变量是在点击（或页面查看）级别。如果列表变量在同一图像请求中有三个值，则匹配一个值的任何区段规则都会将三个值全部提取到报表中。相反，如果定义的排除规则与单个值匹配，则会全部排除这三个值。

**配置** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

无需 Adobe 客户关怀部门的介入，您就可以在管理控制台中访问并更新配置：

1. 转至 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员]** &gt; **[!UICONTROL 报表包]**
1. 选择报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** &gt; **[!UICONTROL 转化]** &gt; **[!UICONTROL 列表变量]**。

* **名称**：每一个分隔值最多可包含 255 个字符（如果使用多字节字符，则会更少）。这是每个元素的最大长度。
* **值分隔符**：用于在列表变量中分隔值的字符。通常有逗号、冒号、竖线或类似的字符。

   >[!NOTE]
   >
   >列表变量不支持将多字节字符作为分隔符。分隔符必须为单字节。

* **过期日期**：类似于 eVar 过期日期，此设置决定列表变量和转化事件之间可产生关联的时间量。

   * **在页面查看或访问级别**：超出页面查看或访问以外的成功事件不会链接回列表变量内的任何值。
   * **基于时段，如日、周、月等**：超出指定时段以外的成功事件将不会链接回列表变量内的任何值。还可以定义自定义天数。
   * **特定转化事件**：在指定的特定事件后触发的任何其他成功事件将不会链接回列表变量内的任何值。
   * **从不**：列表变量和成功事件之间可以传递的时间量不限。

* **分配**：此设置确定成功事件如何进行计数：

   * **完整**：变量过期前定义的所有变量值获得成功事件的全部计数。
   * **线性**：变量过期前定义的所有变量值获得转化事件的平均计数。
   * 变量值永远不会被覆盖，但会被添加到获得成功事件计数的值。

* **最大值**：指定此列表变量允许的活动值的数量。例如，如果设置为 3，则只保存最后捕获的 3 个值，而之前捕获的任何值都将被丢弃。请注意，如果一次点击时发送同一列表 var 的多个值，同时您又对使用最大值进行了限制，那么每个值的时间戳将相同，且不确定将保存哪个值。

   每个访客每次最多可存储 250 个值。如果超出了每个访客 250 个值的限制，则使用最后的 250 个值。这些值的过期设置取决于为变量配置的过期设置。

   “最大值”设置可用于将属性限制为特定数量的值。例如，如果某个列表 var 在访问的首个页面上设置为“A,B,C”，然后在下一页上设置为“X,Y,Z”，那么属性将根据分配情况分发到这六个值。如果您希望将属性限制为仅“X,Y,Z”，那么可以将最大值设为 3。

要设置或编辑列表变量，请转到 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员]** &gt; **[!UICONTROL 报表包]** &gt; **[!UICONTROL 编辑设置]** &gt; **[!UICONTROL 转化**] &gt; **]列表变量**[!UICONTROL 。

**实施示例** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

以下每一个示例都使用逗号作为值分隔符。

**在列表变量内定义单个值：**

```js
s.list1="Cat";
```

**传入多个值：**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**将收入分配给列表变量：**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

此结果会显示三个行项目，并且每个项目的收入为 50 美元。（顶部横幅广告、侧栏广告和内部促销活动 1。）请注意此报表的总量会删除重复的收入，因此总量也将反映为 50 美元。

**将收入分配给访问期间设置了多次的列表变量：**

**分配**：完整

**过期**：访问

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 页面 </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 页面 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> （未设置） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**结果**：访问期间 list var1 中设置的所有值（value1、value2、value3、value4、value5、value6）获得购买的全部计数。

