---
description: 对于每个数值 2 分类，导入和导出文件中都包含六个列。
solution: Analytics
subtopic: Classifications
title: 导入数值 2 分类
topic: Admin tools
uuid: 82a3034c-e002-4991-900f-22dd45d54910
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 导入数值 2 分类

>[!IMPORTANT]
>
>已从代码库中移除了导入数字 2 分类和启用日期的分类的功能。这项更改将随 2019 年 6 月维护版本的发布而生效。如果您的导入文件中包含“数字”或“启用日期”列，则这些单元格会被静默忽略，同时该文件中的任何其他数据均会正常导入。现有的分类仍可以通过标准分类工作流程导出，并将继续在报表中可用。

对于每个数值 2 分类，导入和导出文件中都包含六个列。

以下定义假设您的数值 2 分类名称为 MyCost。

**~MyCost：**&#x200B;行的描述性名称。

**~~MyCost^~id**:用于编辑现有行的ID。 当您添加一个新行时，此栏应为空白。在从分类管理器导出时，系统会自动分配 ID。

**~~MyCost^~value**:行的值。 如果比率列固定不变，则该值为分布于整个区间的单位值。如果比率列为一个事件，则该值为此事件的乘数。该条目不应包含逗号。

**~~MyCost^~period**:此行对应的时间段。 必须包含一个开始日期和一个结束日期，并用短划线分隔。短划线两边必须留有空格。定义应使用如下格式：

YYYY/MM/DD - YYYY/MM/DD

**~~MyCost^~rate**:要乘以“值”列的 [!UICONTROL 事件] 。 有效值为：

* fixed - 用于表示该值就是要分布于整个期间的单位值。
* revenue
* order
* unit
* scopen
* scviews
* instance
* click
* checkout
* scadd
* scremove
* event1
* event2
* 等

**~~MyCost^~Hinge**:用于在细分期间分发值的事件。 This value is often the same as [!UICONTROL ~MyCost^~rate~], unless you are using [!UICONTROL fixed]. The valid values for this column are identical to that of [!UICONTROL ~MyCost^~rate~], with the addition of [!UICONTROL none].
