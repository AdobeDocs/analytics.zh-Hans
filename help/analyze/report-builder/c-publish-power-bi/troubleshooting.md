---
description: 将 Report Builder 与 Power BI 一起使用时常见的问题。
title: Power BI 集成疑难解答
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: a30564e9d8969457aaa8709c3aa3c17ba6d0a2d3
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 90%

---

# Power BI 集成疑难解答

研究并解决将 Report Builder 与 Power BI 一起使用时常见的问题。

## 无法发布到 Power BI

要求 Power BI 发布的计划工作簿需要 Power BI 服务启动和运行。发布失败的两个主要原因包括：

* Power BI 服务可能发生故障。
* 计划该工作簿的用户不再拥有有效的 Microsoft 帐户凭据。

每个 Report Builder 计划任务在每次计划运行时都有三次尝试机会：

* 在首次不成功的尝试之后，您将收到以下消息：“无法将此计划工作簿发布到 Microsoft Power BI。我们将稍后再试。”
* 在第二次不成功的尝试之后，您将不会收到消息。
* 在第三次不成功的尝试之后，您将收到以下消息：“无法将此计划工作簿发布到 Power BI。”

## Power BI 中的可视化效果受损

以下是在将 Report Builder 请求发布到 Power BI 后导致可视化中断的几个主要原因：

* 您在 Report Builder 中编辑了请求（例如更改指标或维度），然后重新发布到 Power BI。编辑请求可能中断您的可视化。
* 您删除了可视化中使用的请求。

## 需要授权 Report Builder 才能访问您的组织资源。只有管理员可授予此访问权限。请要求管理员授予您权限。

让一名 Microsoft 管理员查看可在 **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL 用户设置允许选项]**&#x200B;下找到的“用户可注册应用程序”设置。如果此选项被设置为“否”，则该管理员可注册这些类型的应用程序。

用户可使用以下[链接](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)授予用户访问权限。

管理员使用以下[链接](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)授予每个人访问权限。

## 达到API限制

Power BI中的报表可与Analytics报表API配合使用，因此适用API阈值限制。 有关详细信息，请参阅 [API调用的速率限制是多少？](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/#what-is-the-rate-limit-for-api-calls).
