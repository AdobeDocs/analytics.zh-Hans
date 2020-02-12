---
title: 定义渠道
description: 先创建渠道和用于处理数据的基础规则，然后渠道和渠道数据才能显示在报表中。您还可以创建相关渠道的成本和预算金额，并指定您希望访客参与时间持续多久。在“管理工具”中执行报表配置任务。
translation-type: tm+mt
source-git-commit: e080c38e536f710490291aaca252cba36456b0f9

---


# 定义渠道

先创建渠道和用于处理数据的基础规则，然后渠道和渠道数据才能显示在报表中。您还可以创建相关渠道的成本和预算金额，并指定您希望访客参与时间持续多久。在“管理工具”中执行报表配置任务。

渠道可以看作是一个收集访问的容器。规则把访问分配到正确的容器中。

![](assets/buckets_2.png)

Adobe 在[自动设置](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md)过程中提供了多个预定义渠道，您可以根据自己的需要对这些渠道进行编辑。

>[!NOTE]
>
>Adobe 建议您在可作为测试用模板的报表包中设置报表。您可以使用该模板将这些渠道和规则集全局应用到一个或多个生产报表包中。
>
>请参阅[将模板报表包设置应用于多个报表包](/help/components/c-marketing-channels/getting-started/t-template.md)。

## 先决条件 {#prereqs}

如有必要，请联系客户支持来帮助您实现这些先决条件：

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   有关详细信息，请参阅 Analytics 帮助中的[一般帐户设置](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html)。

* 设置对营销渠道维的访问权限。

   See [Marketing Channels permissions](/help/components/c-marketing-channels/mc-access/c-channel-report-access.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## 重要的处理说明 {#important-proc-rules}

* 系统会按您指定的顺序处理规则，当一个规则得到满足时，系统会停止处理剩余规则。
* 规则可以访问已由 VISTA 设置的变量，但不能访问已被 VISTA 删除的数据。
* 渠道只存储转化量度。流量量度不可用。
* 两个营销渠道从不会接收相同事件的信用，如购买或点击次数。在这方面，营销渠道不同于 eVar（两个 eVar 可能会接收相同事件的信用）。
* 该报表一次最多可处理 25 个渠道。

