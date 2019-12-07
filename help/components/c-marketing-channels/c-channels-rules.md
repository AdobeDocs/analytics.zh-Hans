---
description: 先创建渠道和用于处理数据的基础规则，然后渠道和渠道数据才能显示在报表中。您还可以创建相关渠道的成本和预算金额，并指定您希望访客参与时间持续多久。在“管理工具”中执行报表配置任务。
subtopic: Marketing channels
title: 关于渠道和规则
topic: Reports and analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 关于渠道和规则

先创建渠道和用于处理数据的基础规则，然后渠道和渠道数据才能显示在报表中。您还可以创建相关渠道的成本和预算金额，并指定您希望访客参与时间持续多久。在“管理工具”中执行报表配置任务。

渠道可以看作是一个收集访问的容器。规则把访问分配到正确的容器中。

![](assets/buckets_2.png)

Adobe 在[自动设置](/help/components/c-marketing-channels/c-channel-autosetup.md)过程中提供了多个预定义渠道，您可以根据自己的需要对这些渠道进行编辑。

>[!NOTE]
>
>Adobe 建议您在可作为测试用模板的报表包中设置报表。您可以使用该模板将这些渠道和规则集全局应用到一个或多个生产报表包中。
>
>请参阅[将模板报表包设置应用于多个报表包](/help/components/c-marketing-channels/t-template.md)。

请查阅以下主题：

* [先决条件](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [重要的处理说明](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## 先决条件 {#prereqs}

如有必要，请联系客户支持来帮助您实现这些先决条件：

* 在“管理控制台”（“一般帐户设置”）中，启用报表包的&#x200B;**[!UICONTROL 转化级别]**（电子商务）选项。

   有关详细信息，请参阅 Analytics 帮助中的[一般帐户设置](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html)。

* 设置用户群组对&#x200B;**[!UICONTROL 营销渠道报表]**&#x200B;的访问权限。

   请参阅[配置用户群组访问权限](/help/components/c-marketing-channels/t-user-groups.md)。

* 确保您的帐户管理员已经为您的报表包启用 了&#x200B;**[!UICONTROL 渠道报表]**。

## 重要的处理说明 {#important-proc-rules}

* 系统会按您指定的顺序处理规则，当一个规则得到满足时，系统会停止处理剩余规则。
* 规则可以访问已由 VISTA 设置的变量，但不能访问已被 VISTA 删除的数据。
* 渠道只存储转化量度。流量量度不可用。
* 两个营销渠道从不会接收相同事件的信用，如购买或点击次数。在这方面，营销渠道不同于 eVar（两个 eVar 可能会接收相同事件的信用）。
* 该报表一次最多可处理 25 个渠道。

