---
description: 分类用于对值进行分组归类，并按照分组级别进行报告。 例如，可将所有付费搜索营销活动归为一个如流行音乐术语的类别，并报告该类别相对于“实例”（点进次数）等指标的成功率以及转化为成功事件的情况。
title: 转化分类
feature: Classifications
role: Admin
exl-id: b4855000-adf3-4e3b-af36-f4803383126d
TQID: https://experienceleague.adobe.com/k8wtT-XfijkEOgPHw4j78mm8Da4BA4V3TVVfW6fpCp4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 526
ht-degree: 74%

---

# 转化分类

分类用于对值进行分组归类，并按照分组级别进行报告。 例如，可将所有[!UICONTROL 付费搜索]营销活动归为一个如&#x200B;*流行音乐术语*&#x200B;的类别，并报告该类别相对于“实例”（点进次数）等指标的成功率以及转化为成功事件的情况。 您最多可以向一个变量添加 255 个分类。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化分类]**

转化分类允许您对转化变量进行分类。 分类后，任何可使用关键数据生成的报告也可通过关联的数据属性来生成。

>[!WARNING]
>
>重命名分类可能会导致在[分类规则生成器](/help/components/classifications/crb/classification-rule-builder.md)中创建的现有规则出现问题。 如果您重命名具有分类规则的分类，请确保您更正了每个规则，使其指向重命名后的分类。

## 转化分类描述

| 元素 | 描述 |
| --- | --- |
| 名称 | 分类名称 |
| 启用日期（仅限文本） | 指出文本分类是否为促销活动变量的一个日期范围。 |
| 选项（仅限文本） | 创建一个适用于此分类的分类值列表。 结合使用选项和促销活动变量可在促销活动管理器中为用户提供该分类的一个支持值列表。 |
| 数字类型（仅限数值） | 在数值分类中指定数字的类型。 相关选项包括数值、百分比和货币。 |

## 添加转化分类

将转化分类添加到“管理”：

1. 单击&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报告包]**。
1. 选择某个报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化分类]**。
1. 从&#x200B;**[!UICONTROL 选择分类类型]**&#x200B;下拉列表中，选择要添加分类的变量。

   ![步骤信息](/help/admin/tools/assets/sub_class_create.png)

1. 将鼠标悬停在&#x200B;**[!UICONTROL 编辑分类]**&#x200B;图标上，然后选择&#x200B;**[!UICONTROL 添加分类]**。
1. 在&#x200B;**[!UICONTROL 文本分类]**&#x200B;对话框中，根据需要配置分类。

1. 在下拉列表对话框中添加或删除选项。

   添加选项将创建一个可用于此分类的分类值列表。 您可以将此选项与促销活动变量一起使用，在促销活动管理器中为用户提供该分类的一个支持值列表。 当分类维度的允许值很少（或永远不会更改）时，可使用此项。 例如，您可能会针对不同级别的客户忠诚度开展不同的营销活动：白银、黄金和白金。 然后，您可以使用下拉列表确保仅接受与您的三个级别匹配的值。 如果任何人尝试使用其他值，则该值会被丢弃。

1. 单击&#x200B;**[!UICONTROL 保存]**。

## 删除转化分类

删除不再需要的转化分类。

1. 单击包标题中的&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 报告包]**，打开报告包管理器。
1. 选择某个报告包。
1. 单击&#x200B;**[!UICONTROL 编辑设置]** > **[!UICONTROL 转化]** > **[!UICONTROL 转化分类]**。
1. 从&#x200B;**[!UICONTROL 选择分类类型]**&#x200B;下拉列表中，选择要从中删除分类的变量。
1. 将鼠标悬停在&#x200B;**[!UICONTROL 编辑分类]**&#x200B;图标上，然后选择&#x200B;**[!UICONTROL 删除分类]**。
1. 在“删除分类”对话框中，单击&#x200B;**[!UICONTROL 删除]**。
