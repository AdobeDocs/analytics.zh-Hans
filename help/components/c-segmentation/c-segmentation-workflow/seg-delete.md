---
description: 列出了一些在删除区段前需注意的事项。
seo-description: 列出了一些在删除区段前需注意的事项。
seo-title: 删除区段
solution: Analytics
title: 删除区段
topic: 区段
uuid: cb6db ad-f400-4633-900a-8a02 dcccf2 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 删除区段

列出了一些在删除区段前需注意的事项。

当您删除区段时，

* 应用此区段的计划报表和功能板仍可正常使用，即区段或功能板可继续使用删除的区段。
* 编辑具有相同名称的区段时，计划报表不会更新。例如，假定您在不同报表包中有 2 个使用相同名称的区段：

   ![](assets/duplicate_seg_names.png)

   您的书签引用 mainprod 报表包的区段。然后，由于重复您删除该区段。书签将继续运行，仍引用已删除区段的定义。如果更改剩余区段的区段定义以包括卡特琳娜岛和墨西哥的提华纳，则应用于书签的区段将不会发生更改。仍将使用旧定义。要修复此问题，请更新书签以引用新定义。如果不确定书签、功能板或计划报表是否在使用删除的区段，可以更改剩余区段的名称，这样可以更加明确书签是否在使用剩余的区段。

## Edit Embedded Deleted Segments in Ad Hoc Analysis {#section_976D601DBD2244E38B0A0222E31D2610}

“Ad Hoc Analysis”功能现在允许您在[计算量度生成器](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/)内编辑嵌入式已删除的区段，并且允许您对此区段执行“另存为”操作。

但是，引用这个已删除区段的其他所有已删除区段都将保持不变。
