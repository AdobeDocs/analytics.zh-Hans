---
description: 您可以在“作业”列表中重新运行一个或多个作业。
keywords: Data Feed;job;rerun
solution: Analytics
title: 重新运行作业
uuid: 5caf95da-dd88-4b1a-a081-684f4fd1f714
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 重新运行作业

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

