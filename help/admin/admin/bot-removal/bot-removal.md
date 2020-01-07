---
title: 在 Adobe Analytics 中删除机器人
description: 在 Adobe Analytics 中删除机器人的 3 种方法
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 在 Adobe Analytics 中删除机器人

在 Adobe Analytics 中，您可以使用多个选项从报表中删除机器人流量：

## 使用机器人规则

**[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理员]** &gt; **[!UICONTROL 报表包]** &gt; **[!UICONTROL 编辑设置]** &gt; **[!UICONTROL 常规]** &gt; **[!UICONTROL 机器人规则]**&#x200B;中同时支持标准和自定义机器人过滤方法：

| 规则类型 | 描述 |
|--- |--- |
| 标准 IAB 机器人规则 | 选择&#x200B;**[!UICONTROL 启用 IAB 机器人过滤规则]**&#x200B;可使用 [IAB 的](https://www.iab.com/)（国际广告局的）国际蜘蛛程序和机器人列表来删除机器人流量。大多数客户至少都会选择此选项。 |
| 自定义机器人规则 | 您可以根据用户代理、IP 地址或 IP 范围定义和添加自定义机器人规则。 |

有关详细信息，请参阅[机器人规则概述](/help/admin/admin/bot-removal/bot-rules.md)。

## 使用 `hitGovernor` 实施插件

使用 [s.hitGovernor 实施插件](https://docs.adobe.com/content/help/zh-Hans/analytics/implementation/javascript-implementation/plugins/hitgovernor.html)，以便删除行为与机器人行为相似的访客，即这些访客每分钟会发送数十次或数百次点击。

## 使用 Adobe 工具组合

此外，由于机器人发展较快，因此 Adobe 提供了其他几个强大的功能，如果定期将这些功能合理组合在一起，将有助于提高其数据质量。这些功能包括：Experience Cloud ID 服务、分段、Data Warehouse、客户属性和虚拟报表包。以下对如何利用这些工具的概述。

### 步骤 1：将访客的 Experience Cloud ID 传递到新声明的 ID

首先，您需要在[人员核心服务](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/audiences/audience-library.html)中创建一个新声明的 ID。您需要将访客的 Experience Cloud ID 传递到此新声明的 ID 中，您可以通过 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/zh-Hans/launch/using/implement/solutions/idservice-save.html) 轻松快速地完成此操作。我们使用名称“ECID”作为声明的 ID。

![](assets/bot-cust-attr-setup.png)

以下介绍了如何通过数据元素捕获此 ID。请确保将您的 Experience Cloud 组织 ID 正确填充到数据元素中。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

设置此数据元素后，请按照[以下说明](https://docs.adobe.com/content/help/zh-Hans/launch/using/implement/solutions/idservice-save.html)将声明的 ID 传递到 Launch 中的 ECID 工具。

### 步骤 2：使用分段识别机器人

现在，您已将访客的 ECID 传递到已声明的 ID 中，下面可以使用 [Analysis Workspace 中的分段](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)来识别行为类似于机器人的访客。机器人通常通过其行为进行定义：单次访问、异常用户代理、未知的设备/浏览器信息、无反向链接、新访客、异常登录页面等。使用工作区深化和分段的强大功能，识别已避开 IAB 过滤和您的报表包机器人规则的机器人。例如，以下是您可以使用的区段的屏幕截图：

![](assets/bot-filter-seg1.png)

### 步骤 3：通过 Data Warehouse 导出区段中的所有 [!DNL Experience Cloud IDs]

由于您已经使用区段识别了机器人，那么下一步就是利用 Data Warehouse 提取与此区段关联的所有 Experience Cloud ID。这是您应设置 [Data Warehouse](https://docs.adobe.com/content/help/zh-Hans/analytics/export/data-warehouse/data-warehouse.html) 请求的方式：

![](assets/bot-dwh-3.png)

请记住将 Experience Cloud 访客 ID 用作您的维度并应用机器人区段。

### 步骤 4：将此列表作为客户属性传回 Adobe

Data Warehouse 报表被送达后，您将拥有一个需要从历史数据中过滤的 ECID 列表。将这些 ECID 复制并粘贴到一个空白的 .CSV 文件中，该文件只包含两列：ECID 和机器人标记。

* **ECID**：确保此列标题与您为上述新声明的 ID 提供的名称相匹配。
* **机器人标记**：将其作为客户属性架构维度添加。

将此 .CSV 文件用作“客户属性”导入文件，然后按照此[博客文章](https://theblog.adobe.com/link-digital-behavior-customers)中的说明，将报表包订阅给“客户属性”。

![](assets/bot-csv-4.png)

### 步骤 5：创建可利用新客户属性的区段

在您的数据集已处理并集成到 Analysis Workspace 中后，再创建一个区段，以便利用新的“机器人标记”客户属性维度和[!UICONTROL 排除]容器：

![](assets/bot-filter-seg2.png)

### 步骤 6：使用此区段作为虚拟报表包过滤器

最后，您应该创建一个[虚拟报表包](/help/components/vrs/vrs-about.md)，以便利用此区段过滤掉已识别的机器人：

![](assets/bot-vrs.png)

这个新分段的虚拟报表包现在将生成一组更简洁的数据，其中已识别的机器人会被完全删除。

### 步骤 7：定期重复步骤 2、3 和 4

在定期安排分析之前，设置至少每月提醒一次，以识别和过滤新的机器人。
