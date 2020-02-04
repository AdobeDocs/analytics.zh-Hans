---
description: 您可以通过创建 Adobe Analytics 工具并自动或手动配置页面代码，来使用 Dynamic Tag Management 部署 Adobe Analytics。对于大多数用户，建议使用自动方法。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;analytics tool;property;tool type;tool name;configuration method;analytics premium;evars;events
title: 添加 Adobe Analytics 工具
topic: Developer and implementation
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# 添加 Adobe Analytics 工具

您可以通过创建 Adobe Analytics 工具并自动或手动配置页面代码，来使用 Dynamic Tag Management 部署 Adobe Analytics。对于大多数用户，建议使用自动方法。

> [!NOTE] 为了改进访客跟踪，我们强烈建议您启用 [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)。

## 添加 Adobe Analytics 工具 {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Click  **[!UICONTROL *`Web Property Name`*]**>**[!UICONTROL Overview]**>**[!UICONTROL Add a Tool]**>**[!UICONTROL Adobe Analytics]**.

   ![](assets/dtm-add-analytics-tool.png)

1. 填写以下字段：

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>工具类型 </p> </td> 
   <td colname="col2">工具的类型，如 <span class="keyword">Adobe Analytics</span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>工具名称 </p> </td> 
   <td colname="col2">该工具的描述性名称。此名称显示在“<span class="wintitle">概述</span>”选项卡中的“<span class="wintitle">已安装工具</span>”下方。 </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>配置方法 </p> </td> 
   <td colname="col2"> <p> <b>自动</b>（推荐）：使用动态标签管理来管理配置。这种方法可通过 <span class="keyword">Experience Cloud</span> 登录或 Web 服务 ID 来实现 <span class="keyword">Adobe Analytics</span> 报表包的自动同步，同时还可管理 AppMeasurement 代码。 </p> <p>在连接帐户之后，动态标签管理会将 <span class="keyword">Adobe Analytics</span> 报表包 ID 和名称提取到工具配置界面中，这样可以降低用户出现错误的可能性，同时提高工具部署速度。 </p> <p> <p>注意：<span class="wintitle">Adobe Analytics Premium</span> 客户必须选择“<span class="keyword">自动</span>”选项。 </p> </p> <p>填写特定于自动配置的字段： </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>：（默认）使用 <span class="keyword">Experience Cloud</span> 单一登录。指定 Experience Cloud ID 和密码。 </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Web 服务</b>：指定您的 Web 服务用户名和共享密钥。 </p> <p>共享密钥凭据位于<span class="uicontrol">管理员</span> &gt; <span class="uicontrol">公司设置</span> &gt; <a href="https://docs.adobe.com/content/help/en/analytics/admin/company-settings/web-services-admin.html">Web 服务</a>中。 </p> <p>开发人员请参阅<a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api">获取对企业 API 的 Web 服务访问权限</a>，以获得有关获取 Web 服务凭据的帮助。 </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>手动</b>：手动管理 AppMeasurement 代码。您可以从<span class="keyword"></span>管理工具<span class="keyword"> &gt; </span>代码管理器<span class="ignoretag"><span class="uicontrol">下载 </span>Analytics<span class="uicontrol"> </span>AppMeasurement</span> 代码。 </p> <p>单击 <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html">JavaScript（新）</a>，以了解关于从本地下载代码以将其复制并粘贴到<a href="/help/implement/other/dtm/c-aa-tool/library-management.md">库管理</a>中的<span class="wintitle">编辑代码</span>字段中的信息。 </p> <p>填写特定于手动配置的字段： </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>生产帐户 ID：</b>（必需）用于数据收集的生产帐户。对于 Analytics，这是您的报表包 ID。Dynamic Tag Management 会自动在生产和测试环境中安装正确的帐户。 </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>暂存帐户 ID：</b>（必需）用于您的开发或测试环境。对于 Analytics，这是您的报表包 ID。测试帐户可将测试数据与生产数据分开。 </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b> 跟踪服务器：</b>指定关于 跟踪服务器的信息。 </p> <p><span class="wintitle">跟踪服务器</span>和 <span class="wintitle">SSL 跟踪服务器</span>变量用于第一方 cookie 实施，以指定在其中写入图像请求和 cookie 的域。有关更多信息，请参阅<a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html">正确填充 trackingServer 和 trackingServerSecure 变量</a>一文。 </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>SSL 跟踪服务器：</b>指定关于 SSL 跟踪服务器的信息。 </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. 单击&#x200B;**[!UICONTROL 创建工具]**以创建该工具并显示以进行编辑。

   工具显示在“[!UICONTROL 概述]”选项卡的“[!UICONTROL 已安装的工具]”下方。

1. （满足条件时）按照以下链接中的说明（[!UICONTROL 常规]、[!UICONTROL 库管理]、[!UICONTROL 全局变量]、[!UICONTROL 页面查看次数和内容]、[!UICONTROL 链接跟踪]、[!UICONTROL 反向链接和促销活动]、[!UICONTROL Cookie]和[!UICONTROL 自定义页面代码]），根据需要进一步配置工具。

有关此工具的其他信息，请参阅 [Adobe Analytics 工具常见问题解答](/help/implement/faq.md)。

## 编辑现有的 Adobe Analytics 工具 {#section_148B16AF429B4949B06238D90635B726}

您可以编辑现有的 Adobe Analytics 工具，以更改其配置设置。

1. 单击“![](assets/settings_gear.png)概述[!UICONTROL ”选项卡中已安装工具旁的 ] 图标。
1. 根据需要编辑字段。

   下表仅包含与您在创建 Analytics 工具时可用的元素（如上所述）所不同的元素。但是，您可以更改页面上的任何元素，如两张表中所述。

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>启用自动配置 </p> </td> 
   <td colname="col2"> <p>注意：启用此设置会将手动配置的实施更改为<span class="term">配置方法</span>中描述的自动配置方法。 </p> <p>此选项允许动态标签管理自动检索您 <span class="keyword">Adobe Analytics</span> 帐户的配置。 </p> <p>将使用最新的可用 AppMeasurement 代码，并且会在推出新版本时显示升级通知选项。您还可以出于兼容性等原因，根据需要回滚到以前的 AppMeasurement 版本。最多显示五个以前版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>更新凭据 </p> </td> 
   <td colname="col2"> <p>例如，刷新 API 以更新与用户关联的报表包。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. （满足条件时）按照以下链接中的说明（[!UICONTROL 常规]、[!UICONTROL 库管理]、[!UICONTROL 全局变量]、[!UICONTROL 页面查看次数和内容]、[!UICONTROL 链接跟踪]、[!UICONTROL 反向链接和促销活动]、[!UICONTROL Cookie]和[!UICONTROL 自定义页面代码]），根据需要进一步配置工具。
1. 单击&#x200B;**[!UICONTROL 保存更改]**。
