---
description: 显示有关访客的信息，包括访客计数、客户忠诚度和访客特征等信息。
seo-description: 显示有关访客的信息，包括访客计数、客户忠诚度和访客特征等信息。
seo-title: 访客报告
solution: Analytics
title: 访客报告
topic: Ad Hoc Analysis
uuid: 3e9b41d1-d6 ff-47a8 e6 b-829df1040 c34
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 访客报告

显示有关访客的信息，包括访客计数、客户忠诚度和访客特征等信息。

## 回访频度 {#concept_447A99B71E484D27A7A02888CC51FD3D}

显示同一访客从初次访问网站到回访之间的时间长度，以及每个时间长度下出现的访问量。使用此报表可查看常客未访问您的网站的平均时间，以及常客的访问趋势。

<!-- 

c_reports_return_freq.xml

 -->

例如，在此报表中显示“订购”量度，可帮助零售网站了解产生转化的两次访问之间间隔的最佳时间长度。使用此信息可向一段时间未访问您的网站的访客有效地进行促销。

您可以：

* 确定回访访客数量和回访频度。
* 评估某段时间内网站对访客的吸引力和实用性。
* 了解您的网站对访客的吸引力如何，以及他们迫切希望回访网站以进一步交互或查看更新内容的频度。
* 确定您的网站内容/促销活动对访客的影响。

在默认情况下，此报表包含以下时间长度：

* 不到 1 天
* 1 至 3 天
* 3 至 7 天
* 7 至 14 天
* 14 天到 1 个月
* 超过 1 个月

## 访问量 {#concept_BBB614072FD74379B1A8520ACB75AE9A}

显示您的网站上对成功量度影响最大的客户访问次数。首次访问您的网站的访客将计入“第 1 次访问”行项目中。返回到网站进行第二次访问的访客将计入“第 2 次访问”行项目中，等等。

<!-- 

c_reports_visit_number.xml

 -->

您可以将此报表用作流失报表来查看访客是否是回头客。您还可以将收入量度添加到此报表，以了解初次访问还是后续访问带来的收入更多。

例如，此报表可以解答以下问题：是否第 4 次访问时购买产品的客户比首次访问时购买产品的客户产生的收入多？

您可以按任何其他报表或变量来划分此报表以确定：

* 点击促销活动 XYZ 的用户通常访问多少次才会进行购买操作。
* 例如，相对于伦敦的用户，东京的用户在购买前访问的次数是否更多.

>[!NOTE]
>
>如果同一访客在同一时间段多次访问您的网站，则每次访问都会递增每个指定的访问次数。

此报表基于访客每次点击时传送到 Adobe 的访客 ID 数据。接收到此数据后，Adobe 会将其与历史访客 ID 数据进行比较以确定此点击是否是：

* 新的访客（访问次数等于 1）。
* 先前的访客持续访问（访问次数未增加）。
* 先前的访客进行了新的访问（访问次数递增 1 次）。

>[!NOTE]
>
>每个Analytics访客ID与Adobe服务器上的访客配置文件相关联。无论任何访客 ID Cookie 是否过期，访客资料在处于至少 13 个月的非活动状态之后会被删除。

## 客户忠诚度 {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

使用此报表可以查看影响您收入的最大因素是新客户还是回头客。

<!-- 

c_reports_customerloyalty.xml

 -->

[!UICONTROL 客户忠诚度]报表根据四项忠诚度类别显示客户的购买类型：

* **不是客户**：从未有过购物的访客
* **新客户**：有过一次购物的访客
* **回头客户**：有过 2 次购物的访客
* **忠诚客户**：有过 3 次及以上购物的访客

>[!NOTE]
>
>使用这些指标时，无论访问(或访客)是否包含购买，都将在此报告中显示所有用户访问(或所有访客)。

忠诚度状态会在发生购物事件的访问结束后更改。例如，新客户（购物 1 次）购物一次，并在此次购物后的同一访问期间订阅了新闻。此次新闻订阅事件仍被视为新客户交互，因为访客的客户忠诚度状态会在下一次访问时更改。

## 访客配置文件 {#concept_4D829198CD144DCDA667E0651F93AFC7}

显示有关网站访客类型的信息。您可查看的信息包括，访客位置及其使用的浏览器和计算机硬件类型、语言及 Internet 服务供应商等数据。

<!-- 

c_reports_visitor_profile.xml

 -->

** [!UICONTROL Languages] **: Displays your visitors’ preferred languages, captures the default browser language, and displays the languages that visitors use most often on your site.

** [!UICONTROL Domains] **: Lists the organizations and ISPs your visitors use to access your site. 此报表与[!UICONTROL 完整域名]报表的不同之处在于，完整域名报表记录完整的 ISP 域，而此报表仅列出二级域。

** [!UICONTROL Top Level Domains] **: Identifies world regions that visitors come from based on their originating domain extension, and shows how many visitors come from these countries. 以商业 (.com)、网络 (.net)、教育 (.edu)、政府 (.gov) 和组织 (.org) 结尾的域通常位于美国，而且与其他域分开列出。

** [!UICONTROL Visitor ZIP/Postal Code] **: Displays the zip and postal codes that produced the customers that had the greatest effect on purchase success metrics.

## 地域划分 {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

实时显示访客的地理动态，包括访客浏览网页时所在国家、省/市/自治区和城市。您还可以对此技术和您的网站受众的喜好有更深入的了解。
