---
description: 根据标准或自定义模板创建 Workspace 项目。
title: 模板
feature: Workspace Basics
role: User, Admin
exl-id: 751399fe-6d4f-47cc-8827-82c992079b52
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: ht
source-wordcount: '1410'
ht-degree: 100%

---

# 模板

您可以选择从以下项创建项目：

* **空白项目（默认）**：有关说明，请参阅[创建 Analysis Workspace 项目](/help/analyze/analysis-workspace/home.md)。
* **标准模板**：这些模板由 Adobe 创建，随产品一起提供。
* **自定义模板**：这些模板可由具有管理员权限的用户或非管理员创建、共享或删除，前提是已在 Admin Console 中向他们授予了 [!UICONTROL Analysis Workspace：另存为模板]权限。[了解更多...](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=zh-Hans)

![](assets/start_modal.png)

## 创建自定义模板 {#create-custom-template}

具有管理员权限的用户可以将他们创建的任何项目转换为自定义模板。以下是具体操作方法：

1. 打开该项目。
1. 转到&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 另存为模板]**。

   ![](assets/save_project_template.png)

   项目将使用当前项目名称再加上“（模板）”一词进行保存。管理员可以通过编辑模板来更改此名称。

   >[!NOTE]
   >
   >默认情况下，项目模板对贵组织的每个人均可见。您可以通过应用标记来组织这些模板。（转到&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 项目信息和设置]**&#x200B;以编辑标记和描述。）

以下是一段关于创建和管理自定义模板的视频：

