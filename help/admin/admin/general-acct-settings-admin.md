---
description: 对“管理员”中报表包“一般帐户设置”的字段描述。
title: 一般帐户设置
topic: Admin tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
translation-type: tm+mt
source-git-commit: aa8a82576d6790d3592767960d864eb58f482eec
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 97%

---


# 一般帐户设置

对“管理员”中报表包“一般帐户设置”的字段描述。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 一般帐户设置]**

这些设置包含基本报表包功能的编辑选项，例如名称和时区。

| 选项 | 描述 |
|--- |--- |
| 网站标题 | 标识您的网站。为每个报表包提供一个唯一的网站标题。 |
| 基本 URL | 指定报表包的主网站。由于基本 URL 不影响反向链接过滤。请改为使用[内部 URL 过滤器](/help/admin/admin/internal-url-filter-admin.md)。 |
| 时区 | 确定与报表数据相关联的日期和时间。更改实时报表包的时区会在报表数据中产生尖峰或间隙。为了尽可能减少影响，Adobe 建议在非高峰时间更改时区以免影响数据的准确性。例如，如果在 3:00pm 将报表包时区从中部时间改为太平洋时间，报表包的当前时间将变为 1:00pm。由于报告已经收集了 1:00 的数据，因此报表会在 1:00pm 到 3:00pm 之间出现流量尖峰。或者，如果在 3:00pm 将报表包时区从中部时间改为东部时间，报表包的当前时间将变为 4:00pm。报表显示在更改时间当天 3:00pm 到 4:00pm 没有数据。 |
| 默认页面 | 如果[!UICONTROL 最受欢迎页面]报表包含 URL 而不是页面名称，则此设置可以防止多个 URL 表示同一网页。例如，URL `https://mysite.com` 和 `https://mysite.com/index.html` 通常是同一网页。您可以删除默认的文件名，使这两个 URL 都显示为 `https://mysite.com`。若留为空白，将从 URL 中删除以下文件名：index.htm、index.html、index.cgi、index.asp、default.htm、default.html、default.cgi、default.asp、home.htm、home.html、home.cgi 和 home.asp。要完全禁止删除文件名，请输入一个永远不会出现在您 URL 中的值。 |
| 将 IP 地址的最后八位字节替换为 0 | 删除最后八位字节在 IP 过滤之前完成。这样，最后八位字节将被替换为 0，并且应当更新 IP 排除规则以匹配末尾为 0 的 IP 地址。匹配 * 应当匹配 0。选中此选项表示在处理 IP 地址之前先对它进行更改。例如，IP 地址 134.123.567.780 更改为 134.123.567.0。地域划分数据不会像使用整个 IP 地址时那样精确。具体而言，相对于国家或地区的准确度，城市准确度会受到更大的影响。机器人规则和 VISTA 规则均会受到影响，因为这些功能不能使用完整的 IP 地址。此外，基于 IP 的所有处理规则均受此设置影响，包括营销渠道规则和报表包处理规则。 <br> **注意**：对于 2019 年 1 月之后在伦敦数据中心创建的所有新报表包，默认情况下都会启用这项设置，但前提条件是这些报表包的设置是从 Admin Console 中列出的模板复制的。设置复制自其他报表包的报表包将继承选定报表包的所有设置。 |
| IP 模糊处理 | 将 IP 地址转换为不可识别的字符串，实质上是将它们从 Adobe 数据存储库中删除。启用“IP 模糊处理”后，原始 IP 地址将永久丢失。 <br> **注意**：IP 地址在 Analytics 中的所有地方均被模糊处理，包括 Data Warehouse。但是，Target 中的 IP 设置是单独控制的，因此该设置不对 Target 产生任何影响。<br>如果启用了 IP 模糊处理，则在 IP 地址被模糊处理之前会进行 IP 排除，这样客户就无需在启用 IP 模糊处理时更改任何内容。<br>选中&#x200B;**禁用**&#x200B;会保留数据中的 IP 地址。<br>选中&#x200B;**模糊处理 IP 地址**&#x200B;会将 IP 更改为哈希值（例如，234abc6493872038）。<br> 选 **中“删除** IP地址”后，数据中的x.x.x.x将替换该IP地址。 <br> **注意**：此设置可能会要求对自定义的[机器人规则](/help/admin/admin/bot-removal/bot-rules.md)或 [IP 排除](/help/admin/admin/exclude-ip.md)进行更改。 |
| 交易 ID 存储 | 可让您使用[交易 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md) 数据源。 |
| 激活 Ad Hoc Analysis | 指示所涉及的报表包是否显示为 Ad Hoc Analysis 中的可用报表包。使用此设置可限制哪些报表包显示为 Ad Hoc Analysis 的选项。例如，您可以对开发和 QA 报表包禁用 Ad Hoc Analysis。 |
| 启用 Data Warehouse | 在“Analytics”>“工具”>“Data Warehouse”下启用 Data Warehouse UI。 |
