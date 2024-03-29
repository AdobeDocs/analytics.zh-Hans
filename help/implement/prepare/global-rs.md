---
title: Adobe Analytics 中的全局报表包
description: 了解使用全局报表包的优势和要求。
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 100%

---

# 全局报表包注意事项

全局报表包是从贵组织拥有的所有域和应用程序中收集数据的报表包。要使用此数据收集技术，需要做好相应准备，并且可能需要组织内的各团队之间相互协作。

## 优势

在大多数情况下，Adobe 都建议实施全局报表包。

* **汇总数据：**&#x200B;通过全局报表包，您能够查看自己所拥有的网站中的 KPI 和成功事件。分段和虚拟报表包可用于查看特定于网站的数据。
* **支持 Cross-Device Analytics：** CDA 要求一个报表包能从多个位置（如网站和移动设备应用程序）收集数据。如果实施得当，各个设备可以将数据拼合在一起。有关更多信息，请参阅《组件用户指南》中的 [Cross-Device Analytics](../../components/cda/overview.md)。
* **无需多个报表包：**&#x200B;可以将所有数据收集到一个报表包中，如此一来，开发人员便不太可能将数据误发到错误的报表包。
* **无需汇总**：汇总是一个比较过时的功能，是指每天对各个报表包的数据进行汇总。汇总不会删除重复的访问或访客数据，因此会导致数字虚增。有关详细信息，请参阅《管理员用户指南》中的[汇总](../../admin/admin/c-manage-report-suites/rollup-report-suite.md)。
* **节省时间：**&#x200B;工作区项目、分类、区段和计算量度都与同一全局报表包相关联。因此，可以节省管理员在管理这些组件和数据上所花费的时间。
* **更准确的跨品牌归因：**&#x200B;如果在触发成功事件之前，访客首先访问了您的一个网站，然后又点击了您的另一个网站，则系统会收集准确的归因信息。例如，访客先点击付费搜索链接并登陆网站 A。在此之后，访客又点击指向网站 B 的链接，然后进行购买。在这种情况下，全局报表包可正确地将购买归因于付费搜索。
* **简化的实施：**&#x200B;由于所有品牌/网站都将数据发送到同一报表包，因此您在每个网站上的实施都将保持一致。这一强制性管理功能可确保将特定维度或量度保存在同一 eVar 或事件中。管理员、测试人员、标签管理负责人员和分析师都将从这项简化中受益。

>[!NOTE]
>
>协调全局报表包实施的工作是一项大工程。为此，Adobe 建议与顾问合作，以尽量避免可能会出现问题和由此产生复杂情况。

## 使用全局报表包启动新实施

请阅读以下一般准则，以了解实施全局报表包的流程。

1. 在 Adobe Analytics 中创建全局报表包。有关详细信息，请参阅《管理员用户指南》中的[创建报表包](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)。
1. 与组织中负责每个域的团队合作。许多团队都有特定于其业务领域的报告要求。
1. 将所有这些要求记录并汇总到一个[解决方案设计文档](solution-design.md)中。如果各个团队具有类似的维度要求，则他们可以使用相同的自定义变量。例如，如果网站 A 和网站 B 都需要痕迹导航维度，则两个网站在实施过程中都可以通过 eVar1 发送该数据。

   >[!IMPORTANT]
   >
   > 请确保所有给定的自定义变量在各个域中的使用方式均类似。请勿在不同网站上将同一 eVar 或事件用于不同目的。
1. 请确保每个域都有一个数据层，以便能够简化数据收集流程。如果没有数据层，虽然仍然可以收集数据，但实施的可靠性会降低且使用时间会缩短，在对您的网站进行重新设计时尤其如此。
1. 使用 Adobe Experience Platform 中的标记实施 Analytics。不同的网站可能需要不同的数据元素。请使用特定于每个域的规则以确保正确填充每个数据元素，然后将这些数据元素分配给相应的 eVar 和事件。请参阅[标记概述](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hans)。
1. 包含 [Adobe Experience Cloud ID 服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)，并使用 [appendVisitorIDsTo](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html?lang=zh-Hans) 函数。当用户从一个域单击到另一个域时，此函数将合并访客数据。

## 使用全局报表包修改现有的实施

若要跨多个站点将一个现有实施转移到单个全局报表包中，则需要贵组织中的各个团队之间相互协作。

1. 确定您是要使用某个现有报表包，还是要新建一个报表包以完全重头开始。如果要更改实施中现有变量的用法，建议从新建一个报表包开始。
2. 确定直接转换日期，即要转换到全局报表包的日期。进行直接转换的理想时机是在两个重要的报告时间段之间，或是在对网站进行重大更改时。例如，财季或财年初、网站刷新期间，或对新的标签管理系统进行更改期间。
3. 按照上述步骤操作（创建报表包、收集所有报表要求并将其汇总到一个解决方案设计文档中、在每个网站上建立一个数据层）。实施 Adobe Experience Platform 中的标记时，请使用您网站的开发版本验证您的实施。
4. 确认您的标记实施可以在开发版网站上正常使用后，请在既定的直接转换日期推出标记实施。

## 相关页面

[从多包标记转换到全局报表包和虚拟报表包](../../components/vrs/vrs-considerations.md)
[比较汇总和全局报表包](../../admin/admin/c-manage-report-suites/rollup-report-suite.md)