>[!VIDEO](https://video.tv.adobe.com/v/23231/?quality=12)

### 管理自定义模板 {#manage-custom-template}

| 操作 | 描述 |
|--- |--- |
| 编辑模板 | 允许管理员通过更改模板的数据源、修改组件、可视化图表、日期范围等内容来编辑模板。要编辑自定义模板，请<ul><li>在 Analysis Workspace 中调出自定义模板列表，选择一个模板，然后单击“编辑模板”，或</li><li>在 Analytics 中，导航到“组件”>“项目”，然后对“模板”进行过滤。单击要编辑的模板的名称。</li></ul>**注意：**&#x200B;编辑模板之后，根据具体情况，您有两个选项可用：“保存”、“另存为”。以下是它们的不同之处：<ul><li>**保存：**&#x200B;更新所有用户的自定义模板。其他人从该自定义模板创建项目时会看到您做出的更改。</li><li>**另存为：**&#x200B;创建包含您所做更改的自定义模板副本。（如果“共享”>“共享项目”菜单项处于禁用状态，那么您可以据此判断您处于编辑模式当中。）</li></ul> |
| 搜索模板 | 在“自定义模板”对话框中，单击“搜索模板”。 |
| 排序模板 | 您可以按字母顺序、相关性和创建日期对模板进行排序。在“自定义模板”对话框中，单击“排序:”。 |
| 将标签应用到模板 | 打开模板，然后转到“项目”>“项目信息和设置”。单击“添加标签”。 |
| 修改模板描述 | 打开模板，然后转到“项目”>“项目信息和设置”。双击该描述并进行编辑。 |


## 标准模板

首次打开 Workspace 时，模板位于左边栏中。Analysis Workspace 模板涵盖常见用例。它们按所属的垂直领域分组，并填充了不同的维度、区段、量度和可视化图表，具体取决于您选择的报表包。

您可以按原样使用这些预填充模板，或修改它们以符合您的需要（例如，添加或替换量度或可视化图表），然后起一个新名称保存它们。

这里有一段关于 [Analysis Workspace 中的标准模板](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/standard-templates-in-analysis-workspace.html?lang=zh-Hans)的视频教程（2 分 46 秒）

以下是可用的模板和每个模板帮助回答的问题：

### 培训

该标准模板将指导您逐步了解在 Workspace 中构建第一个分析时通常会用到的术语和步骤。 该模板可用作新建项目模式中的标准模板，并替换当前存在的示例项目，供列表中没有其他项目的新用户使用。

以下是一段关于[!UICONTROL 培训教程]模板的视频：

>[!VIDEO](https://video.tv.adobe.com/v/33773/?quality=12)

### 广告

>[!IMPORTANT]
>
>仅当您的报表包启用了 [Advertising Analytics](https://experienceleague.adobe.com/docs/analytics/integration/advertising-analytics/overview.html?lang=zh-Hans) 时，广告模板才可用。

* **付费搜索引擎**：此模板可划分广告趋势、广告平台、关键字、帐户、营销活动等。

### 商务

* **Magento：营销与商务**：此模板通过营销渠道归因细分您的电子商务转化，并按搜索关键字、登陆页面、地理位置等提供见解。以下是一段关于 [Magento：营销与商务模板](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/magento/magento-analysis-workspace-template.html?lang=zh-Hans)的视频教程。

### 数据收集

* **ITP 影响**：了解 Apple 的 ITP 如何影响您的数据以及如何相应地调整报表。

### 媒体

* **内容使用**：谁是我的忠实读者
* **回访间隔 - 频率 - 忠诚度**：哪种内容使用最多，并且吸引用户？
* **流媒体使用**：提供所有数字设备的媒体使用的趋势和主要量度。 以下是一段关于流媒体使用模板的视频：

   >[!VIDEO](https://video.tv.adobe.com/v/23901/?quality=12)

### 移动

>[!IMPORTANT]
>
>仅当您的报表包启用了移动应用程序分析时，移动模板才可用。

* **客户获取：** 了解移动设备客户获取链接的表现如何。
* **应用程序使用情况：** 应用程序拥有多少用户、启动次数和首次启动次数，以及平均会话时长是多少？
* **历程：** 我的应用程序最突出的使用模式是什么？
* **关键量度：** 掌握应用程序关键量度。
* **位置：** 包括可展示位置数据的“地图”。
* **消息：** 重点关注应用内消息和消息推送的性能。
* **性能：**&#x200B;应用程序性能如何、用户在哪些情况下遇到问题？
* **维系率：**&#x200B;谁是我的忠实用户，他们会怎么做？

### 零售

* **促销活动效果：**&#x200B;哪些促销活动获得的收入最多？
* **产品：**&#x200B;哪些产品的表现最佳？

### Web

* **客户获取：**&#x200B;我的网站最主要的流量推动因素是什么？
* **AEM 网站性能概述：** 我的 Adobe Experience Manager 网站的性能如何？
* **内容使用情况：**&#x200B;用户在我的网站中最常访问哪些区域？
* **维系率：**&#x200B;哪类用户可能成为我的网站的忠实用户？
* **技术：**&#x200B;用户使用哪些技术访问我的网站？

### 人员

>[!NOTE]
>
>“人员”模板及其关联的“人员”量度只能在 [Adobe Experience Cloud 设备协作](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=zh-Hans)中使用。

该模板基于“人员”量度，“人员”量度是删除了重复数据的独特访客量度版本。通过“人员”量度可测量客户使用多个设备与您的品牌进行交互的频率。该模板允许您

* 将美国/加拿大的数据与世界其它地区的数据进行分段。该设备协作当前仅在北美地区可用。
* 横向比较“人员”与“独特访客”量度。
* 请参阅“压缩率”，该计算量度用于计算“人员”量度小于独特访客的百分比。
* 比较客户使用的设备类型总数
* 查看每人使用的平均设备数量。
* 了解如何对“人员”量度进行分段堆叠。
* 探索如何在您的环境中使用 Experience Cloud ID 来增强“人员”量度的效率。

### 历程 IQ：Cross-Device Analytics 模板

<!--This content is mirrored in the CDA doc.-->

此模板可让您查看重要的跨设备性能数据。它仅适用于有权访问[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hans) (CDA) 的客户。

* **对协作图成员的特别说明**：显示报表包的哪些部分包含支持协作图的区域的访客，以及不支持协作图的区域的访客。
* **用户标识**：显示使用基于 Cross-Device Analytics 的方法识别网站访客的频率。
* **测量受众规模**：显示“独特设备”与“人员”的对比。这两个数字的比例称为“跨设备压缩”，该计算量度在此面板中可见。此压缩量度取决于多种因素：
   * **使用协作图或专用图：**&#x200B;一般而言，使用设备协作的组织往往比使用专用图的组织获得更好的压缩率。
   * **登录率**：登录您网站的用户越多，Adobe 跨设备识别和拼合的访客越多。登录率较低的网站，其压缩率也较低。
   * **Experience Cloud ID 覆盖**：只能拼合拥有 ECID 的访客。使用 ECID 访问您网站的访客百分比越低，则压缩率也越低。
   * **多种设备使用情况**：如果网站的访客不使用多种设备，则压缩率可能较低。
   * **报表粒度**：按日压缩通常比按月或按年压缩更小。单个用户在一天内使用多种设备的几率比整个月内使用多种设备的几率更小。分段、过滤或使用划分维度也可能会获得较低的压缩率。
* **基于人员的区段**：包含区段下拉列表，允许您查看设备特定数据。此面板鼓励对区段进行实验，以了解包括或排除设备类型对报表有何影响。
* **分析跨设备历程**：根据设备类型提供流量和流失报告。
* **跨设备归因**：将历程 IQ 和归因 IQ 的功能结合使用。
* **其他提示与技巧**：可让您充分利用 CDA 的有用主题。
