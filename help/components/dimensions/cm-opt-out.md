---
title: 同意管理选择退出
description: 查看访客选择禁用的隐私设置。
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
TQID: 'https://experienceleague.adobe.com/tsMhHR84qhEUZIZjPTluCJOHMPc37-JRwLsipAycgJI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 83%
---
# 同意管理选择退出

“同意管理选择退出”[维度](overview.md)显示访客明确选择退出的隐私设置。 您可以使用此维度根据隐私设置过滤数据，或查看最常见的隐私选择禁用原因。

## 使用数据填充此维度

此维度从以下[上下文数据变量](/help/implement/vars/page-vars/contextdata.md)收集数据：

* `contextData.['cm.ssf']`（当设置为 `1`）。 如果 `cm.ssf` 等于 `0` 或为空，则此变量不执行任何操作。
* `contextData.['opt.dmp']`（当设置为 `N`）。 如果 `opt.dmp` 等于 `Y`，则改为填充[同意管理选择加入](cm-opt-in.md)维度。
* `contextData.['opt.sell']`（当设置为 `N`）。 如果 `opt.sell` 等于 `Y`，则改为填充[同意管理选择加入](cm-opt-in.md)维度。

您的组织确定实现这些上下文数据变量的逻辑。 在每个页面上设置每个上下文数据变量。

| 属性 | 值 |
| --- | --- |
| **AppMeasurement变量** | 无（通过同意信号设置） |
| **Web SDK / XDM字段** | 无 |
| **查询参数** | 不适用 |
| **XML标记** | 不适用 |
| **字节限制** | 100字节 |
| **持久性** | 点击 |

## 维度项目

维度项包括以下三个值：

* **`SSF`**：访客选择退出[服务器端转发](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)。 此维度项在上下文数据变量 `cm.ssf` 等于 `1` 时存在。 有关更多信息，请参阅 Audience Manager 用户指南中的[数据隐私概述](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=zh-Hans)。 点击不会转发到 Adobe Audience Manager。
* **`DMP`**：访客选择不分享到数据管理平台。 此维度项在上下文数据变量 `opt.dmp` 等于 `N` 时存在。 与 `SSF` 类似，点击不会转发到 Adobe Audience Manager。
* **`SELL`**：访客选择不向第三方共享或出售数据。 此维度在上下文数据变量 `opt.sell` 等于 `N` 时存在。
