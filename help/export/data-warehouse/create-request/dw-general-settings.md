---
description: 描述如何创建 Data Warehouse 请求的步骤。
title: Data Warehouse请求常规设置
feature: Data Warehouse
source-git-commit: 0abf0c76f38b481c0b72d113fe49e0da03ddd8cd
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 27%

---

# Data Warehouse请求常规设置

>[!AVAILABILITY]
>
>本文中介绍的一些Data Warehouse功能(以及此部分中的其他Data Warehouse文章)仅在版本的有限测试阶段提供，并且在您的环境中可能尚未提供。
>
>有关尚未向所有客户提供的功能的信息，以及有关这些功能发布时间线的信息，请参阅 [发行说明](/help/release-notes/latest.md).
>
>当该功能正式发布时，将删除此说明。有关 Analytics 发布流程的信息，请参阅 [Adobe Analytics 功能发布](/help/release-notes/releases.md)。

创建Data Warehouse请求时，有多种可用的配置选项。 以下信息介绍了如何配置请求的常规设置。

有关如何开始创建请求以及指向其他重要配置选项的链接的信息，请参阅 [创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

要配置Data Warehouse请求的常规设置，请执行以下操作：

1. 通过选择开始在Adobe Analytics中创建Data Warehouse请求 **[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **添加**].

   有关其他详细信息，请参阅 [创建Data Warehouse请求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 在“新建Data Warehouse请求”页面上，选择 [!UICONTROL **常规设置**] 选项卡。

   ![“报表目标”选项卡](assets/dw-general-settings.png)

1. 请完成以下字段：

   | 选项 | 函数 |
   |---------|----------|
   | 请求名称 | 管理请求时，此名称将显示在主Data Warehouse页上。 |
   | 日期范围 | 选择要包含在报告中的日期范围。 <p>您可以选择自定义日期或预设日期范围。 预设范围是相对于发送报表日期的。</p><p>以下预设选项可用：</p><ul><li>今天</li><li>昨天</li><li>最近 7 天</li><li>最近 30 天</li><li>本周</li><li>上周</li><li>最近2周</li><li>最近3周</li><li>最近4周</li><li>本月</li><li>上个月</li><li>上一小时</li><li>今天</li><li>今天</li></ul> |
   | 粒度 | <!--what does this setting do? It's not the schedule/frequency... --> 时间粒度。 有效值为无、小时、天、周、月、季和年。<p>报告粒度需要额外的处理时间。在对全年报告每月粒度时，如果按月提交报表请求，则报表的处理速度会更快。</p> |

   {style="table-layout:auto"}

1. 继续在上配置您的Data Warehouse请求 [!UICONTROL **构建报告**] 选项卡。 有关更多信息，请参阅 [为Data Warehouse请求构建报告](/help/export/data-warehouse/create-request/dw-request-build-report.md).