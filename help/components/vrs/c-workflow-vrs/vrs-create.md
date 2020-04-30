---
description: 在您开始创建虚拟报表包之前，请注意下面一些事项。
keywords: Virtual Report Suite
title: 创建虚拟报表包
topic: Reports and analytics
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 创建虚拟报表包

在您开始创建虚拟报表包之前，请注意下面一些事项。

* 非管理员用户看不到虚拟报表包管理器。
* 无法共享虚拟报表包。可通过群组/权限实现“共享”。
* 在虚拟报表包管理器中，您只能看到自己的虚拟报表包。您需要单击“显示所有”才能看到其他所有人的虚拟报表包。

1. 导航到 **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]**。
1. 单击 **[!UICONTROL Add +]**.

   ![](assets/new_vrs.png)

1. 填写以下字段：

<table id="table_0F85B56480BB46CBA5BE236BBD70156D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> <p>虚拟报表包的名称不会继承父报表包的名称，该名称应当具有独特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 描述 </td> 
   <td colname="col2"> <p>为便于业务用户识别，应添加适当的描述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 标记 </td> 
   <td colname="col2"> <p>您可以添加标记以组织报表包。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 群组  </td> 
   <td colname="col2"> <p>选择您希望对此 VRS 拥有访问权限的权限群组。（您也可以从<span class="ignoretag"><span class="uicontrol">管理员</span> &gt; <span class="uicontrol">用户管理</span> &gt; <span class="uicontrol">群组</span></span>中管理群组权限。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父报表包 </td> 
   <td colname="col2"> <p>此虚拟报表包从中继承以下设置的报表包。大多数服务级别和功能（例如，eVar 设置、处理规则、分类等）都会被继承。要更改 VRS 中的这些继承设置，您必须编辑父报表包（<span class="ignoretag"><span class="uicontrol">管理员</span> &gt; <span class="uicontrol">报表包</span></span>）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时区 </td> 
   <td colname="col2"> <p>选择时区为可选操作。 </p> <p>如果您选择了时区，则该时区会与 VRS 一起保存。如果您没有选择时区，则使用父报表包的时区。 </p> <p>编辑 VRS 时，与 VRS 一起保存的时区将会显示在下拉选择器中。如果 VRS 是在添加时区支持之前创建的，则父报表包的时区将显示在下拉选择器中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 区段 </td> 
   <td colname="col2"> <p>您可以仅添加一个区段，也可以<a href="https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/segmentation-workflow/seg-build.html"  >堆叠区段</a>。 </p> <p> <p>注意：堆叠两个区段时，将使用 AND 语句联接它们。无法更改为 OR 语句。 </p> </p> <p>当您尝试删除或修改虚拟报表包中当前使用的某个区段时，会显示一条警告。 </p> </td> 
  </tr> 
 </tbody> 
</table>

