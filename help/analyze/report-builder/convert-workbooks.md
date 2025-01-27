---
title: 如何将旧版Report Builder工作簿转换为数据块
description: 介绍如何将旧版请求转换为数据块
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: cf1b64479690cf5bdfdc8d9ba08879d0e0886611
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---

# 将旧版Report Builder工作簿转换为数据块

在向新Report Builder技术迁移的过程中，您可以快速将当前旧版工作簿转换为基于Javascript的工作簿。

>[!IMPORTANT]
>
>复制每个工作簿并重命名一个版本，然后再转换它。 这样，如果需要原始工作簿的副本，您仍然可以使用该副本。

>[!VIDEO](https://video.tv.adobe.com/v/3434957/?quality=12&learn=on)

1. 按照](/help/analyze/report-builder/report-builder-setup.md)中的说明由[设置新Report Builder。

1. 打开Excel，然后单击右上方的Adobe Report Builder图标。

1. 单击&#x200B;**[!UICONTROL 登录]**&#x200B;并登录Report Builder。

1. Report Builder加载项检测到此工作簿是否包含[旧版Report Builder](/help/analyze/legacy-report-builder/home.md)请求。

   ![升级工作簿提示](assets/upgrade_workbook.png)

1. 如果找到一个或多个旧版请求，请单击&#x200B;**[!UICONTROL 升级]**&#x200B;以升级工作簿。

   >[!NOTE]
   >
   >您必须单独升级每个请求。 不支持批量升级。


1. 如果升级，会出现警告，提醒您对工作簿的更改。 它还敦促您在继续之前创建旧工作簿的备份。

   ![升级警告](assets/upgrade_warning.png)

1. 单击&#x200B;**[!UICONTROL 继续]**&#x200B;以继续升级。

   如果升级成功，将显示以下完成通知：

   ![升级完成](assets/upgrade_complete.png)

1. （可选）单击&#x200B;**[!UICONTROL 下载升级报告]**。 此报表包含每个已升级数据块的状态。

您现在可以[管理数据块](/help/analyze/report-builder/manage-reportbuilder.md)。


## 新Report Builder中不支持旧版Report Builder功能 {#unsupported}

将旧版Report Builder的功能与新Report Builder加载项进行比较时，某些旧版功能不再可用：

- 实时请求

- 路径/流失报表

- 计划报表的FTP选项

- 访客量度。 以下量度将全部转换为“独特访客”，即使报表结果可能不完全匹配： `visitorshourly`、`visitorsdaily`、`visitorsweekly`、`visitorsmonthly`、`visitorsquarterly`和`visitorsyearly`。 这也适用于`mobilevisitorshourly`、`mobilevisitorsdaily`、`mobilevisitorsweekly`、`mobilevisitorsmonthly`、`mobilevisitorsquarterly`和`mobilevisitorsyearly`。

## 计划转换的工作簿 {#schedule}

请参阅计划文章中的[计划转换的工作簿](/help/analyze/report-builder/schedule-reportbuilder.md)。