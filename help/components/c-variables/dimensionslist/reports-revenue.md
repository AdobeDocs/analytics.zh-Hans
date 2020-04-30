---
description: 测量您所有的产品在特定时段内产生的收入量。
title: 收入
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 收入

测量您所有的产品在特定时段内产生的收入量。

使用“收入”可查看网站的大致成功和趋势情况。您还可以使用它选出贵网站在哪些时段内尤其成功，并找到相关资源，然后将其用于未来的促销活动。

## 报表的常规属性 {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* 要使此报表能够成功收集数据，必须满足一定的要求。在同一个图像请求内必须发生以下情况：

   * 事件 [!UICONTROL purchase] 必须在变量中 `s.events` 触发。

   * 必须在价格字段内为 `products` 变量定义一个数字。
   * 例如，这将向收入报表中传递 $35.99。

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* 当 [!UICONTROL s.products] 变量中存在不止一个产品时，则所有对象都将计入收入报表。例如，[!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] 会向报表传递收入 $9。

   >[!NOTE]
   >
   >在单个产品的数量增加的情况下，收入并不会按此倍数增加。例如，[!DNL s.products="Womens;Socks;5;4.50"] 不会向报表传递 $22.50，而是传递 $4.50。请确保您的实施传递了所列数量的总收入 ([!DNL s.products="Womens;Socks;5;22.50"])。

* [!UICONTROL Revenue] 将某个时间段的总金额舍入到最接近的货币值。 它不会对每一个单独的产品或每一次点击进行四舍五入。
* 由于 Analytics 会将每日收入四舍五入至最接近的整数货币值，因此每日收入量之和与每月总收入量相比较，会有极微小的出入。这是因为每月总收入量并非是经过四舍五入的每日收入量之和，而是将绝对总和四舍五入到最接近的整数货币值。
* 您可以使用[计算量度](https://docs.adobe.com/content/help/zh-Hans/analytics/components/calculated-metrics/cm-overview.html)创建一个报表，该报表不会将收入量四舍五入到最接近的整数货币值。
* 除非使用 `purchaseID` 变量，否则用户在刷新页面时会使收入虚增，因为它会将此数据多次发送至 Adobe。
* 小时划分是基于报表包的时区。
* 此报表不包含行项目。它只能以趋势格式查看。
* 可应用“小时”、“日”、“周”、“月”、“季”和“年”粒度。这些粒度的可用性取决于报表日期范围。
* 此报表可通过以下报表划分（取决于组织和报表包设置）：

   * [!UICONTROL Time Spent per Visit] 报表.
   * [!UICONTROL Pages and Site Sections] 报表.
   * [!UICONTROL Videos] 报表.
   * [!UICONTROL Page Depth and Entry Pages] 报表.
   * 大多 [!UICONTROL Traffic Sources]数报告， [!UICONTROL Search Keywords]包括 [!UICONTROL Search Engines]、和 [!UICONTROL Referring Domains] 报告。

   * [!UICONTROL Tracking Code] 报告和所有关联的分类报告。
   * [!UICONTROL Products variable] 报告和所有关联的分类报告。 还有 [!UICONTROL Categories] 报告。

   * 几乎所有 [!UICONTROL Visitor Profile] 报告，不包括 [!UICONTROL GeoSegmentation] 报告。

   * 所有变 [!UICONTROL Custom Conversion] 量报告均具有基本子关系。

* 未提供按小时的划分。

## 产品特定的属性 {#section_ED87FFD020634453AABE86B0248BE69B}

* 可通过以下路径访问此报表： **[!UICONTROL Conversion]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] “barklins”（划分）可在下 [!UICONTROL Finding Methods]找到。

* 可通过以下路径访问此报表： **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* 除了之前列出的所有细分之外， [!UICONTROL First and Last Touch Marketing Channel] 还提供了细分。

* 也可以通过以下路径访问此报表： **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* In addition to the previously mentioned breakdowns, [!UICONTROL List]variables and the current [!UICONTROL Video] variables can be used.

* 此报表可使用区段。

* 您可按所有其他报表和变量划分此报表中的每个项目，因此可按您希望的任何粒度显示划分结果。
* 您可以同时使用 [!UICONTROL conversion] 所有 [!UICONTROL traffic] 指标和指标 [!UICONTROL Revenue]。 You can use different allocation for all [!UICONTROL conversion] metrics.

* 此报表可使用多个非常高级的区段。

如果该报表不在默认位置，请咨询您的管理员。他们可能为了更好地满足贵组织的独特需求，而更改了默认名称或菜单结构。
