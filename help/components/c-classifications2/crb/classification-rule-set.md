---
description: 规则集是特定变量的一组分类规则。您可将变量应用到规则集。如果您要为一个变量创建多个规则集，则必须将每个规则集应用到多个报表包。
subtopic: Classifications
title: 分类规则集
topic: Admin tools
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 分类规则集

规则集是特定变量的一组分类规则。您可将变量应用到规则集。如果您要为一个变量创建多个规则集，则必须将每个规则集应用到多个报表包。

## 分类规则集

规则集是特定变量的一组分类规则。您可将变量应用到规则集。如果您要为一个变量创建多个规则集，则必须将每个规则集应用到多个报表包。

## 分类规则生成器页面 {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

The following fields and options are available on the [!UICONTROL Classifications Rule Builder].

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/c-classifications2/crb/classification-rule-set.md"  > 添加规则集</a> </p> </td> 
   <td colname="col2"> <p>创建一个规则集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>规则 </p> </td> 
   <td colname="col2"> 显示规则集中包含的规则数量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>状态 </p> </td> 
   <td colname="col2"> 显示规则集的活动状态，如“草稿”或“活动”。活动规则每天进行处理，通常每月检查一次返回的分类数据。规则会自动检查新值，并上载分类。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次更改 </p> </td> 
   <td colname="col2"> 指示规则集的编辑时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>复制 </p> </td> 
   <td colname="col2"> 复制一个规则集，以便可以将该规则集应用到其他变量，或应用到不同报表包中的相同变量。 </td> 
  </tr> 
 </tbody> 
</table>

## 创建分类规则集 {#create-classification-rule-set}

命名分类规则集，应用变量并指定覆盖设置。

1. （入门项目）在 **[!UICONTROL Admin]** >中定义分类结 **[!UICONTROL Report Suites]**&#x200B;构。

   （请参阅“管理工具”帮助中的[分类](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html)，以了解有关添加分类的信息。）

   Variables will display in the [!UICONTROL New Rule Set] panel only after they have at least one classification defined for that variable.

   您可以在> **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Traffic]** (或 **[!UICONTROL Traffic Classifications]** > **[!UICONTROL Conversion]****[!UICONTROL Conversion Classifications]**)中为变量创建分类。 Then select the variable, then click **[!UICONTROL Add Classification]**.

1. To create the rule set, click **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]** > **[!UICONTROL Add Rule Set]**.

   ![](assets/new_rule_set.png)

1. 命名规则集，然后单击 **[!UICONTROL Create Rule Set]**。
1. 选择要编辑的规则集。

   ![](assets/classification_rules_page.png)

1. 单击 **[!UICONTROL Select Report Suites and Variables]**.

   报表包和变量列表中填充了可在登录公司的所有报表包中使用的所有分类变量。报表包中的单个变量只能属于一个规则集。

   请参阅&#x200B;*`Variable`*（详细信息位于[分类规则生成器](/help/components/c-classifications2/crb/classification-rule-definitions.md)页面的定义中）。
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. 继续向规则集[添加分类规则](/help/components/c-classifications2/crb/classification-rule-set.md)。
