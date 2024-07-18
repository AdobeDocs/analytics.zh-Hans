---
title: CDA 工作区模板
description: 描述 Analysis Workspace 内 CDA 模板中的每个字段。
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 93%

---

# CDA 工作区模板

Adobe 提供一个模板以查看重要的跨设备性能数据。

1. 导航到 [experiencecloud.adobe.com](https://experiencecloud.adobe.com) 并使用 Adobe ID 凭据登录。
1. 单击顶部的 9 宫格图标，然后单击“Analytics”。
1. 单击顶部的[!UICONTROL 工作区]，然后单击[!UICONTROL 新建项目]。
1. 找到“跨设备分析”模板&quot;，然后单击[!UICONTROL 创建]。
1. 如果出现提示，请将报表包更改为支持 CDA 的报表包。

将创建一个包含多个面板的 Analysis Workspace 项目。在顶部显示了目录和简介，允许查看报表的上下文和导致到单个报表。单击目录中的链接或展开面板的折叠面板可查看这些报表。

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **用户标识**：显示使用基于 Cross-Device Analytics 的方法识别网站访客的频率。
* **测量受众规模**：显示“独特设备”与“人员”的对比。这两个数字的比例称为“跨设备压缩”，该计算量度在此面板中可见。此压缩量度取决于多种因素：
   * 登录率：登录您网站的用户越多，Adobe 跨设备识别和拼合的访客越多。登录率较低的网站，其压缩率也较低。
   * Experience Cloud ID 覆盖：只能拼合拥有 ECID 的访客。使用 ECID 访问您网站的访客百分比越低，则压缩率也越低。
   * 多种设备使用情况：如果网站的访客不使用多种设备，则压缩率可能较低。
   * 报表粒度：按日压缩通常比按月或按年压缩更小。单个用户在一天内使用多种设备的几率比整个月内使用多种设备的几率更小。分段、过滤或使用划分维度也可能会获得较低的压缩率。
* **基于人员的区段**：包含区段下拉列表，允许您查看设备特定数据。 此面板鼓励对区段进行实验，以了解包括或排除设备类型对报表有何影响。
* **分析跨设备历程**：根据设备类型提供流量和流失报告。
* **跨设备归因**：将历程IQ和归因的功能结合使用。
* **其他提示与技巧**：可让您充分利用 CDA 的有用主题。
