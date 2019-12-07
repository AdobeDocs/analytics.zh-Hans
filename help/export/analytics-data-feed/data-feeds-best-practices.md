---
description: '以下是数据馈送处理和提交的最佳实践。您应该 '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: 最佳实践和常规信息
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 最佳实践

以下是数据馈送处理和提交的最佳实践。

* 确保提前沟通预计会出现的任何流量尖峰。延迟会直接影响数据馈送的处理时间。 请参 [阅管理员用户指南中](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) ，计划流量尖峰。
* 除非您与Adobe的合同中明确规定，否则数据源不包含服务级别协议。 馈送通常在报告窗口通过后的几小时内交付，但有时可能需要12小时或更长时间。
* 确保您的 FTP 站点拥有充足的空间。定期从目标位置删除文件，这样您就不会因疏忽而用尽磁盘空间。
* 使用多个文件交付流程的每小时源速度最快。 如果组织高度重视及时交付，请考虑使用每小时多个文件源。
* 如果使用sFTP，请勿读取或删除带后缀的 `.part` 文件。 后缀 `.part` 表示文件已部分传输。 传输文件后，后缀 `.part` 消失。
* 如果自动化了信息源摄取过程，请考虑一个文件可以多次传输的可能性。 用户可以重新发送重复文件，Adobe很少重新发送重复文件。
