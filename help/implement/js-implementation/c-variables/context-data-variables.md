---
description: 使用上下文数据变量可在每个页面上定义能够由处理规则读取的自定义变量。
keywords: Analytics实施；contextData；s. contextData
seo-description: 使用上下文数据变量可在每个页面上定义能够由处理规则读取的自定义变量。
seo-title: 上下文数据变量
solution: Analytics
subtopic: 变量
title: 上下文数据变量
topic: 开发人员和实施
uuid: 4b215803-99d4-46f2-b3 c1-e78558987764
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 上下文数据变量

使用上下文数据变量可在每个页面上定义能够由处理规则读取的自定义变量。

您可以使用通过处理规则映射的上下文数据变量发送数据，而无需在代码中将值明确分配给 prop 和 eVar。处理规则提供强大的图形界面，以便对接收的数据进行更改。根据上下文数据中发送的值，您可以设置事件、将值复制到 eVar 和 prop，以及执行其他条件语句。

>[!NOTE]
>
>上下文数据变量不区分大小写。例如，以下两个变量实际上相同：&gt;
>```>
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>
>
```>
>and 
>
>
```>
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```>



使用上下文数据有助于避免更新代码后支持不同的报表包配置。

例如，可以定义以下&#x200B;*`s.contextData`* 变量：

```
s.contextData['myco.rsid'] = 'value'
```

通过使用处理规则，您可以添加一个条件来查找 `myco.rsid` 上下文数据变量。当找到此变量时，可以添加一个操作将其复制到某个 prop 或 eVar。

此外，还可以在处理规则界面中直接定义上下文数据变量来临时存储值，或收集将在报表包中使用的上下文数据变量的值。例如，如果需要交换两个值，您可以在交换期间创建一个上下文数据变量来存储其中一个值。

由于仅在收集数据时应用处理规则，因此在开始发送上下文数据前设置处理规则非常重要。处理点击时处理规则未读取的上下文数据值都将被丢弃。

## 规则 {#section_2229739F6B1A4C1CAD7140BDF4687523}

<table id="table_4433A32A952340699B189CAEAF158B06"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>规则 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>支持的名称和字符 </p> </td> 
   <td colname="col2"> <p>上下文数据变量名称只能包含字母数字字符、下划线和点。任何其他字符都将被去除。上下文数据变量并非数值型变量，它而是名称型变量。 </p> <p>例如，上下文数据变量 <code>login_page-home</code> 会自动变为 <code>login_pagehome</code>。发送给 <code>login_page-home</code> 变量的所有数据都会被分配在 <code>login_pagehome</code> 下面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>命名空间 </p> </td> 
   <td colname="col2"> <p>有一种妥善的方法是在您的变量前加上您的公司名、网站名或类似值的前缀，以确保此名称在整个报表包中是唯一的名称。 </p> <p>上下文数据变量的命名类似于其他 JavaScript 变量。请注意，命名空间 <code>a.*</code> 为保留的命名空间，供 Adobe 产品在上下文变量名称中使用。例如，用于 iOS 的 AppMeasurement 库使用 <code>a.InstallEvent</code> 来衡量应用程序的安装情况。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Internet Explorer的URL限制 </p> </td> 
   <td colname="col2"> <p>您可能会遇到早期存在于 Internet Explorer 6 和 7 中的 URL 限制，在这种限制中，URL 将于第 2000 个字节的位置被截断。可以使用 <span class="keyword">DigitalPulse</span> 调试器确定 URL 字符串的大小。 </p> <p>得益于 AppMeasurement 近期的更新（2014 年 9 月），Internet Explorer 8 及更高版本采用了 HTTP POST，从而解决了上述截断问题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>支持的 AppMeasurement 版本 </p> </td> 
   <td colname="col2"> <p>上下文数据变量至少需要 H23 代码或更高版本。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 跟踪链接调用时发送上下文数据 {#section_35EBE5D1CF29427598BD4B2165CE64FC}

加入 `ContextData` + 您希望在 `s.linkTrackVars` 中加入的变量的名称：

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## 示例 {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Possible ways to replace implementation of the *`s.pageName`* variable, assuming that processing rules are set up correctly for each:

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

实施上下文数据变量的其他示例：

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

有关示例，请参阅 Analytics 参考中的[将上下文数据变量复制到 eVar](https://marketing.adobe.com/resources/help/en_US/reference/?f=processing_rules_copy_context_data)。
