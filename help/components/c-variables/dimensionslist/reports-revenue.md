---
description: 测量您所有的产品在特定时段内产生的收入量。
seo-description: 测量您所有的产品在特定时段内产生的收入量。
seo-title: 收入
solution: Analytics
title: 收入
topic: 报表
uuid: e5b72798-f5 c7-440d-a62 d-376bfd115 ac8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 收入

测量您所有的产品在特定时段内产生的收入量。

使用“收入”可查看网站的大致成功和趋势情况。您还可以使用它选出贵网站在哪些时段内尤其成功，并找到相关资源，然后将其用于未来的促销活动。

## 报表的常规属性 {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* 要使此报表能够成功收集数据，必须满足一定的要求。在同一个图像请求内必须发生以下情况：

   * 必须触发一个[!UICONTROL 购买]事件（在`s.events` 变量中设置。

   * `products` 必须在价格字段中定义变量。
   * 例如，这将向收入报表中传递 $35.99。

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* 当 [!UICONTROL s.products] 变量中存在不止一个产品时，则所有对象都将计入收入报表。For example, [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] would pass $9 in revenue to reporting.

   >[!NOTE]
   >
   >如果在单一产品中数量增加，收入不会乘以。For example, [!DNL s.products="Womens;Socks;5;4.50"] does not pass $22.50 into reporting, it passes $4.50. Make sure your implementation passes the total revenue for the quantity listed ( [!DNL s.products="Womens;Socks;5;22.50"]).

* “[!UICONTROL 收入]”会将某时段的总收入量四舍五入至最接近的货币值。它不会对每一个单独的产品或每一次点击进行四舍五入。
* 由于 Analytics 会将每日收入四舍五入至最接近的整数货币值，因此每日收入量之和与每月总收入量相比较，会有极微小的出入。这是因为每月总收入量并非是经过四舍五入的每日收入量之和，而是将绝对总和四舍五入到最接近的整数货币值。
* 您可以使用[计算量度](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/)创建一个报表，该报表不会将收入量四舍五入到最接近的整数货币值。
* 除非使用 `purchaseID` 变量，否则用户在刷新页面时会使收入虚增，因为它会将此数据多次发送至 Adobe。
* 小时划分是基于报表包的时区。
* 此报表不包含行项目。它只能以趋势格式查看。
* 可应用“小时”、“日”、“周”、“月”、“季”和“年”粒度。这些粒度的可用性取决于报表日期范围。
* 此报表可通过以下报表划分（取决于组织和报表包设置）：

   * [!UICONTROL 每次访问逗留时间]报表。
   * [!UICONTROL 页面和网站区域]报表。
   * [!UICONTROL 视频]报表。
   * [!UICONTROL 页面深度和登录页面]报表。
   * 大部分[!UICONTROL 流量源]报表，包括[!UICONTROL 搜索关键词]、[!UICONTROL 搜索引擎]和[!UICONTROL 反向链接域名]报表。

   * [!UICONTROL 跟踪代码]报表和所有关联的分类报表。
   * [!UICONTROL 产品变量]报表和所有关联的分类报表。还有[!UICONTROL 类别]报表。

   * 几乎所有[!UICONTROL 访客资料]报表，不包括[!UICONTROL 地域划分]报表。

   * 所有具有基本子关系的[!UICONTROL 自定义转化]报表。

* 未提供按小时的划分。

## 产品特定的属性 {#section_ED87FFD020634453AABE86B0248BE69B}

* This report can be accessed by going to **[!UICONTROL Conversion]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* [!UICONTROL 流量源]划分可在[!UICONTROL “查找方法”]下方找到。

* This report can be accessed by going to **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* 除前面提到的所有划分外，还提供[!UICONTROL 首次联系和最近联系营销渠道]划分。

* This report can also be accessed by going to **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* 除了之前提到的划分之外，还可使用[!UICONTROL 列表]变量和当前[!UICONTROL 视频]变量。

* 此报表可使用区段。

* 您可按所有其他报表和变量划分此报表中的每个项目，因此可按您希望的任何粒度显示划分结果。
* 您可以随[!UICONTROL 收入]一起使用所有[!UICONTROL 转化]和[!UICONTROL 流量]量度。您可以对所有[!UICONTROL 转化]量度进行不同的分配。

* 此报表可使用多个非常高级的区段。

如果该报表不在默认位置，请咨询您的管理员。他们可能为了更好地满足贵组织的独特需求，而更改了默认名称或菜单结构。
