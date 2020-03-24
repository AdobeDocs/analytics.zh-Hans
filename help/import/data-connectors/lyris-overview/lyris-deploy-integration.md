---
description: 描述三步部署流程。
title: 部署集成
uuid: a3c0ef21-ed9a-44d7-bdce-19b3bd5b8b80
translation-type: ht
source-git-commit: a3aa8feb937e2a1f40c498aa4e143de21cf26b86

---


# 部署集成{#deploying-the-integration}

描述三步部署流程。

部署此集成的流程非常简单，只需执行以下操作：

## 完成集成向导{#completing-the-integration-wizard}

使用集成向导的步骤。

要激活集成，必须在 Data Connectors 界面中完成 Lyris 配置向导。

1. 导航到 Adobe Experience Cloud 中的“Data Connectors”（以前称为 Genesis）区域。

   ![](assets/data_connectors.png)

1. 在&#x200B;**[!UICONTROL 添加集成]**&#x200B;中的“Lyris HQ”下，单击&#x200B;**[!UICONTROL 激活]**。

   ![](assets/add_integration.png)

1. 在&#x200B;**[!UICONTROL 常规设置]**&#x200B;下，选择所需的报表包并提供集成的名称。
1. 在&#x200B;**[!UICONTROL 自定义值]**&#x200B;下，填写所有与您的 Lyris 帐户相关的信息。

   ![](assets/general_settings.png)

1. 从下拉菜单中选择适当的保留 eVar 和事件。

   ![](assets/variable_mapping.png)

1. 除了 3 个自动提供的合作伙伴区段外，您还可以在&#x200B;**[!UICONTROL 您的区段]**&#x200B;下选择自己的区段。
1. 此集成可能需要将几个数据点下载到您的 Lyris 帐户。您可以在&#x200B;**[!UICONTROL 访问请求]**&#x200B;下选择授予此访问权限。
1. 在&#x200B;**[!UICONTROL 数据收集]**&#x200B;下，您可以选择使用自动或手动解决方案（JavaScript 插件）从登陆页面 URL 中收集查询字符串参数。如果您选择使用自动解决方案，请输入消息 ID 和收件人 ID 的查询字符串参数。有关 JavaScript 插件，请联系您的 Adobe 顾问。

   ![](assets/data_collection.png)

1. 您可以选择自动为您生成 Lyris 功能板和书签。

   ![](assets/dashboard_generation.png)

1. 查看集成摘要并单击&#x200B;**[!UICONTROL 激活]**。

## Lyris EmailLabs 中的配置{#configuration-within-the-lyris-emaillabs}

介绍完成向导后要在 Lyris 中配置的项目的步骤。

1. 完成集成向导后，您必须与 Lyris 专业团队合作，以完成与 Lyris HQ 帐户的集成并开展测试。
1. 添加 URL 查询字符串参数：验证 URL 附加字符串是否已正确输入到用户界面的“组织”设置区域中。它应当包含促销活动级别 ID (hq_m) 和收件人级别 ID (hq_v)。

   以下是字符串 ID 的一个示例：

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >如果要应用 Lyris 的本机分析工具，请单击所有添加的必需变量的“跟踪”**&#x200B;标记。

## 验证集成{#verifying-the-integration}

验证 Lyris/Adobe Analytics 集成是否成功的步骤。

完成所有部署步骤后，您可以验证集成是否可成功传输数据。

> [!NOTE] 需要几天时间才能开始交换数据。请确保在激活集成后联系 Lyris。

1. 导航到 Data Connectors 中的 Lyris 集成。在&#x200B;**[!UICONTROL 支持]**&#x200B;选项卡 > **[!UICONTROL 集成活动日志]**&#x200B;下，您应会看到诸如&#x200B;**[!UICONTROL 已成功导入量度数据]**&#x200B;和/或&#x200B;**[!UICONTROL 已成功导入分类数据]**&#x200B;等事件：

   ![](assets/integration_info.png)

1. 现在，查看包含相应量度的 Lyris 消息报表。在 Adobe Experience Cloud 中，选择 **[!UICONTROL Reports &amp; Analytics]**。
1. 选择适当的报表包。
1. 在&#x200B;**[!UICONTROL 自定义转化]**&#x200B;下，选择&#x200B;**[!UICONTROL 消息 ID 报表]**，然后选择&#x200B;**[!UICONTROL 消息 ID/消息名称]**。

## 查询字符串参数插件代码{#query-string-param-plug-in-code}

显示要与 Adobe Analytics 一起使用的 Lyris 插件代码。

> [!NOTE] 在使用以下代码之前，请确保在 Adobe Analytics 的管理员工具中保留了必需的 eVar。在获知保留了哪些 eVar 之后，请使用相关 eVar 替换 eVarN。例如，eVar10。

```
/* 
  * Plugin: getQueryParam 2.3 
  */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/*in the s_doPlugins function - Replace N with actual eVar number*/ 
s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Message ID in eVarN variable s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Recepient ID in eVarN variable 
```
