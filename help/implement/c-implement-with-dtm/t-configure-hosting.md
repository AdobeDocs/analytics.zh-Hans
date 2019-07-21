---
description: 您可以使用一个或多个可用托管选项来部署动态标签管理。
keywords: Analytics实施；实施方法；动态标签管理；dm；托管；托管选项；Akamai；自助托管；自助托管；ftp交付；ftp托管；库下载
seo-description: 您可以使用一个或多个可用托管选项来部署动态标签管理。
seo-title: 配置托管选项
solution: Analytics
title: 配置托管选项
topic: 开发人员和实施
uuid: 04268f2d-e76 f-4fe4-8cfc-f0 db016502
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 配置托管选项

You can deploy [!UICONTROL Dynamic Tag Management] using one or more of the available hosting options.

[!UICONTROL 动态标签管理提供了多个用于托管所需 JavaScript 文件的选项。]

有关托管的详细信息，请参阅“动态标签管理产品文档”中的[嵌入代码和托管选项](https://marketing.adobe.com/resources/help/en_US/dtm/deployment.html)。

在“嵌入”选项卡中，选择一个托管选项。

<table id="table_229298207DB64838B6F2477DFFAE073F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 托管选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 实施 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Akamai </p> </td> 
   <td colname="col2"> <p> 最便于实施的托管选项。 </p> <p>全局分布式提交网络。 </p> <p>添加其他第三方基础环境依赖关系（DNS 查找、Akamai 可用性）。 </p> <p>有关更多详细信息，请参阅“动态标签管理产品文档”中的 <a href="https://marketing.adobe.com/resources/help/en_US/dtm/akamai.html" format="html" scope="external">Akamai</a>。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_EF148EF091A645B3962B084963B3C0B0"> 
     <li id="li_7ECE0C331EEE4907A563D581DF1DFEFE">动态标签管理生成自定义 JavaScript 库。 </li> 
     <li id="li_8E2C858290EF4665B2F45ACAFA121CB3">动态标签管理将自定义 JavaScript 库导出至 Akamai。 </li> 
     <li id="li_CE88B10B6E844A56BBB8C575A9363BA9">目标网站直接在页面级别引用 Akamai 托管的动态标签管理库。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自托管：FTP 交付 </td> 
   <td colname="col2"> <p><span class="term"> 一</span> 种推送方法，因此动态标签管理通过FTP协议将自定义JavaScript库直接导出到Web内容服务器主机。 </p> <p>此解决方案要求 Web 内容服务器上有可用的 FTP 服务器和凭据，以便将更改发布到自定义动态标签管理库。 </p> <p>有关更多详细信息，请参阅“动态标签管理产品文档”中的 <a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_ftp.html" format="html" scope="external">FTP</a>。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_60348F9C991D4F2B9457006B0F98C834"> 
     <li id="li_24A141C3C7074BF9897C022A22CAE78C">动态标签管理生成自定义 JavaScript 库。 </li> 
     <li id="li_E1E0843060F7447E853EA416A0B033BE">动态标签管理将自定义 JavaScript 库经由 FTP 导出至主机服务器。 </li> 
     <li id="li_EAF5D2ABD03B4911A0CFA464AD8791CE">目标网站可在本地引用自定义动态标签管理库。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自托管：库下载 </td> 
   <td colname="col2"> <p><span class="term"> 拉取</span> 方法，即应用程序导出自定义JavaScript库 <!-- to Amazon S3-->。这样，这些库就可以由托管的服务器端进程进行访问。 </p> <p>另外，这些库可通过 Web 下载直接从动态标签管理界面获取。 </p> <p>此解决方案要求手动检索并发布动态标签管理库，或者创建一个可将库从 Akamai 提取到 Web 内容服务器的自动化进程。 </p> <p>此方法在设置上最耗时，但也是最安全灵活的选项。 </p> <p>要检查引用的是否是库文件的最新版本，请使用相应命令 </p> <p>有关更多详细信息，请参阅“动态标签管理产品文档”中的<a href="https://marketing.adobe.com/resources/help/en_US/dtm/deployment_download.html" format="html" scope="external">库下载</a>。 </p> </td> 
   <td colname="col3"> 
    <ol id="ol_F40B721306FE473496BD657262DFD585"> 
     <li id="li_4EA4D6B555CE4E9CA476C7550C18C061">动态标签管理生成自定义 JavaScript 库。 </li> 
     <li id="li_BA40EBD7AD1546F29D8A209034D06477">动态标签管理将自定义 JavaScript 库导出至 Akamai。 </li> 
     <li id="li_E107E69E386A40F3B067F9991C2979AF">自定义动态标签管理库通过手动或编程方式移至 Web 内容服务器。 </li> 
     <li id="li_0809038453B544168A20CE09D7E5AC59">目标网站可在本地引用自定义动态标签管理库。 </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

您可以同时使用多个托管选项。例如，您可以使用 Akamai 托管暂存文件，但同时使用自托管方式托管您的生产站点。请注意，每个托管类型都有自己的嵌入代码，而一个页面上只能添加一个嵌入代码。
