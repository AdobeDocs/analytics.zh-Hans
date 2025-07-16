---
description: 处理规则简化了数据收集，并在数据被发送到报表时对内容进行管理。
subtopic: Processing rules
title: 处理规则概述
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 3%

---

# 处理规则概述

利用处理规则，可修改在将数据写入报表包之前收集数据的方式。

**[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** >选择报表包> **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 处理规则]**

>[!WARNING]
>
>处理规则直接影响数据收集，如果使用不正确，可能会导致数据丢失。 在生产报表包中启用处理规则以缓解数据质量问题之前，请始终测试开发报表包中的处理规则。

处理规则的两个主要用例包括：

* **使用上下文数据变量实施工作流**：您可以使用[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)来设置键/值对，而不是直接在实施中设置变量。 例如，不要设置：

  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  您可以改为设置：

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```

  然后，您可以在Analytics UI中将上下文数据变量映射到所需的维度和量度。

  与组织中的开发人员通信以在资产上实施Analytics时，使用上下文数据变量可简化通信过程。 开发人员只需实施每个键/值对一次，您作为Analytics管理员可以确保数据能够到达正确的实施变量。

* **在收集数据时对其进行修改**：此用例包含多种应用程序，例如临时修复数据质量或帮助填补实施缺口。 有关更多信息和具体示例，请参阅[处理规则用例](pr-use-cases.md)。

## 权限

默认情况下，产品管理员有权访问处理规则。 您可以向非管理员授予处理规则的访问权限，方法是将这些处理规则包含在产品配置文件中，该产品配置文件包含&#x200B;**[!UICONTROL 处理规则]**&#x200B;权限项。 有关详细信息，请参阅[报表包工具的产品配置文件权限](/help/admin/admin-console/permissions/report-suite-tools.md)。

## 创建或编辑处理规则时的注意事项

创建或编辑处理规则时，请考虑以下事项：

* **可能的空值**：创建规则时，请考虑覆盖值为空的情况。 例如，如果某个规则使用eVar2覆盖eVar1，而eVar2为空，则这两个变量都将被清空。 Adobe建议添加一个条件，以在使用变量值覆盖其他值之前检查该变量值。
* **保存后立即应用**：处理规则在您保存收集的数据时即应用于这些数据。 它们不会追溯应用于已收集的数据。
* **规则内的处理顺序**：如果您有多个处理规则，则其运行的顺序很重要。 确保在多个规则中使用给定变量时，变量应按照正确顺序执行。 如果覆盖规则1中的eVar3，则该原始eVar3值在任何后续规则中均不可用。
* **数据收集管道中的处理顺序**：请参阅[Adobe Analytics中数据的处理顺序](/help/technotes/processing-order.md)，以了解处理规则在整个数据收集管道中的应用位置。
* **编码**：几乎所有情况下都遵循UTF-8编码。
* **区分大小写**：处理规则中的字符串比较不区分大小写。 用于覆盖值的字符串值与直接填充变量的规则相同。
* **单个报表包**：编辑处理规则时，它们只应用于一个报表包。 在报表包管理器中选择多个报表包，可强制选择单个报表包。 创建或编辑所需的处理规则后，您可以[将这些规则复制到其他报表包](pr-copy.md)。
* **无数据排除**：排除数据不是处理规则的预定功能。 考虑在数据收集级别使用[`abort`](/help/implement/vars/config-vars/abort.md)或在收集数据后使用[VISTA规则](/help/technotes/vista.md)。
* **可用变量**：处理规则中并非所有维度和量度都可用。 有关支持的内容的完整列表，请参阅[可用于处理规则的维度和量度](pr-variables.md)。
* **允许的规则数**：每个报表包最多可包含150个规则。 每个规则最多可包含30个条件。

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [使用处理规则将上下文数据变量映射到prop和eVar](https://experienceleague.adobe.com/zh-hans/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
