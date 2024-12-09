---
description: 了解Analytics中数据馈送处理和提交的最佳实践。
keywords: 数据馈送;最佳实践;流量尖峰;每小时;ftp
title: 最佳实践和常规信息
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 0eef1b1269dcfbc7648127602bdfe24d4789f4b7
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 84%

---

# 数据馈送最佳实践

以下是数据馈送处理和提交的一些最佳实践。

* 确保提前沟通预计会出现的任何流量尖峰。延迟会直接影响数据馈送的处理时间。请参阅管理员用户指南中的[计划流量尖峰](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)。

* 除非您与 Adobe 签订的合同中有明确规定，否则数据馈送不包含服务级别协议。通常情况下，馈送会在报告时间范围超过后的几小时内交付，但有时也可能需要 12 小时或更长时间才能交付。

* 使用多个文件交付流程的每小时馈送速度最快。如果贵组织高度重视及时交付，请考虑使用每小时多个文件馈送。

* 如果您要自动执行馈送纳入过程，请考虑点击和文件可能会进行多次传输的可能性。您的馈送纳入过程需要处理重复点击和重复文件，而不会出错或复制数据。我们建议组合使用 `hitid_high` 和 `hitid_low` 列以唯一标识点击。

  在极少数情况下，您可能会看到重复的 `hitid_high` 和 `hitid_low` 值。如果发生这种情况，请确认以前未发送和处理该文件。如果只有文件中的某些行是重复的，请考虑添加 `visit_num` 和 `visit_page_num` 以帮助确定唯一性。

* 如果使用FTP（不推荐），请确保您的FTP站点拥有充足的空间。 定期删除目标中的文件，以便您不会无意间耗尽磁盘空间。

* 如果使用sFTP（不推荐），请勿读取或删除后缀为`.part`的文件。 `.part` 后缀表示文件已部分传输。文件全部传输后，`.part` 后缀会消失。