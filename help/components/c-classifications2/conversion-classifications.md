---
description: 分类用于对值进行分组归类，并按照分组级别进行报告。例如，您可将所有“付费搜索”促销活动归为一个类似于流行音乐术语的类别，并且相对于“实例”（点进次数）等量度，报告该类别的成功以及有关成功事件的转化。
subtopic: Classifications
title: 转化分类
topic: Admin tools
uuid: 4c8726c9-f527-44e1-be01-8c7b3b5c20f0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 转化分类

分类用于对值进行分组归类，并按照分组级别进行报告。例如，您可将所有“付费搜索”促销活动归为一个类似于流行音乐术语的类别，并且相对于“实例”（点进次数）等量度，报告该类别的成功以及有关成功事件的转化。

## 转化分类 {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

分类用于对值进行分组归类，并按照分组级别进行报告。例如，您可将所有“付费搜索”促销活动归为一个类似于&#x200B;*流行音乐术语*&#x200B;的类别，并且相对于“实例”（点进次数）等量度，报告该类别的成功以及有关成功事件的转化。

转化分类可用于分类转化变量。分类后，任何可使用关键数据生成的报表也可通过关联的数据属性来生成。

启用分类后，使用[分类导入器](/help/components/c-classifications2/c-classifications-importer/c-working-with-saint.md)将特定的值指定给相应的分类。

## 转化分类描述 {#section_4A98DD5F5C314B9DAEE710AEE4EE51D4}

<table id="table_0B72C485467348E2A34BF913441F4AF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle">名称</span> </td> 
   <td colname="col2"> 分类名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">启用日期（仅限文本）</span> </td> 
   <td colname="col2"> <p>指出文本分类是否为促销活动变量的一个日期范围。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">选项（仅限文本）</span> </td> 
   <td colname="col2">创建一个适用于此分类的分类值列表。结合使用<span class="wintitle">选项</span>和促销活动变量可在<span class="wintitle">促销活动管理器</span>中为用户提供该分类的一个支持值列表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">数字类型（仅限数值）</span> </td> 
   <td colname="col2">在数值分类中指定数字的类型。相关选项包括<span class="wintitle">数值</span>、<span class="wintitle">百分比</span>和<span class="wintitle">货币</span>。 </td> 
  </tr> 
 </tbody> 
</table>

## 添加转化分类 {#task_D535D09E3EAF4CD1A15A6B93C0BB1BB5}

<!-- 

t_classification_conversion.xml

 -->

描述如何在“管理员”中添加转化分类的步骤。

1. 单击&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**。
1. 选择报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化分类]**。
1. 从&#x200B;**[!UICONTROL 选择分类类型]**&#x200B;下拉列表中，选择要添加分类的变量。

   ![步骤信息](assets/sub_class_create.png)

1. 将鼠标悬停在&#x200B;**[!UICONTROL 编辑分类]**&#x200B;图标上，然后选择&#x200B;**[!UICONTROL 添加分类]**。
1. 在&#x200B;**[!UICONTROL 选择类型]**&#x200B;字段中，选择要添加到变量的分类类型。

   相关选项包括&#x200B;**[!UICONTROL 文本]**&#x200B;和&#x200B;**[!UICONTROL 数值]**。有关分类类型的详细信息，请参阅[关于分类](/help/components/c-classifications2/c-classifications.md)。
1. 在&#x200B;**[!UICONTROL 文本分类]**&#x200B;对话框中，根据需要配置分类。

   有关这些元素的信息，请参阅[转化分类描述](/help/components/c-classifications2/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4)。

1. 在&#x200B;**[!UICONTROL 下拉列表]**&#x200B;对话框中，添加或删除选项。

   添加选项可为此分类创建可用的分类值列表。您可以将此选项和促销活动变量结合使用，在促销活动管理器中为用户提供该分类的一个支持值列表。将它用于此分类维度，其中拥有极少数很少更改或从不更改的允许值。例如，您可能针对以下不同级别的客户忠诚度运行不同的促销活动：银牌客户、金牌客户和白金客户。然后，您可以使用此下拉列表确保只有被接受的值才是那些匹配这三个级别的值。如果任何人试图使用其他的值，则它将被丢弃。
1. 单击&#x200B;**[!UICONTROL 保存]**。

## 删除转化分类 {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

删除不再需要的转化分类。

1. 单击包标题中的&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]**，打开报表包管理器。
1. 选择报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化分类]**。
1. 从&#x200B;**[!UICONTROL 选择分类类型]**&#x200B;下拉列表中，选择要从中删除分类的变量。
1. 将鼠标悬停在&#x200B;**[!UICONTROL 编辑分类]**&#x200B;图标上，然后选择&#x200B;**[!UICONTROL 删除分类]**。
1. 在“删除分类”对话框中，单击&#x200B;**[!UICONTROL 删除]**。
