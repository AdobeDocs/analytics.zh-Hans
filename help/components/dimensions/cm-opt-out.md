---
title: 同意管理选择退出
description: 查看访客选择退出的隐私设置。
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 93%

---

# 同意管理选择退出

&#39;同意管理选择退出&#39; [维度](overview.md) 显示访客明确选择退出的隐私设置。 您可以使用此维度根据隐私设置过滤数据，或查看最常见的隐私选择退出原因。

## 使用数据填充此维度

此维度从以下[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)收集数据：

* `contextData.['cm.ssf']`（当设置为 `1`）。如果 `cm.ssf` 等于 `0` 或为空，则此变量不执行任何操作。
* `contextData.['opt.dmp']`（当设置为 `N`）。如果 `opt.dmp` 等于 `Y`，则改为填充[同意管理选择加入](cm-opt-in.md)维度。
* `contextData.['opt.sell']`（当设置为 `N`）。如果 `opt.sell` 等于 `Y`，则改为填充[同意管理选择加入](cm-opt-in.md)维度。

您的组织确定实现这些上下文数据变量的逻辑。它们在点击之后便不再存在，因此您必须在每个页面上设置每个上下文数据变量。

## 维度项

维度项包括以下三个值：

* **`SSF`**：访客选择退出[服务器端转发](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)。此维度项在上下文数据变量 `cm.ssf` 等于 `1` 时存在。有关更多信息，请参阅 Audience Manager 用户指南中的[数据隐私概述](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html)。点击不会转发到 Adobe Audience Manager。
* **`DMP`**：访客选择不分享到数据管理平台。此维度项在上下文数据变量 `opt.dmp` 等于 `N` 时存在。与 `SSF` 类似，点击不会转发到 Adobe Audience Manager。
* **`SELL`**：访客选择不向第三方共享或出售数据。此维度在上下文数据变量 `opt.sell` 等于 `N` 时存在。
