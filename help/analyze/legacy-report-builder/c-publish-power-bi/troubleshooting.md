---
description: 将 Report Builder 与 Power BI 一起使用时常见的问题。
title: Power BI 集成疑难解答
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
TQID: https://experienceleague.adobe.com/Q4n08pGcqBwhUl5q3VnWhuVcW9E-tdvv3LoHSLoGleA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 382
ht-degree: 32%

---

# Power BI 集成疑难解答

{{legacy-arb}}

研究并解决将 Report Builder 与 Power BI 一起使用时常见的问题。

## 无法发布到 Power BI

需要Power BI发布的计划工作簿取决于Power BI服务的正常运行情况。 无法发布的两大主要原因是：

* Power BI服务可能已关闭。
* 安排工作簿的用户不再具有有效的Microsoft帐户凭据。

每个Report Builder计划任务每次计划运行将获得三次尝试：

* 第一次尝试失败后，您会看到以下消息：“我们无法将此计划工作簿发布到Microsoft Power BI。 我们很快将再试一次。”
* 第二次尝试失败后，您将不会收到任何消息。
* 第三次尝试失败后，您会看到以下消息：“我们无法将此工作簿发布到Power BI。”

## Power BI 中的可视化效果受损

以下是将Report Builder请求发布到Power BI后，可视化图表可能会中断的主要原因：

* 您在 Report Builder 中编辑了请求（例如更改指标或维度），然后重新发布到 Power BI。 编辑请求可能会破坏可视化图表。
* 您已删除可视化图表中使用的请求。

>[!IMPORTANT]
>
>Report Builder需要管理员授权访问您的组织资源。 如果您需要访问权限，请要求管理员授予您权限。
> Microsoft管理员可以查看在以下位置找到的&#x200B;*用户可注册应用程序*&#x200B;设置： **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL 用户设置允许选项]**。 如果此选项设置为&#x200B;**否**，则管理员可以注册这些类型的应用程序。

用户可以通过登录到其[Microsoft Power BI帐户](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US)来授予访问权限。

管理员可以通过登录到其[管理员的Microsoft Power BI帐户](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US)来授予每个人访问权限。

## 达到API限制

Power BI中的报表可与Analytics报表API配合使用，因此API阈值限制适用。
