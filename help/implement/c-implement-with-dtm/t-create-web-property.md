---
description: Web 属性可以是包含在一个嵌入代码中且具有规则库的一个或多个域和子域的任意组合。
keywords: Analytics实施；实施方法；动态标签管理；dm；web属性；property
seo-description: Web 属性可以是包含在一个嵌入代码中且具有规则库的一个或多个域和子域的任意组合。
seo-title: 创建Web属性
solution: Analytics
title: 创建Web属性
topic: 开发人员和实施
uuid: f19d5504-eb4-4d93-a387-7470ab4 b3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a3 a
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# 创建Web属性

Web 属性可以是包含在一个嵌入代码中且具有规则库的一个或多个域和子域的任意组合。

>[!NOTE]
>
>只有具有管理员权限的用户才能创建属性。For more information about roles, see [Create and Manage Groups in DTM](https://marketing.adobe.com/resources/help/en_US/dtm/groups.html) in the Dynamic Tag Management Product Documentation.

您可以使用 DTM 管理和跟踪这些资产。例如，假定您有多个基于一个模板的网站，并希望在所有这些网站中跟踪相同的资产。您可以将一个 Web 属性应用于多个域。

有关 Web 属性和最佳实践的一般信息，请参阅[动态标签管理产品文档中的Web属性](https://marketing.adobe.com/resources/help/en_US/dtm/web_property.html) 。

1. Navigate to your company page, then click **[!UICONTROL Add Property]**.

   ![](assets/dtm-create-web-property.png)

1. 填写以下字段：

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 元素 </th> 
    <th colname="col2" class="entry"> 描述 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol">名称</span> </td> 
    <td colname="col2"> <p>属性的名称。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol">URL</span> </td> 
    <td colname="col2"> <p>属性的基本 URL。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 此网站跨多个域 </span> </td> 
    <td colname="col2"> <p>如果您希望访客数据在各域之间持续保留，可以添加和删除域。如果选择此选项，则访问数据将在各域间持续保留。 </p> <p>此设置允许您指定要如何跟踪在关联子域或域之间流动的流量。指向子域的链接被当作出站链接处理。因此，会单独跟踪对子域的访问。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. （可选）配置[!UICONTROL 高级设置]。

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 元素 </th> 
    <th colname="col2" class="entry"> 描述 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 允许多规则批准</span> </td> 
    <td colname="col2"> <p>允许一次批准此属性的多个规则。默认的批准设置仅允许批准一个规则。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 启用选择性发布</span> </td> 
    <td colname="col2"> <p>指定是否允许用户选择要发布哪些已批准的规则。这是默认选项。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 跟踪 Cookie 名称</span> </td> 
    <td colname="col2"> <p>覆盖默认跟踪 Cookie 名称。您可以自定义动态标签管理用来跟踪您的退出状态的名称，以便接收其他 Cookie。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 标记超时</span> </td> 
    <td colname="col2"> <p>指定动态标签管理在超时和取消标签请求之前等待标签触发的时间。 </p> <p> 鉴于动态标签管理的工作原理，您无需担心此超时时间值过高。DTM 提供了一些有效的方法来确保慢速标签不会影响用户体验。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 锚记延迟</span> </td> 
    <td colname="col2"> <p>指定动态标签管理在等待标记在点击链接上触发时经过多长时间，才移至下一个页面。默认值为 100 毫秒。 </p> <p>较长的延迟可提高跟踪准确性。Adobe 建议将延迟设置为等于或少于 500 毫秒，用户将不会察觉到这段延迟。 </p> <p>动态标签管理将等待指定的时间，但如果信标先行触发，则延迟会被缩短。（也就是说，用户并不会总是等待延迟的全部时长。） </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Create Property]**.
