---
title: 在 Adobe Analytics 中删除机器人
description: 如何删除 Adobe Analytics 中的机器人
feature: Bot Removal
role: Admin
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: 50c2881aa61097c14057dd4fd4654c832f20b26f
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 78%

---

# 在 Adobe Analytics 中删除机器人

Adobe Analytics提供了多个用于从报表中删除机器人流量的选项：

## 使用机器人规则

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 机器人规则]**&#x200B;中同时支持标准和自定义的机器人过滤方法：

| 规则类型 | 描述 |
|--- |--- |
| 标准 IAB 机器人规则 | 选择&#x200B;**[!UICONTROL 启用 IAB 机器人过滤规则]**&#x200B;可使用 [IAB ](https://www.iab.com/)的（国际广告局的）国际蜘蛛程序和机器人列表来删除机器人流量。大多数客户至少都会选择此选项。 |
| 自定义机器人规则 | 您可以根据用户代理、IP 地址或 IP 范围定义和添加自定义的机器人规则。 |

有关详细信息，请参阅[了解和配置机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)。

## 使用 [!UICONTROL websiteBot] 插件识别机器人

[!UICONTROL websiteBot] 插件允许您动态识别桌面访客是否为机器人。您可以凭借此数据来提高所有报表类型的准确性，从而更好地衡量合法的网站流量。

这个插件可执行两项检查：

* 首先，它使用 navigator.UserAgent 变量确定设备是桌面还是移动设备。移动设备将被忽略。
* 如果是桌面设备，该插件将添加一个用于了解鼠标移动的事件侦听器。

有关详细信息，请参阅[《Adobe Analytics 实施指南》](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html?lang=zh-Hans)。

## 使用 Adobe 工具组合

此外，由于机器人发展较快，因此 Adobe 提供了其他几个强大的功能，如果定期将这些功能合理组合在一起，将有助于提高其数据质量。这些功能包括：Experience Cloud ID服务、分段、Data Warehouse、客户属性和虚拟报表包。 这里是如何使用这些工具的概述。

### 步骤 1：将访客的 Experience Cloud ID 传递到新声明的 ID

要开始，请在 [People Core Service](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=zh-Hans) 中创建新声明的 ID。将您的访客 Experience Cloud ID 传递到此新声明的 ID 中，这可以使用 [Adobe Experience Platform 中的标记](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=zh-Hans)快速轻松地完成。我们使用名称“ECID”作为声明的 ID。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-cust-attr-setup.png)

以下介绍了如何通过数据元素捕获此 ID。请确保正确地将 Experience Cloud OrgID 填充到数据元素中。

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

设置了数据元素之后，请按照[这些说明](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=zh-Hans)将声明的 ID 传递到使用 Adobe Experience Platform 中的标记的 ECID 工具中。

### 步骤 2：使用分段识别机器人

现在，您已将访客的 ECID 传递到已声明的 ID 中，下面可以使用 [Analysis Workspace 中的分段](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=zh-Hans)来识别行为类似于机器人的访客。机器人通常通过其行为进行定义：单次访问、异常用户代理、未知的设备/浏览器信息、无反向链接、新访客、异常登录页面等。使用工作区深化和分段的强大功能，识别已避开 IAB 过滤和您的报表包机器人规则的机器人。例如，以下是您可以使用的区段的屏幕截图：

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg1.png)

### 步骤 3：通过 Data Warehouse 导出区段中的所有 [!DNL Experience Cloud IDs]

现在，您已使用区段确定了机器人，下一步是使用 Data Warehouse 提取与此区段关联的所有 Experience Cloud ID。此屏幕截图显示了应如何设置 [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) 请求：

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-dwh-3.png)

请记住使用 Experience Cloud 访客 ID 作为您的维度并应用“Bots”区段。

### 步骤4：将此列表作为客户属性传递回Adobe

Data Warehouse 报表到达之后，您就有了必须从历史数据中筛选出去的 ECID 列表。将这些 ECID 复制并粘贴到一个空白的 .CSV 文件中，该文件只包含两列：ECID 和机器人标记。

* **ECID**：确保此列标题与您为以上新声明的 ID 提供的名称相匹配。
* **机器人标记**：添加“机器人标记”作为客户属性架构维度。

将此.CSV文件用作“客户”属性导入文件，然后按照此[博客帖子](https://blog.adobe.com/en/publish/2016/10/20/link-digital-behavior-customers)中的说明，将报表包订阅给“客户”属性。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-csv-4.png)

### 步骤5：创建一个利用新“客户”属性的区段

在您的数据集得到了处理并集成到 Analysis Workspace 之后，创建另一个利用您的新“机器人标记”客户属性维度的区段，以及一个[!UICONTROL 排除]容器：

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg2.png)

### 步骤6：将此区段用作虚拟报表包过滤器

最后，创建使用此区段的[虚拟报表包](/help/components/vrs/vrs-about.md)以过滤掉已识别的机器人：

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-vrs.png)

这些新区段虚拟报表包现在会生成更干净的数据集，其中删除了已识别的机器人。

### 步骤 7：定期重复步骤 2、3 和 4

设置至少一个月的提醒以识别和过滤新的机器人，最好在定期计划的分析之前进行。

>[!MORELIKETHIS]
>
>* [更好的机器人阻止（第1部分）：基本知识](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-1-the-basics/ba-p/715839)
>* [更好的机器人阻止（第2部分）：识别机器人并利用CIDR](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-2-identifying-bots-and-leveraging-cidr/ba-p/722132)
>* [更好的机器人阻止（第3部分）：点击调控器](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-3-the-hit-governor/ba-p/727051)

