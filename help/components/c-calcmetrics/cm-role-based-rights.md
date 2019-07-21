---
description: 计算量度权限在管理员级别的用户和非管理员用户之间有所不同。
seo-description: 计算量度权限在管理员级别的用户和非管理员用户之间有所不同。
seo-title: 计算得出的度量基于角色的权限
title: 计算得出的度量基于角色的权限
uuid: 7c14d32d-370c-4afa-8f80-5bdd8fc8fc12ec7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 计算得出的指标：基于角色的权限

计算量度权限在管理员级别的用户和非管理员用户之间有所不同。

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
   <td colname="col02"> 管理员可以创建计算量度，也可以通过创建<a href="https://marketing.adobe.com/resources/help/en_US/reference/groups.html" format="https" scope="external">组</a>来限制用户创建计算量度的权限。 </td> 
   <td colname="col2"> 可与整个公司、用户组和个人用户进行共享。 </td> 
   <td colname="col3"> <span class="keyword"> [！UICCONTROL Reports&amp; Analytics] </span>：可以查看/编辑/删除/etc他们自己以及其他用户的计算量度执行查看/编辑/删除等操作。 <p> <span class="keyword">Ad Hoc Analysis</span> 和 <span class="keyword">Report Builder</span>：可以查看/编辑/删除/等等。他们自己的计算量度以及与他们共享的计算量度执行查看/编辑/删除等操作。 </p> </td> 
   <td colname="col4"> 可以批准计算量度作为规范。 </td> 
   <td colname="col5"> 可以在整个组织内应用任何计算量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>非管理员级别的用户</b> </td> 
   <td colname="col02"> 默认情况下，用户可以创建计算量度。但是，管理员可能会限制此类权限。 </td> 
   <td colname="col2"> 只能与个人用户共享 </td> 
   <td colname="col3"> 只能对他们自己的计算量度执行查看/编辑/删除等操作。 <p>非管理员用户必须具有所有组件事件的访问权限，才能查看共享量度（管理控制台中的权限仍然是必需的）。 </p> <p>如果与非管理员用户共享功能板或计划报表，并且他们没有与其共享的量度，则报表将随应用的量度一起运行（假定他们有权查看事件）。但是，他们将无法查看定义或编辑量度。 </p> </td> 
   <td colname="col4"> 只能使用批准的计算量度，无法将计算量度标记为已批准。 </td> 
   <td colname="col5"> 可以应用他们自己的计算量度以及与他们共享的区段。 </td> 
  </tr> 
 </tbody> 
</table>

