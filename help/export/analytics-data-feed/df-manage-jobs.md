---
title: 管理数据馈送作业
description: 了解如何管理数据馈送中的各个作业。 导航界面，使用筛选器和搜索，以及查找列定义。
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: d042bdb680504fdbf0ba346e5829713e529bd543
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 11%

---

# 管理数据馈送作业

作业是输出压缩文件的单个任务。 作业由馈送创建和管理。

您可以查看每个数据馈送、重新发送作业或重新处理作业的作业历史记录。

## 查看数据馈送的作业历史记录

您可以查看给定数据馈送的数据馈送作业列表，以及每个作业的相关信息。

要查看数据馈送的作业历史记录，请执行以下操作：

1. 使用您的 Adobe ID 凭据登录 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。

1. 选择右上方的九宫格图标，然后选择 [!UICONTROL **Analytics**]。

1. 在顶部导航栏中前往&#x200B;[!UICONTROL **管理员**] > [!UICONTROL **数据馈送**]。

   此时将显示您有权访问的所有报表包的数据馈送。 或者，如果尚未配置馈送，则页面会显示&#x200B;**[!UICONTROL 创建数据馈送]**&#x200B;按钮。

   ![数据馈送管理器](assets/data-feed-manager.png)

1. 选中包含要查看的作业的数据馈送旁边的复选框，然后选择&#x200B;[!UICONTROL **作业历史记录**]。

   将显示数据馈送作业历史记录，其中每个作业的相关信息都位于可用列中。

1. （可选）要调整表格中的可见列，请选择右上角的列图标![列图标](assets/customize-columns-icon.png)，然后在“自定义表格”对话框中，选择要查看的每个列，并取消选择要隐藏的每个列。

   以下列可供使用：

   * **[!UICONTROL 请求期开始]**

   * **[!UICONTROL 请求期结束]**

   * **[!UICONTROL 已计划]**

   * **[!UICONTROL 已启动]**

   * **[!UICONTROL 已完成]**

   * **[!UICONTROL 运行#]**

   * **[!UICONTROL 状态]**

   * **[!UICONTROL 错误代码]**

   * **[!UICONTROL 错误消息]**

## 重新发送数据馈送作业

当您重新发送数据馈送作业时，它会再次发送数据馈送文件，其数据和处理方式与最初发送文件时相同。 或者，您可以[重新处理数据馈送作业](#reprocess-data-feed-jobs)。

要重新发送一个或多个数据馈送作业，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **管理员**] > [!UICONTROL **数据馈送**]。

1. 选中包含要重新发送的作业的数据馈送旁边的复选框，然后选择&#x200B;[!UICONTROL **作业历史记录**]。

1. 选中一个或多个数据馈送作业旁边的复选框，然后选择&#x200B;**[!UICONTROL 重新发送]**。<!-- What does the status need to be? Error, ... -->

   ![重新处理数据馈送作业](assets/data-feed-job-resend.png)

## 重新处理数据馈送作业

重新处理数据馈送作业时，它会重新处理数据馈送作业的源数据，并使用重新处理的数据再次发送该源数据。 或者，您可以[重新发送数据馈送作业](#resend-data-feed-jobs)。

要重新处理一个或多个数据馈送作业，请执行以下操作：

1. 在Adobe Analytics中，选择&#x200B;[!UICONTROL **管理员**] > [!UICONTROL **数据馈送**]。

1. 选中包含要重新处理的作业的数据馈送旁边的复选框，然后选择&#x200B;[!UICONTROL **作业历史记录**]。

1. 选中一个或多个数据馈送作业旁边的复选框，然后选择&#x200B;**[!UICONTROL 重新处理]**。<!-- What does the status need to be? Error, ... -->

   ![重新处理数据馈送作业](assets/data-feed-job-reprocess.png)
