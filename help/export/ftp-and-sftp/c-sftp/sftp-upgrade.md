---
title: SFTP 服务升级 — 常见问题解答
description: 有关计划进行的 SFTP 服务升级的常见问题解答。
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 100%

---

# SFTP 服务升级 — 常见问题解答

Adobe Analytics 将于 2022 年 9 月 20 日升级其安全文件传输协议 ([SFTP]) 服务，以增强文件传输的安全性。作出此更改后，将不再支持某些 SFTP 客户端配置。这将仅影响使用 SFTP 发送到 Adobe Analytics 或从其检索的数据。而不影响 FTP 协议。为避免服务中断，请确保您的 SFTP 客户端（代码、工具、服务）与下文详述的更改一致。

## 如何确定我所在的组织当前使用何种算法、连接类型和协议？

所使用的 FTP/SFTP 软件应指示在配置为与 Adobe Analytics 交换数据的连接中使用了什么具体设置。此软件还应包括有关对于连接可用的各种选项的文档。在此更新之后支持的选项在业内受到广泛支持和认可。

一般将删除的连接选项视为过时，并在当前的软件中不使用这些选项。如果过去三年内升级过 FTP/SFTP 软件，则连接可能已符合要求。

## 哪些 Adobe Analytics 功能使用 SFTP 引入数据？

以下功能可使用 SFTP 将数据上传到 Adobe Analytics。

* [分类](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html?lang=zh-Hans)

* [客户属性](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=zh-Hans)

* [数据馈送](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [数据源](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Data Warehouse 传送的报表](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* 此外，通过[工程技术服务](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html)创建的某些自定义实现可使用 SFTP 与 Adobe 交换数据。

## 此更新将包含哪些具体更改？

下方详细列出将删除和将支持的连接和算法：

* SFTP 协议 mac 算法：

   * 我们将不再支持：hmac-md5、hmac-md5-96、hmac-ripemd160、hmacripemd160@openssh.com、hmac-sha1、hmac-sha1-96、hmac-sha1-etm@openssh.com、umac-64-etm@openssh.com、umac-64@openssh.com

   * 我们将仅支持：hmac-sha2-512-etm@openssh.com、hmac-sha2-256-etm@openssh.com、umac-128-etm@openssh.com、hmac-sha2-512、hmacsha2-256、umac-128@openssh.com

* SFTP 协议密码算法：

   * 我们将不再支持：3des-cbc、aes128-cbc、aes128-gcm@openssh.com、aes192-cbc、aes256-cbc、aes256-gcm@openssh.com、arcfour、arcfour128、arcfour256、blowfish-cbc、cast128-cbc、rijndael-cbc@lysator.liu.se

   * 我们将仅支持：aes128-ctr、aes192-ctr、aes256-ctr

* SFTP 协议支持的连接：

   * 我们将不再支持通过 sftp 协议使用 scp 和 rsync 命令或连接

   * 我们将仅支持纯 SFTP 协议连接

* 支持的 FTP/SFTP 客户端/协议：

   * FTP：vsftpd 版本 3.0.2-25 或更高版本

   * SFTP：openssh 版本 7.4p1-21 或更高版本
