---
description: 以下是数据馈送处理和提交的最佳实践。
keywords: 数据馈送;最佳实践;流量尖峰;每小时;ftp
title: 最佳实践和常规信息
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 8f6c6aabf1e41cfd4b143a5d4cf14e73cdcbb603
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 最佳实践

以下是数据馈送处理和提交的最佳实践。

* 确保提前沟通预计会出现的任何流量尖峰。延迟会直接影响数据馈送的处理时间。请参阅管理员用户指南中的[计划流量尖峰](/help/admin/c-traffic-management/t-traffic-schedule-spike.md)。

* 除非您与 Adobe 签订的合同中有明确规定，否则数据馈送不包含服务级别协议。通常情况下，馈送会在报告时间范围超过后的几小时内交付，但有时也可能需要 12 小时或更长时间才能交付。

* 确保您的 FTP 站点拥有充足的空间。定期删除目标中的文件，以便您不会无意间耗尽磁盘空间。

* 使用多个文件交付流程的每小时馈送速度最快。如果贵组织高度重视及时交付，请考虑使用每小时多个文件馈送。

* 如果使用 SFTP，请勿读取或删除带 `.part` 后缀的文件。`.part` 后缀表示文件已部分传输。文件全部传输后，`.part` 后缀会消失。

* 如果您自动执行信息源摄取过程，请考虑是否可以多次传输点击和文件。 您的馈送摄取流程需要处理重复的点击和重复文件，而无需删除或复制数据。 我们建议使用`hitid_high`和`hitid_low`列的组合来唯一标识点击。

   在极少数情况下，您可能会看到重复的`hitid_high`和`hitid_low`值。 如果发生这种情况，请确认文件之前未发送和处理。 如果文件中只有一些行重复，请考虑添加`visit_num`和visit_page_num`以帮助确定唯一性。
