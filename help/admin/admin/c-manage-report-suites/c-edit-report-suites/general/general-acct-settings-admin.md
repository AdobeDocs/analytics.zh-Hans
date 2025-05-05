---
description: 对“管理员”中报表包“一般帐户设置”的字段描述。
title: 一般帐户设置
feature: Admin Tools
uuid: c1ab5c34-2c41-4d12-a706-0e760dff8a95
exl-id: f49babb2-8e26-4cc6-b264-b4d7be93f130
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 83%

---

# 一般帐户设置

对“管理员”中报表包“一般帐户设置”的字段描述。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL 常规]** > **[!UICONTROL 一般帐户设置]**

这些设置包含基本报表包功能的编辑选项，例如名称和时区。


>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [为演示视频配置常规帐户设置](https://video.tv.adobe.com/v/3411504/?quality=12&learn=on&captions=chi_hans){target="_blank"}。

>[!ENDSHADEBOX]

| 选项 | 描述 |
|--- |--- |
| 网站标题 | 标识您的网站。为每个报表包提供一个唯一的网站标题。 |
| 基本 URL | 指定报表包的主网站。由于基本 URL 不影响反向链接过滤。请改用[内部URL过滤器](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)。 |
| 时区 | 确定与报表数据相关联的日期和时间。更改实时报表包的时区会在报表数据中产生尖峰或间隙。为了尽可能减少影响，Adobe 建议在非高峰时间更改时区以免影响数据的准确性。例如，如果在 3:00pm 将报表包时区从中部时间改为太平洋时间，报表包的当前时间将变为 1:00pm。由于报告已经收集了 1:00 的数据，因此报表会在 1:00pm 到 3:00pm 之间出现流量尖峰。或者，如果在 3:00pm 将报表包时区从中部时间改为东部时间，报表包的当前时间将变为 4:00pm。报表显示在更改时间当天 3:00pm 到 4:00pm 没有数据。 |
| 默认页面 | 如果[!UICONTROL 最受欢迎页面]报表包含 URL 而不是页面名称，则此设置可以防止多个 URL 表示同一网页。例如，URL `https://example.com` 和 `https://example.com/index.html` 通常是同一网页。您可以删除默认的文件名，使这两个 URL 都显示为 `https://example.com`。若留为空白，将从 URL 中删除以下文件名：index.htm、index.html、index.cgi、index.asp、default.htm、default.html、default.cgi、default.asp、home.htm、home.html、home.cgi 和 home.asp。要完全禁止删除文件名，请输入一个永远不会出现在您 URL 中的值。 |
| 将 IP 地址的最后八位字节替换为 0 | 启用后，会将IP地址的最后八位字节替换为零。 这种情况发生在填充地理相关的报表之前，因此可能会影响这些报表的准确性。 |
| IP 模糊处理 | 将 IP 地址转换为不可识别的字符串，实质上是将它们从 Adobe 数据存储库中删除。启用IP模糊处理后，原始IP地址将永久丢失。<br> **注意**：IP 地址在 Analytics 中的所有地方均被模糊处理，包括 Data Warehouse。但是，Target 中的 IP 设置是单独控制的，因此该设置不对 Target 产生任何影响。<br>如果启用 IP 模糊处理，所有需要的处理（包括 IP 过滤/排除、机器人规则和地域划分查找）将在模糊处理 IP 地址之前完成。启用 IP 模糊处理时无需更改任何内容。<ul><li>选中&#x200B;**禁用**&#x200B;会保留数据中的 IP 地址。</li><li>选中&#x200B;**模糊处理 IP 地址**&#x200B;会将 IP 更改为两个冒号后跟一个哈希值（例如 `::1932023538`）。</li><li>选中&#x200B;**移除 IP 地址**&#x200B;会在地理查找之后，将数据中的 IP 地址替换为 `::X.X.X.X`。</li></ul>**注意**：此设置可能需要更改自定义[机器人规则](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)或[IP排除](/help/admin/admin/exclude-ip.md)。<br> **注意**：使用Web SDK收集的数据可以通过[数据流配置](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hans#@advanced-options)在Edge Network上应用IP模糊处理。 如果在Edge Network应用了IP模糊处理，则当它到达Analytics时，将处于模糊处理状态。 此模糊处理会影响机器人规则和地理查找。 |
| 交易 ID 存储 | 可让您使用[交易 ID](/help/import/data-sources/transactionid.md) 数据源。 |
| 启用 Data Warehouse | 在“Analytics”>“工具”>“Data Warehouse”下启用 Data Warehouse UI。 |
| 邮政编码选项 | 让您指定邮政编码，而不是使用我们的地理 IP 查找生成的任何内容。 |
| 多字节字符支持 | 多字节字符支持使用 UTF-8 将字符存储在报表包中。系统在接收数据之后会将其从您的网页字符集转换为 UTF-8 字符集，从而使您可以在市场营销报告中使用任何语言。要将现有报表包更改为支持多字节字符，请联系您的 Adobe 客户团队或客户关怀团队。 |
| 已激活 | 指定是否激活此报表包。 |
| 基本货币 | 允许您为此报表包指定基本[货币](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/currencycode.html?lang=zh-Hans)。 |
| 组织 ID | 与您设置的 Experience Cloud 公司关联的 ID。此 ID 是由 24 个字符组成的字母数字字符串，其后跟（且必须包括）@AdobeOrg。 |
