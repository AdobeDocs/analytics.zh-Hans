---
title: 从Adobe Analytics标记扩展迁移到Web SDK标记扩展
description: 更新您在Adobe Experience Platform数据收集标记上的Analytics实施，以使用Web SDK扩展。
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '1704'
ht-degree: 1%

---

# 从Adobe Analytics标记扩展迁移到Web SDK标记扩展

此实施路径涉及从Adobe Analytics标记扩展迁移到Web SDK标记扩展的方法迁移。 其他实施路径将在单独的页面上介绍：

* [Web SDK JavaScript库AppMeasurement](appmeasurement-to-web-sdk.md)：一种流畅、系统地迁移到Web SDK的方法，只不过它不使用标记。 您而是需要手动删除Adobe Analytics数据收集库(`AppMeasurement.js`)并将其替换为Web SDK JavaScript库(`alloy.js`)。
* [Web SDK标记扩展](web-sdk-tag-extension.md)：全新Web SDK安装，您可以在其中使用Adobe Experience Platform数据收集中的标记管理实施。 它需要Adobe Analytics ExperienceEvent字段组，其中包括要包含在XDM架构中的典型Analytics变量。
* [Web SDK JavaScript库](web-sdk-javascript-library.md)：使用Web SDK JavaScript库的全新Web SDK安装(`alloy.js`)。 自行管理实施，而不是使用标记UI。 它需要Adobe Analytics ExperienceEvent字段组，其中包括要包含在XDM架构中的典型Analytics变量。

## 此实施路径的优缺点

使用此迁移方法既有优点，也有缺点。 仔细权衡每个选项，以确定哪种方法最适合您的组织。

| 优势 | 缺点 |
| --- | --- |
| <ul><li>**您的网站上无代码更改**：由于您的实施已安装标记，因此可以在标记界面中进行所有迁移更新。</li><li>**使用您现有的实施**：此方法不需要全新实施。 虽然它确实需要新的规则操作，但您可以以最小的更改重复使用现有数据元素和规则条件。</li><li>**不需要架构**：对于迁移到Web SDK的这一阶段，您不需要XDM架构。 相反，您可以填充 `data` 对象，可直接将数据发送到Adobe Analytics。 迁移到Web SDK完成后，您可以为组织创建架构，并使用数据流映射填充适用的XDM字段。 如果在迁移过程的此阶段需要架构，则贵组织将被强制使用Adobe Analytics XDM架构。 使用此架构会使贵组织将来更难以使用自己的架构。</li></ul> | <ul><li>**执行技术债务**：由于此方法使用现有实施的修改形式，因此可能更难跟踪实施逻辑并在需要时执行更改。 自定义代码可能特别难以调试。</li><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Customer Journey Analytics时，您必须将数据发送到Adobe Experience Platform中的数据集。 该操作要求 `data` 对象是数据流映射工具中的一个条目，可将其分配给XDM架构字段。 此工作流的映射只需执行一次，并且不涉及对实施进行更改。 但是，这是一个额外的步骤，在XDM对象中发送数据时不需要执行此步骤。</li></ul> |

Adobe建议在以下情况下遵循此实施路径：

* 您已有使用Adobe Analytics标记扩展的实施项目。 如果您有一个使用AppMeasurement的实施，请遵循 [从AppMeasurement迁移到Web SDK](appmeasurement-to-web-sdk.md) 而是。
* 您打算在将来使用Customer Journey Analytics，但不希望从头开始使用Web SDK实施来替换Analytics实施。 在Web SDK上从头开始替代实施需要做出最大努力，但同时需要提供最可行的长期实施架构。 如果贵组织愿意进行干净的Web SDK实施，请参阅 [通过Adobe Experience Platform Web SDK引入数据](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) 《Customer Journey Analytics用户指南》中的。

## 迁移到Web SDK所需的步骤

以下步骤包含要努力实现的具体目标。 单击每个步骤以了解完成该操作的详细说明。

+++**1. 创建和配置数据流**

在Adobe Experience Platform数据收集中创建数据流。 当您将数据发送到此数据流时，它会将数据转发到Adobe Analytics。 将来，同一数据流会将数据转发到Customer Journey Analytics。

