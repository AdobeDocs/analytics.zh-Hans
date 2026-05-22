---
description: Web 服务 API 可通过编程方式访问市场营销报告及其他“包”服务，从而让您以其他方式使用通过 Analytics 界面提供的功能，以及实现更多功能。
title: Web 服务
feature: Company Settings
exl-id: d003d40e-b0b6-44f3-b9ef-ce6af61f5eb5
role: Admin
TQID: https://experienceleague.adobe.com/q0Ji-KYZJS486CKtHaDttXs3coS5hSYQd-cArPK1mCU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 303
ht-degree: 42%

---

# Web 服务

Web 服务 API 可通过编程方式访问市场营销报告及其他“包”服务，从而让您以其他方式使用通过 Analytics 界面提供的功能，以及实现更多功能。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 所有管理员]** > **[!UICONTROL 公司设置]** > **[!UICONTROL Web服务]**&#x200B;或&#x200B;**[!UICONTROL API访问]**


## Analytics 2.0 API

要访问Analytics 2.0 API，您需要Analytics公司的全球公司ID。 您可以在[!UICONTROL API访问]部分的顶部&#x200B;**bold**&#x200B;中找到全局公司ID。 以下是一个示例：“您当前登录的Analytics公司的全局公司ID是&#x200B;**adobe1234**。”

## 管理旧版 Web 服务（已弃用）

在 [Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html) 中，您可以更新权限以包括那些需要访问 Web 服务 API 的用户。

## WSDL：为 Web 服务开发人员下载 Web 服务 API WSDL

访问 [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/)，其中提供了与 Web 服务 API 相关的文档、示例代码和论坛。 有关详细信息，请单击Web服务API概述。

## 过滤选项

使用SOAP时，如果XML解析器在响应Web服务API调用时遇到非法或无效字符问题，请选择以下一个或两个选项以使Analytics自动筛选响应输出。 通常，只有双字节语言（日语、中文、韩语）会发生此问题。

## API 访问信息

按用户查看Web服务访问信息。 此表包括Web服务用户名和共享机密，用户在进行Web服务调用时必须将这些用户名和机密用作身份验证过程的一部分。

## 令牌用法

查看有关您的公司在当前日历月中使用的Web服务令牌数的信息。
