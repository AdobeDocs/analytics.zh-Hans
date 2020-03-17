---
description: 文件下载有助于了解访客从您的网站下载文件的频度。文件下载可包括文字处理器文档、电子表格、音频文件、视频文件和用户手册等。其中包括直接从浏览器保存和打开的文件，以及保存到用户计算机的文件。此报表显示下载文件的名称，包含访问该文件所需的完整 URL。
title: 文件下载
topic: Reports
uuid: 897fc221-aa30-4eac-aca6-bccb76adaf71
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 文件下载

文件下载有助于了解访客从您的网站下载文件的频度。文件下载可包括文字处理器文档、电子表格、音频文件、视频文件和用户手册等。其中包括直接从浏览器保存和打开的文件，以及保存到用户计算机的文件。此报表显示下载文件的名称，包含访问该文件所需的完整 URL。

**导航**

**[!UICONTROL 报表]** > **[!UICONTROL 网站内容]** > **[!UICONTROL 链接]** > **[!UICONTROL 文件下载]**

如果该报表不在默认位置，请咨询您的管理员，他们可能已更改了默认菜单结构，以更好地满足您组织的独特需求。

使用该报表可以：

* 确定您网站中下载最频繁的文件。
* 了解某些文件在特定时段内下载的次数是否更多。
* 验证是否需要指定文档的所有格式。

   例如，或许您正在将用户手册翻译成十二种语言，并通过您的网站提供这些手册。使用文件下载报表，您可以了解下载每个用户手册版本的频度，评估是否有必要继续将用户手册翻译成全部十二种语言。

**故障诊断**

市场营销报告从包含 JavaScript 代码的网站上的任意页面捕获下载文件的相关信息。但是，特定变量必须存在并经过正确设置，才会报告文件下载信息。如果报表无法显示数据或无法显示预期的值，请按照以下步骤验证您的实施。

1. 在您的网站上找到全局 JavaScript 文件。该文件通常名为 [!DNL s_code.js]，但可能已被重命名。如果该文件已被重命名，则您可以在站点上搜索值 *`s.account`* 的 JavaScript 文件，此值是 JavaScript 代码的一部分。

1. 在文件中找到 [s.trackDownloadLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackdownllinks.html) 变量。确保将其设置为 *true*。

1. 找到 [s.linkDownloadFileTypes](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkdownfiletypes.html) 变量。确保所需的所有文件扩展名都出现在列表中。如有必要，请添加缺少的扩展名，例如 [!DNL .zip]、[!DNL .pdf] 等。

如果这些变量配置正确，但[!UICONTROL 文件下载报表]仍无法接收数据，则贵组织的受支持用户应与客户关怀团队联系。