1. 导航到 [experience.adobe.com](https://experience.adobe.com) 并使用您的凭据登录。
1. 使用右上角的主页或产品选择器可导航至 **[!UICONTROL 数据收集]**.
1. 在左侧导航中，选择 **[!UICONTROL 数据流]**.
1. 选择&#x200B;**[!UICONTROL 新数据流]**。
1. 输入所需的名称，然后选择 **[!UICONTROL 保存]**.
1. 创建数据流后，选择 **[!UICONTROL 添加服务]**.
1. 在服务下拉菜单中，选择 **[!UICONTROL Adobe Analytics]**.
1. 输入与您当前将分析数据发送到的网站相同的报表包ID。 单击&#x200B;**[!UICONTROL 保存]**。

![添加Adobe Analytics服务](assets/datastream-rsid.png) {style="border:1px solid gray"}

您的数据流现在可以接收数据并传递给Adobe Analytics。

+++

+++**2. 将Web SDK扩展添加到您的标记属性中**

此部分将为您准备标记，以便进行下一步中的大量迁移工作。

1. 单击Adobe Experience Platform界面左上角的汉堡图标，然后选择 **[!UICONTROL 标记]**.
1. 选择所需的标记属性。
1. 在标记属性的左侧导航中，选择 **[!UICONTROL 扩展]**.
1. 选择 **[!UICONTROL 目录]** 在顶部附近，可查看所有可用扩展的列表。
1. 搜索并选择 **[!UICONTROL Adobe Experience Platform Web SDK]** 扩展，然后单击 **[!UICONTROL 安装]** 在右边。

   ![目录](assets/catalog.png) {style="border:1px solid gray"}

1. 此时会显示扩展配置设置。 找到数据流部分，然后选择在上一步中创建的数据流。

   ![数据流选择](assets/datastream-select.png) {style="border:1px solid gray"}

1. 选择&#x200B;**[!UICONTROL 保存]**。

您的标记资产现在已安装Web SDK。

+++

+++**3. 创建数据对象数据元素**

数据对象数据元素提供了一个直观的框架，用于配置Web SDK用于发送到数据流的负载。 您在以下步骤中更新的大多数规则都会与此数据元素交互。

1. 在标记界面的左侧导航中，选择 **[!UICONTROL 数据元素]**.
1. 选择 **[!UICONTROL 添加数据元素]**
1. 为数据元素指定以下设置：
   * [!UICONTROL 名称]：您想要的任何内容，例如“数据层”或“数据对象”
   * [!UICONTROL 扩展名]： [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL 变量]： [!UICONTROL 变量]
   * 复选框可以保持原样
1. 在右侧，选择以下设置：
   * “属性”单选按钮： [!UICONTROL 数据]
   * 解决方案： [!UICONTROL Adobe Analytics]
1. 选择&#x200B;**[!UICONTROL 保存]**。

![创建数据元素](assets/create-data-element.png) {style="border:1px solid gray"}

标记资产现在具有更新每个规则所需的一切。

+++

+++**4. 更新规则以使用Web SDK扩展而不是Analytics扩展**

此步骤包含迁移到Web SDK所需的大部分工作，并且需要了解您的实施的工作方式。 以下提供了示例，作为如何编辑典型标记规则的示例。 更新实施中的所有标记规则，将对Adobe Analytics扩展的所有引用替换为Web SDK扩展。

1. 在标记界面的左侧导航中，选择 **[!UICONTROL 规则]**.
1. 选择要编辑的规则。
1. 选择操作 **[!UICONTROL Adobe Analytics — 设置变量]**
1. 记下在此规则中设置的所有Analytics变量。 请注意在下拉菜单中设置的变量以及自定义代码中设置的变量。
1. 更改 [!UICONTROL 操作配置] 到以下设置：
   * [!UICONTROL 扩展名]： [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL 操作类型]：更新变量
1. 确保在右侧的下拉列表中选择数据对象。
1. 将Analytics变量设置为其各自的值，这些值与Analytics扩展中配置的值相同。
   * 在标记界面中设置的变量可以直接转换为相同的值。
   * 在自定义代码中设置的字符串变量需要进行的调整最少。 不要使用 `s` 对象，使用 `data.__adobe.analytics` 而是。 例如， `s.eVar1` 将转换为 `data.__adobe.analytics.eVar1`.
   * 自定义代码中的Analytics配置变量和方法调用可能需要修改实施逻辑。 查看每个页面的 [变量](/help/implement/vars/overview.md) 以确定如何使用Web SDK实现其等效功能。
1. 使用Web SDK扩展复制所有规则逻辑后，选择 **[!UICONTROL 保留更改]**.
1. 对使用Adobe Analytics扩展设置值的每个操作配置重复这些步骤。 此步骤包括使用标记界面设置的变量和使用自定义代码设置的变量。 自定义代码块无法引用 `s` 任何位置的对象。

上述步骤仅适用于设置值的规则。 以下步骤将替换使用 [!UICONTROL 操作配置] [!UICONTROL 发送信标].

1. 选择发送信标的规则。
1. 选择操作 **[!UICONTROL Adobe Analytics — 发送信标]**.
1. 记下当前值 [!UICONTROL 跟踪] 右侧的单选按钮([`s.t()`](../../vars/functions/t-method.md) 或 [`s.tl()`](../../vars/functions/tl-method.md))。
1. 更改 [!UICONTROL 操作配置] 到以下设置：
   * [!UICONTROL 扩展名]： [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL 操作类型]： [!UICONTROL 发送事件]
1. 在右侧，将操作设置更改为以下内容：
   * [!UICONTROL 类型]：用于 `s.t()`，使用 **[!UICONTROL Web网页详细信息页面查看次数]**. 对象 `s.tl()`，使用 **[!UICONTROL Web Web交互链接点击次数]**. 如果您使用 [`s.tl()`](../../vars/functions/tl-method.md)中，您还必须在数据对象中包含以下字段。 以下列出了这些字段 [!UICONTROL 其他属性] 执行 [!UICONTROL 更新变量] 操作配置：
      * [链接名称](../../vars/functions/tl-method.md)
      * [链接类型](../../vars/functions/tl-method.md)
      * [链接URL](../../vars/config-vars/linkurl.md)
1. 选择&#x200B;**[!UICONTROL 保留更改]**。
1. 对使用Adobe Analytics发送信标的每个操作配置重复这些步骤。

+++

+++**5. 发布更新的规则**

发布更新规则的工作流程与对标记配置进行的任何其他更改相同。

1. 在标记界面的左侧导航中，选择 **[!UICONTROL 发布流]**.
1. 选择 **[!UICONTROL 添加库]**.
1. 为此标记提交一个名称，如“升级到Web SDK”。
1. 选择 **[!UICONTROL 添加所有已更改资源]**.
1. 选择&#x200B;**[!UICONTROL 保存]**。
1. 发布工作流程会显示一个橙色点，指示它正在构建。 一旦圆点变为绿色，您的更改即可在开发环境中使用。
1. 在开发环境中测试您所做的更改，以确保所有规则均正确触发，并且数据对象已使用预期值填充。
1. 准备就绪后，提交库以供审批，构建到暂存，最终审批并发布到生产环境。

![发布流](assets/publishing-flow.png) {style="border:1px solid gray"}

+++

+++**6. 禁用Analytics扩展**

标记实施完全在Web SDK上后，您可以禁用Adobe Analytics扩展。

1. 在标记界面的左侧导航中，选择 **[!UICONTROL 扩展]**.
1. 找到并选择 [!UICONTROL Adobe Analytics] 扩展。 在右侧，选择 **[!UICONTROL 禁用]**.
1. 按照上面的相同发布工作流程发布删除的 [!UICONTROL Adobe Analytics] 扩展。
1. 在生产环境中禁用该扩展后，您可以将其完全卸载。 选择扩展，选择右侧的三个圆点菜单，然后选择 **[!UICONTROL 卸载]**.
1. 按照上面的同一发布工作流程将这些更改发布到生产环境。

+++

此时，您的Analytics实施已完全放在Web SDK上，并准备好将来迁移到Customer Journey Analytics。
