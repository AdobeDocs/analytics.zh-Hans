---
description: 以下是在结合使用 Report Builder 与 Power BI 时存在的几个常见问题。
seo-description: 以下是在结合使用 Report Builder 与 Power BI 时存在的几个常见问题。
seo-title: Power BI集成疑难解答
title: Power BI集成疑难解答
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Power BI集成疑难解答

以下是在结合使用 Report Builder 与 Power BI 时存在的几个常见问题。

## 步骤 1. Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

要求 Power BI 发布的计划工作簿需要 Power BI 服务启动和运行。发布失败的两个主要原因包括：

* Power BI 服务可能发生故障。
* 计划该工作簿的用户不再拥有有效的 Microsoft 帐户凭据。

每个 Report Builder 计划任务在每次计划运行时都有三次尝试机会：

* 在首次不成功的尝试之后，您将收到以下消息：“无法将此计划工作簿发布到 Microsoft Power BI。我们将稍后再试。”
* 在第二次不成功的尝试之后，您将不会收到消息。
* 在第三次不成功的尝试之后，您将收到以下消息：“无法将此计划工作簿发布到 Power BI。”

## 步骤 2. Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

以下是在将 Report Builder 请求发布到 Power BI 后导致可视化中断的几个主要原因：

* 您在 Report Builder 中编辑了请求（例如更改量度或维度），然后重新发布到 Power BI。编辑请求可能中断您的可视化。
* 您删除了可视化中使用的请求。

