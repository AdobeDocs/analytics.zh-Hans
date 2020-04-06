---
title: 设置广告帐户
uuid: 4e37caa3-e4a5-43ad-97c0-12db62ad5283
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 设置广告帐户

Adobe Analytics管理员可以创建新的广告帐户并将多个帐户映射到多个报表包(1:1、1:Many、Many:Many)。

管理员还可 [以授予非管理员的权限](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) ，以设置广告帐户。

![](assets/aa_accounts.png)

1. 在Adobe Analytics中，导航到 **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**。
1. （仅限首次使用）接受最终用户许可协议的条款。
1. 单击 **[!UICONTROL + Add]**.
1. 此时 [!UICONTROL New Search Engine Account] 将显示对话框：

   ![](assets/aa_new_se_account.png)

1. 请填写以 **[!UICONTROL Search Engine Settings]** 下准则：

   <table id="table_B3BE66B7D4C54766B8FFD2C6DCD657AF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 设置 </th> 
      <th colname="col2" class="entry"> 描述 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>类型 </p> </td> 
      <td colname="col2"> <p>您有 2 个选项：Google AdWords 和 Microsoft Bing Ads。 </p> <p>注意：Microsoft Bing 于 2019 年 3 月 31 日收购了 Yahoo Gemini。因此，现已不再提供 Yahoo Gemini 广告帐户选项。  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>帐户名称 </p> </td> 
      <td colname="col2"> <p>您可以选择将此帐户名称设置为任何适合您的名称。 这是将显示在UI中的帐户的易记名称。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>OAuth令牌 </p> </td> 
      <td colname="col2"> <p>注意：OAuth 是一种针对访问权限委派的开放标准，通常用于授予网站或应用程序访问其他网站上的信息的权限，且无需提供密码。 </p> <p>注意：您会注意到您将被路由到一个第三方 URL (efrontier.com)。Adobe 使用 efrontier 为所有三个搜索引擎启用 OAuth 身份验证过程。 </p> <p>注意：如果您使用的是 Internet Explorer 11（或更早版本），则无法为三个搜索引擎中的任何一个成功检索 Oauth 令牌。请改用其他Web浏览器。 </p> <p>单击<span class="uicontrol"> “检索令牌</span> ”可启动OAuth2身份验证过程。 这意味着将要求您使用凭据登录Google/Bing搜索帐户。 根据您选择的搜索引擎，该过程略有不同： </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google广告词：提供Google帐户ID。 </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing:提供Bing帐户ID和Bing客户ID。 </li> 
        </ul> <p>Refer to <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Locate your Account ID</a> for information on these IDs. </p> <p>成功登录后，OAuth 令牌字段将会显示 
        <systemoutput>
          已检索
        </systemoutput>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. In the **[!UICONTROL Tracking]** section, you provide information on how the Search Engine data is tracked by your Adobe Analytics implementation. 这是向 Adobe Analytics 数据适当增加搜索引擎数据的必要步骤。请填写以 **[!UICONTROL Tracking Settings]** 下准则：

   <table id="table_1AB4E31456E84ABF8209B02058259C4D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 设置 </th> 
      <th colname="col2" class="entry"> 描述 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>类型 </p> </td> 
      <td colname="col2"> 
        <ul id="ul_1C5A0502A4984E57A08417A91CCD6FFE"> 
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol">自动</span>：让 Advertising Cloud 引擎自行决定如何将跟踪参数附加到搜索引擎的跟踪模板/目标 URL。这种方法最简单，但可能不会生成最佳的集成数据集。 <p>重要信息：要在“自动模式”下配置搜索引擎帐户，您需要执行以下操作： 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">“s_kwcid”参数和值将添加到要添加的帐户中的帐户跟踪模板或登陆页URL。 此组件将插入URL末尾。 因此，如果Web服务器要求在URL末尾有特定的key=value对，或者需要更新以支持URL中的任何新key=value对，则可能需要您执行其他操作。 </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">此外，可将关键字作为“s_kwcid”值的一部分插入登录URL，因此，如果关键字包含特殊字符或符号，请确认Web服务器可支持这些字符（通用特殊字符的示例为“广泛匹配已修改”关键字中使用的“+”）。 </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol">手动</span>：让您管理如何将跟踪参数添加到搜索引擎的跟踪模板/目标 URL。<a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md"  >请参考每个搜索引擎的手动跟踪示例</a>。 </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. 在部 **[!UICONTROL Mapping]** 分中，您选择要链接到此搜索引擎帐户的报表包。 在保存广告帐户之前，您需要至少提供一个报告套件。 您可以将多个帐户映射到多个报表包(1:1、1:Many、Many:Many)。 请注意，AMO从搜索引擎中提取的数据只会被复制到任何映射的报表包，因此不会拆分数据。

   >[!IMPORTANT]
   >
   >只有已经[映射到 Experience Cloud 组织](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html)的报表包才可供选择。如果在列出的报表包中未看到您的报表包，请参阅 [Advertising Analytics 疑难解答](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md)。

   根据以 **[!UICONTROL Mapping Settings]** 下准则：

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 设置 </th> 
      <th colname="col2" class="entry"> 描述 </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>报表包 映射 </p> </td> 
      <td colname="col2"> <p>报表包映射确定链接到此搜索引擎帐户的报表包。 换句话说，它决定将搜索引擎数据发送到哪个报表包中。 </p> <p>如果在列出的报表包中未看到您的报表包，则可使用此工具<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html"  >将您的报表包映射到 Experience Cloud 组织</a>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save]**.
1. 保存后，免责声明会显示一列表警告。 系统要求您确认您已阅读并了解本协议。 Click the checkbox, then click **[!UICONTROL OK]**.

   现在，您将进入广告帐户管 [理UI](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)，新创建的帐户应列在该UI中。

>[!NOTE] 您可能需要至少等待 24 小时，搜索引擎数据才会开始填充到您的 Analytics 报表中。

