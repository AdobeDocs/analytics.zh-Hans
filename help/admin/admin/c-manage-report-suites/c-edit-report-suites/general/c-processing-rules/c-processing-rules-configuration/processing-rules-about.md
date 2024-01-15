---
description: 使用处理规则可以基于定义的条件对数据进行更改。当属性或值匹配定义的条件时，可以设置和删除值，并可以设置事件。
subtopic: Processing rules
title: 处理规则的工作原理
feature: Processing Rules
role: Admin
exl-id: 9d2d9f2d-1e16-486f-9191-2c43776374da
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 94%

---

# 处理规则的工作原理

使用处理规则可以基于定义的条件对数据进行更改。当属性或值匹配定义的条件时，可以设置和删除值，并可以设置事件。

收集数据时，会对数据应用处理规则，并且规则会应用于通过 AppMeasurement 库和数据插入 API 获得的所有数据。处理规则还应用于完整数据源和日志数据源。这些源包含的数据表示 *`hit`* 或用户采取的某个操作。 处理规则不适用于其他数据源。

## 重要概念 {#section_EB138775E7C64C74B0D1D3213F7A823C}

下表包含在使用处理规则时需要了解的关键概念：

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>概念 </p> </th> 
   <th colname="col2" class="entry"> <p>详细信息 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>规则应用于单个报表包。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> 将处理规则复制到其他报表包 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>处理规则按所列顺序依次应用。 </p> </td> 
   <td colname="col2"> <p>如果某个操作更改了一个值，后续条件将使用这个新值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>处理规则在保存后将被立即应用于报表包。 </p> </td> 
   <td colname="col2"> <p>来自处理规则的更改应在保存后的几分钟内在您的报表包中可见。测试处理规则时，我们建议配置 <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md"> 实时报表</a> ，以便快速查看处理规则的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>处理规则是访问上下文数据变量的唯一途径。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> 将上下文数据变量复制到 eVar</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>处理规则先于 VISTA 规则和营销渠道规则应用。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/technotes/processing-order.md"> 处理顺序 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不能排除点击量。 </p> </td> 
   <td colname="col2"> <p>您可以使用 VISTA 规则排除点击量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>产品字符串、反向链接和用户代理不能改变。 </p> </td> 
   <td colname="col2"> <p>反向链接和用户代理为只读。产品字符串不可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备属性和分类不可用。 </p> </td> 
   <td colname="col2"> <p>移动设备查找先于处理规则发生，但属性在处理规则中不可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果您运行的是 JavaScript AppMeasurement H.25.2 或更早版本，则无法读取查询字符串参数中的 URL 前 255 个字符以外的内容。JavaScript AppMeasurement H.25.3 及更高版本提供了完整的 URL，包括用于处理规则的所有查询字符串参数。 </p> </td> 
   <td colname="col2"> <p>升级到 H.25.3 或更高版本，或者读取来自长 URL 客户端的查询字符串参数，并将值存储在上下文数据变量中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查询字符串值必须以 Unicode 或 UTF-8 编码才能由处理规则读取。 </p> </td> 
   <td colname="col2"> <p>这可能影响使用查询字符串传递的多字节字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>每个报表包都限制在 150 个规则，每个规则 30 条件。 </p> </td> 
   <td colname="col2"> <p>处理规则限制是按报表包划分的，而非按公司划分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>必须设置处理规则，以便在发送数据之前检索上下文数据变量。 </p> </td> 
   <td colname="col2"> <p>在发送服务器调用时会应用处理规则。如果未使用处理规则复制存储在上下文数据变量中的值，则将丢弃这些值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>在 UI 中的值比较区分大小写。 </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md">清除报表中的值</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上下文数据变量名称只能包含字母数字字符、下划线和点。任何其他字符都会被去除。 </p> </td> 
   <td colname="col2"> <p>例如，上下文数据变量 <code> login_page-home</code> 会自动变为 <code> login_pagehome</code>。发送给 <code> login_page-home</code> 变量的所有数据会被分配在 <code> login_pagehome</code> 下。 </p> <p>在“处理规则”界面中无法添加包含不支持的字符的上下文数据变量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>插入符号 (^) 在处理规则系统中是特殊字符。 </p> </td> 
   <td colname="col2"> <p>要匹配单个插入字符，请使用两个插入字符 (^^)。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 处理规则条件 {#section_387390EEE9BA4DA98698522A84326DB4}

“条件”将检查页面变量是否有匹配值或者是否存在值。可以添加多个条件并且可以选择是否必须匹配所有条件。

您可以创建没有任何条件的规则，这样即始终执行定义的操作。

在发生操作之前不会自动检查变量的值。例如，Prop1 包含一个值“something”，eVar1 为空。如果将 Prop1 设置为等于 eVar1，则两个值都将为空。如果需要避免此情况，可添加一个条件来检查是否存在值。

## 处理规则操作 {#section_E2285C9D008442C7BF136E52A9A4CC06}

“操作”设置页面变量、删除页面变量或触发事件。操作还可以关联值使其显示在报表中。

例如，您可以通过关联两个变量来显示 `category:product`。
