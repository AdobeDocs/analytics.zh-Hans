---
description: 您可以在“作业”列表中重新运行一个或多个作业。
keywords: 数据馈送；工作；rreun
seo-description: 您可以在“作业”列表中重新运行一个或多个作业。
seo-title: 重新运行工作
solution: Analytics
title: 重新运行工作
uuid: 5caf95da-dd88-4b1 a-a081-684f4 fd1 f714
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 重新运行工作

您可以在“作业”列表中重新运行一个或多个作业。

1. 选择要重新运行的一个或多个作业。
1. Click **[!UICONTROL Rerun Job]**.

   重新运行过程取决于当前作业状态：

   | 状态 | 在服务器上缓存的文件名 | 过程 |
   |---|---|---|
   | 已完成 | 是 | 已重新发送文件。 |
   | 已完成 | 否 | 在重新处理作业后重新发送。 |
   | 失败 | 否 | 在重新处理作业后重新发送。 |
   | 其他状态 | 不适用 | 不受支持。 |

