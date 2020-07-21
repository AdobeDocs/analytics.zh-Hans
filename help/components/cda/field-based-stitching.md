---
title: 基于场的拼接
description: 了解使用基于字段的拼接拼接数据的先决条件和限制。
translation-type: tm+mt
source-git-commit: 2e7ec3b2e4401b02005b3099dae2bb34c64a6846
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 23%

---


# 基于场的拼接

跨设备Analytics提供两种将数据拼接在一起的不同方法。 此方法依赖Analytics变量(如 [prop](/help/implement/vars/page-vars/prop.md)[或eVar](/help/implement/vars/page-vars/evar.md))包含人员标识符。 它使用该变量作为将设备连接在一起的基础。

## 特定于基于字段的拼接的先决条件

如果您打算使用基于字段的拼接来实施跨设备Analytics，则需要满足以下条件。 请与贵组织内的团队以及 Adobe 客户经理合作，确保满足以下所有条件。

>[!IMPORTANT] 如果不满足所有先决条件，则可能会导致无法启用跨设备分析，或者导致拼合数据时的结果不佳。

* 概述页面上列出的所 [有先决条件](overview.md)。
* 您的实施必须设置prop或eVar，尽可能唯一地标识个人身份，如用户登录或打开电子邮件时。 这项要求适用于所有平台，包括使用的移动设备应用程序。为基于字段的拼接设置所需的标识变量后，请将该标识变量告知您的客户经理。

## 基于字段的拼接特有限制

* 基于字段的拼接最适合具有高用户识别率的报表包。 如果您的报表包的标识率或登录率较低，请考 [虑使用合作图](device-graph.md)。

## 后续步骤

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).