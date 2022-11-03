---
title: 同意管理选择退出
description: 查看访客选择退出的隐私设置。
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 5%

---

# 同意管理选择退出

“同意管理选择退出”维度显示访客明确选择退出的隐私设置。 您可以使用此维度根据隐私设置过滤数据，或查看最常见的隐私选择退出原因。

## 使用数据填充此维度

此维度从以下内容收集数据 [上下文数据变量](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` 当设置为 `1`. 如果 `cm.ssf` 等于 `0` 或为空，则此变量不执行任何操作。
* `contextData.['opt.dmp']` 当设置为 `N`. 如果 `opt.dmp` 等于 `Y`, [同意管理选择加入](cm-opt-in.md) 维度将被填充。
* `contextData.['opt.sell']` 当设置为 `N`. 如果 `opt.sell` 等于 `Y`, [同意管理选择加入](cm-opt-in.md) 维度将被填充。

贵组织确定实施这些上下文数据变量的逻辑。 它们不会在设置的点击之后保留，因此您必须在每个页面上设置每个上下文数据变量。

## 维度项

Dimension项目包括以下三个值：

* **`SSF`**:访客选择退出 [服务器端转发](/help/admin/admin/c-server-side-forwarding/ssf.md). 上下文数据变量时存在此维度项目 `cm.ssf` 等于 `1`. 请参阅 [数据隐私概述](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) （详细信息）Audience Manager用户指南中。
* **`DMP`**:访客选择退出共享到数据管理平台。 上下文数据变量时存在此维度项目 `opt.dmp` 等于 `N`. 点击不会转发到Adobe Audience Manager。
* **`SELL`**:访客选择退出向第三方共享或出售数据。 上下文数据变量时存在此维度 `opt.sell` 等于 `N`.
