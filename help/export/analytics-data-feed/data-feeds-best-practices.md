---
description: '以下是数据馈送处理和提交的最佳实践。您应该 '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: 最佳实践和常规信息
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 最佳实践

以下是数据馈送处理和提交的最佳实践。

* 确保提前沟通预计会出现的任何流量尖峰。延迟会直接影响数据馈送的处理时间。请参阅管理员用户指南中的[计划流量尖峰](/help/admin/c-traffic-management/t-traffic-schedule-spike.md)。
* 除非您与 Adobe 签订的合同中有明确规定，否则数据馈送不包含服务级别协议。通常情况下，馈送会在报告时间范围超过后的几小时内交付，但有时也可能需要 12 小时或更长时间才能交付。
* 确保您的 FTP 站点拥有充足的空间。定期删除目标中的文件，以便您不会无意间耗尽磁盘空间。
* 使用多个文件交付流程的每小时馈送速度最快。如果贵组织高度重视及时交付，请考虑使用每小时多个文件馈送。
* 如果使用 SFTP，请勿读取或删除带 `.part` 后缀的文件。`.part` 后缀表示文件已部分传输。文件全部传输后，`.part` 后缀会消失。
* 如果您要自动执行馈送纳入过程，请考虑将文件进行多次传输。用户或 Adobe 可以重新发送重复文件，但 Adobe 很少会这样做。
