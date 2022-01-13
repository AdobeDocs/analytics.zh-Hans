---
title: SFTP服务升级 — 常见问题解答
description: 有关2022年5月计划升级SFTP服务的常见问题解答。
source-git-commit: eb9bdcbd99d45afc913c5ade37e8fb5c62a3a456
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 2%

---


# SFTP服务升级 — 常见问题解答

开 **2022年5月2日**,Adobe Analytics将升级其安全文件传输协议 [SFTP] 服务，以便为文件传输提供改进的安全性。 在实施此更改后，将不再支持某些SFTP客户端配置。 我们还将添加一些连接选项，这些选项将由 **2022年3月1日**. 这仅会影响使用SFTP发送到Adobe Analytics或从Analytics检索到的数据。 FTP协议将不会受到影响。 为避免服务中断，请确保您的SFTP客户端（代码、工具、服务）将符合以下详细更改。

## 如何确定我的组织当前使用的算法、连接类型和协议？

您使用的FTP/SFTP软件应指示在您配置的连接中使用哪些特定设置来与Adobe Analytics交换数据。 此软件还应包含有关可用于连接的不同选项的文档。 行业广泛支持并接受本次更新后将支持的选项。

## 哪些Adobe Analytics功能使用SFTP进行数据摄取？

以下功能提供了一个选项，可使用SFTP将数据上传到Adobe Analytics。

* [分类](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [数据馈送](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [数据源](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Data Warehouse 传送的报表](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* 此外，通过创建的一些自定义实施 [工程服务](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) 可能使用SFTP与Adobe交换数据。

## 此更新中将包含哪些具体更改？

下面是将删除哪些连接和算法以及将支持哪些连接和算法的详细列表：

* SFTP协议mac算法：

   * 我们将不再支持：hmac-md5、hmac-md5-96、hmac-ripemd160、hmacripemd160@openssh.com、hmac-sha1、hmac-sha1-96、hmac-sha1-etm@openssh.com、umac-64-etm@openssh.com、umac-64@openssh.com

   * 我们只支持：hmac-sha2-512-etm@openssh.com、hmac-sha2-256-etm@openssh.com、umac-128-etm@openssh.com、hmac-sha2-512、hmacsha2-256、umac-128@openssh.com

* SFTP协议加密算法：

   * 我们将不再支持：3des-cbc、aes128-cbc、aes128-gcm@openssh.com、aes192-cbc、aes256-cbc、aes256-gcm@openssh.com、arcfour、arcfour128、arcfour256、blowfish-cbc、cast128-cbc、rijndael-cbc@lysator.liu.se

   * 我们只支持：aes128-ctr、aes192-ctr、aes256-ctr

* SFTP协议支持的连接：

   * 我们将不再支持通过sftp协议使用scp和rsync命令或连接

   * 我们将仅支持纯SFTP协议连接

* 支持的FTP/SFTP客户端/协议：

   * FTP:vsftpd版本3.0.2-25或更高版本

   * SFTP:openssh版本7.4p1-21或更高版本