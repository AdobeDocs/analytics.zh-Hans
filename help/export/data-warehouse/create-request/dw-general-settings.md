---
description: 描述如何创建 Data Warehouse 请求的步骤。
title: Data Warehouse请求常规设置
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: baac0c0384b714cf2ca536149ca10eec3a7065ad
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 39%

---

# Data Warehouse请求常规设置

提供了在创建 Data Warehouse 请求时可使用的多种配置选项。以下信息介绍了如何配置请求的常规设置。

有关如何开始创建请求的信息以及其他重要配置选项的链接，请参阅[创建 Data Warehouse 请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)。

要配置Data Warehouse请求的常规设置，请执行以下操作：

1. 通过选择&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **添加**]，开始在Adobe Analytics中创建Data Warehouse请求。

   有关更多详细信息，请参阅[创建 Data Warehouse 请求](/help/export/data-warehouse/create-request/t-dw-create-request.md)。

1. 在“新建Data Warehouse请求”页面上，选择&#x200B;[!UICONTROL **常规设置**]&#x200B;选项卡。

   ![“报表目标”选项卡](assets/dw-general-settings.png)

1. 请完成以下字段：

   | 选项 | 功能 |
   |---------|----------|
   | 请求名称 | 管理请求时，此名称将显示在主Data Warehouse页上。 |
   | 日期范围 | 选择要包含在报告中的日期范围。 <p>您可以选择自定义日期或预设日期范围。 预设范围是相对于发送报表日期的。</p><p>以下预设选项可用：</p><ul><li>今天</li><li>昨天</li><li>最近 7 天</li><li>最近 30 天</li><li>本周</li><li>上周</li><li>最近2周</li><li>最近3周</li><li>最近4周</li><li>本月</li><li>上个月</li><li>上一小时</li></ul> |
   | 粒度 | <!--what does this setting do? It's not the schedule/frequency... --> 时间粒度。 有效值为无、小时、天、周、月、季和年。<p>报告粒度需要额外的处理时间。在对全年报告每月粒度时，如果按月提交报表请求，则报表的处理速度会更快。</p> |
   | 向组织中的用户提供 | 所有Data Warehouse请求仅对您和所有系统管理员可见。 如果要使请求对贵组织中的每个人都可见，请启用此选项。 <p>如果您希望组织中的其他用户帮助创建或更新请求，则启用此选项很有用。</p> |

   {style="table-layout:auto"}

1. 继续在&#x200B;[!UICONTROL **生成报表**]&#x200B;选项卡上配置Data Warehouse请求。 有关详细信息，请参阅[为Data Warehouse请求生成报告](/help/export/data-warehouse/create-request/dw-request-build-report.md)。
