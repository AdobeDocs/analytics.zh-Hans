---
description: 对Power BI使用Report Builder时的常见问题。
title: Power BI 集成疑难解答
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 3aae3b00db1d7f720641ed5ccbefd8acc03460e3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 51%

---


# Power BI 集成疑难解答

研究并解决在对Report Builder进行Power BI时的常见问题。

## 发布到 Power BI 失败

要求 Power BI 发布的计划工作簿需要 Power BI 服务启动和运行。发布失败的两个主要原因包括：

* Power BI 服务可能发生故障。
* 计划该工作簿的用户不再拥有有效的 Microsoft 帐户凭据。

每个 Report Builder 计划任务在每次计划运行时都有三次尝试机会：

* 在首次不成功的尝试之后，您将收到以下消息：“无法将此计划工作簿发布到 Microsoft Power BI。我们将稍后再试。”
* 在第二次不成功的尝试之后，您将不会收到消息。
* 在第三次不成功的尝试之后，您将收到以下消息：“无法将此计划工作簿发布到 Power BI。”

## Power BI 中的可视化图表损坏

以下是在将 Report Builder 请求发布到 Power BI 后导致可视化中断的几个主要原因：

* 您在 Report Builder 中编辑了请求（例如更改量度或维度），然后重新发布到 Power BI。编辑请求可能中断您的可视化。
* 您删除了可视化中使用的请求。

## Report Builder需要获得访问组织资源的授权。 此访问权限只能由管理员授予。 要求管理员授予您权限。

让Microsoft Admin查看“用户可以注册应用程序”设置，该设置位于： **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** >用 **[!UICONTROL 户设置允许选项]**。 如果此选项设置为“否”，则管理员可以注册这些类型的应用程序。

用户可以使用以下链接授予访 [问权](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)。

管理员通过以下链接授予了对每个用户的 [访问权限](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)。
