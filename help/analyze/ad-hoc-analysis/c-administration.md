---
description: 配置用户和了解数据取样。
seo-description: 配置用户和了解数据取样。
seo-title: 管理
title: 管理
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# 管理

配置用户和了解数据取样。

For [!DNL Admin Console] help, see the [Analytics Reference](https://marketing.adobe.com/resources/help/en_US/reference/index.html).

## 用户许可证 {#concept_C1440741C77C471EB38A243B013EA620}

用户在登录前，必须获得用户许可证。用户许可证是并发使用许可证。用户可以共享用户许可证，但在任何给定的时间内，用户数仅限于购买的用户许可证数。

<!-- 

c_user_license.html

 -->

如果登录的用户数超过可用许可证数，则会出现对话框，通知用户所有可用的许可证都已使用。系统将显示队列中的用户位置以及用于确认队列位置的链接。当许可证可用时，用户会收到电子邮件和弹出对话框，提醒用户 Ad Hoc Analysis 已经可以访问。用户有 15 分钟的时间来作出回应，超过此时间便会丧失在队列中的位置。

## 授予用户许可证 {#task_22AE669703EC48BA9685414538D8B1FA}

描述本地 Reports &amp; Analytics 管理员如何通过权限系统授予用户许可证的步骤。

<!-- 

t_user_licenses.xml

 -->

1. 登录到 [!DNL Experience Cloud]。
1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**.
1. Click **[!UICONTROL Edit Groups]**.

   如果贵公司已经购买了用户许可，则[!UICONTROL “Ad Hoc Analysis 授权用户”]组将会出现在[!UICONTROL “群组名称”]列。同时还会显示可供用户登录用的可用许可证数量。

1. Click **[!UICONTROL Edit]**.
1. 在[!UICONTROL 指定用户登录]**下，选择要添加到该组的用户，然后单击[!UICONTROL 添加。]**
1. Click **[!UICONTROL Save Group]**.

   许可系统不会显示添加到组中的用户数量。对于购买的用户许可的数量，存在并用方面的限制。

## 管理用户会话 {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

说明管理员如何终止用户会话的步骤。此功能无法阻止终止的用户再次登录。

<!-- 

t_managing_users.xml

 -->

1. 单击 **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**，然后单击管理用 ****&#x200B;户管理。
1. 找到用户，然后单击&#x200B;**[!UICONTROL 终止]。**

   在“[!UICONTROL 活动 Ad Hoc Analysis 会话]”页面中，空闲最久的用户显示在列表顶部。

## 权限 {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

You set up access to report suites in the [!DNL Administration Console]. 您可以在报表包级别配置权限。例如，如果您启用了多个报表包，但不希望为所有用户授予所有报表包的访问权限，则可以创建包含特定报表包的组，然后将这些用户分配给相应的组。

## 向所有报表访问群组添加用户 {#task_E821BF3B4FDB434D844A98AAB15487A9}

描述如何为非管理员用户授予所有报表包的访问权限的步骤。

<!-- 

t_permissions.xml

 -->

1. Log in to the **[!UICONTROL Experience Cloud]**.
1. Click **[!UICONTROL Adobe Analytics &gt; Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL All Report Access]**.
1. 在**“现有用户”中，选择用户，然后单击“添加”。**
1. Click **[!UICONTROL Save Group]**.

## 创建权限群组 {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

为非管理员用户创建权限组以访问特定报表包。

<!-- 

t_permission_groups.xml

 -->

1. Log in to the **[!UICONTROL Experience Cloud]**.
1. Click **[!UICONTROL Adobe Analytics &gt; Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Edit Groups]**.
1. 创建一个非管理员用户的权限组，在该组中纳入您允许用户访问的活动的 Ad Hoc Analysis 报表包。

   在您创建新项目时，用户可用的报表包会显示在“[!UICONTROL 报表云]”菜单中。

## 在 Java 中设置代理策略 {#task_3B03F58519544025B55CF54FACF8F4F5}

描述如何在出现服务器连接错误时设置代理策略的步骤。

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis 通过 HTTP 与服务器进行通信。可以使用与其他 HTTP 流量相同的代理策略。

1. 在中， [!DNL Windows Control Panel]启动 [!UICONTROL Java控制面板]。
1. On the **[!UICONTROL General]** tab, click **[!UICONTROL Network Settings]**.
1. Select **[!UICONTROL Use browser settings]**, or manually configure the proxy settings.
1. Click **[!UICONTROL OK]**, then click **[!UICONTROL OK]** on the [!UICONTROL Java Control Panel].

## 数据如何采样 {#concept_8433CFD38E0243849E92DF4F1E743AC3}

访客数据的采样用于生成有意义的精确报表。时间范围将作为所加载项目的数据片段。片段通常表示当月和前两个月的数据。

<!-- 

c_overview_data_sampling.xml

 -->

为了优化处理，Ad Hoc Analysis 使用的每个片段的最高点击量大约为 7.5 亿。（点击量 = 页面查看次数 + 事件数量。）

为达到预计的采样率，将计算每个数据集的预计点击量，然后除以 7.5 亿，如下所示：

* （平均每日点击量 x 该数据片段中包含的天数）/750,000,000

例如，如果一天点击量为 10,000,000，数据片段的天数为 90 天：

* (10,000,000 x 90) / 750,000,000 = 1.2

因此，要想将这 90 天片段的点击量保持在 750,000,000 以下，该数据必须按照 1.2:1 采样，但由于 Discover 使用整数进行采样，因此采样率为 2:1。

又如，如果一天点击量为 10,000,000，数据片段的天数为 365 天：

* (10,000,000 x 365) / 750,000,000 = 4.8

因此，要想将这 365 天片段的点击量保持在 750,000,000 以下，该数据必须按照 4.8:1 采样，但由于 Discover 使用整数，因此采样率为 5:1。

>[!MORE_LIKE_THIS]
>
>* [用户](https://marketing.adobe.com/resources/help/en_US/reference/users.html)
>* [群组 ](https://marketing.adobe.com/resources/help/en_US/reference/groups.html)

