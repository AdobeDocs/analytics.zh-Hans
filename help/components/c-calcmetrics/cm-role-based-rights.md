---
description: 计算指标权限在管理员级别的用户和非管理员用户之间有所不同。
title: 计算指标：基于角色的权限
uuid: 7c14d32d-370c-4afa-8f80-5bbd8fc12ec7
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '254'
ht-degree: 100%

---

# 计算指标：基于角色的权限

计算指标权限在管理员级别的用户和非管理员用户之间有所不同。

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> 创建 </th> 
   <th colname="col2" class="entry"> 共享 </th> 
   <th colname="col3" class="entry"> 查看/管理 </th> 
   <th colname="col4" class="entry"> 批准 </th> 
   <th colname="col5" class="entry"> 应用 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>管理员级别的用户</b> </td> 
   <td colname="col02"> 管理员可以创建计算指标，也可以通过创建<a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=zh-Hans"  >组</a>来限制用户创建计算指标的权限。 </td> 
   <td colname="col2"> 可与整个公司、用户组和个人用户进行共享。 </td> 
   <td colname="col3"> <span class="keyword">Reports &amp; Analytics</span>：可以对他们自己以及其他用户的计算量度执行查看/编辑/删除等操作。 <p> <span class="keyword">Report Builder</span>：可查看/编辑/删除/等等自身的计算指标和与他共享的计算指标。 </p> </td> 
   <td colname="col4"> 可以批准计算指标作为规范。 </td> 
   <td colname="col5"> 可以在整个组织内应用任何计算指标。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>非管理员级别的用户</b> </td> 
   <td colname="col02"> 默认情况下，用户可以创建计算指标。但是，管理员可能会限制此类权限。 </td> 
   <td colname="col2"> 只能与个人用户共享 </td> 
   <td colname="col3"> 只能对他们自己的计算指标执行查看/编辑/删除等操作。 <p>非管理员用户必须具有所有组件事件的访问权限，才能查看共享指标（管理控制台中的权限仍然是必需的）。 </p> <p>如果与非管理员用户共享功能板或计划报表，并且他们没有与其共享的指标，则报表将随应用的指标一起运行（假定他们有权查看事件）。但是，他们将无法查看定义或编辑指标。 </p> </td> 
   <td colname="col4"> 只能使用批准的计算指标，无法将计算指标标记为已批准。 </td> 
   <td colname="col5"> 可以应用他们自己的计算指标以及与他们共享的区段。 </td> 
  </tr> 
 </tbody> 
</table>
