---
description: 显示搜索关键词的划分。
seo-description: 显示搜索关键词的划分。
seo-title: 搜索关键词
solution: Analytics
title: 搜索关键词
topic: 报表
uuid: db9d477b-b711-4b93-9c25-3aebis5 f2 ace6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 搜索关键词

显示搜索关键词的划分。

**搜索关键词 - 全部**：显示搜索关键词分类细目，其中包含被用来找到您的网站的每个搜索关键词。可点击列表上方的列标题，按页面查看或搜索关键词对列表排序。点击搜索关键词旁边的放大镜，可查看网站的搜索结果。

**搜索关键词 - 付费**：显示搜索关键词分类细目，其中包含用于查找您的网站的每个付费搜索关键词。可点击列表上方的列标题，按页面查看或搜索关键词对列表排序。点击搜索关键词旁边的放大镜，可查看网站的搜索结果。

**搜索关键词 - 免费**：显示搜索关键词分类细目，其中包含用于查找您的网站的每个免费搜索关键词。可点击列表上方的列标题，按页面查看或搜索关键词对列表排序。点击搜索关键词旁边的放大镜，可查看网站的搜索结果。

>[!IMPORTANT]
>
>对于付费和自然搜索，搜索引擎停止提供(在大多数情况下)作为引介的一部分的搜索关键字。因此，Adobe 始终会将 Google（或 Bing、Yahoo）域分类为搜索。根据反向链接的格式和内容（甚至不含关键词），Adobe 通常可确定它是否为搜索的结果，因此搜索将在没有关键词的情况下进行计数。[更多信息...](https://helpx.adobe.com/analytics/kb/keyword-unavailable.html)

## 分配、过期和特殊值 {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 量度分配 </td> 
   <td colname="col2"> <p>原始值（默认） </p> <p> 可更改为线性。 </p> </td> 
   <td colname="col3"> 最近（可使用量度的线性版本更改为线性） </td> 
   <td colname="col4"> <p>原始值（默认） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值过期时间 </td> 
   <td colname="col2"> 访问 - 可以缩短，但不能加长 </td> 
   <td colname="col3"> 访问 </td> 
   <td colname="col4"> 访问 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 值限制 </td> 
   <td colname="col2"> 无限制（后续版本中或有变更） </td> 
   <td colname="col3"> 无限制（后续版本中或有变更） </td> 
   <td colname="col4"> 无 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 特殊值 </td> 
   <td colname="col2"> <p>“无”：网站范围在访问期间没有关键词的总计。 </p> “关键词不可用”搜索的是从搜索中删除了关键词，并且不发送到数据收集的情况。这种情况一般会在客户登录 Google 帐户时发生。适用于付费和免费搜索。 </td> 
   <td colname="col3"> （低流量）代表超过前 500k 流量的值，而尚未收到可供报告的足够流量。 </td> 
   <td colname="col4"> <p> 空：等于“无”，网站范围内在访问期间没有关键词的总计。 </p> <p>“关键词不可用”搜索的是从搜索中删除了关键词，并且不发送到数据收集的情况。这种情况一般会在客户登录 Google 帐户时发生。适用于付费和免费搜索。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 报表历史记录 {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| 日期 | 更改 |
|---|---|
| 2014 年 1 月 16 日 | Data Warehouse 已更新，以匹配 Marketing Reports &amp; Analytics 所用的逻辑。在此日期之前，搜索关键词在整个访问期间并非持续存在。 |

