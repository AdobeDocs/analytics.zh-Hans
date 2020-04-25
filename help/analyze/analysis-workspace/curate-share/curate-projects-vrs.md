---
title: VRS 和项目策划
description: 了解如何策划 VRS 组件和项目
translation-type: tm+mt
source-git-commit: db983980a6ec3db4d60bbc8fc3ba57a4e1219287

---


# VRS 和项目策划

在策划项目或虚拟报表包 (VRS) 时，您实际上可以过滤掉一些组件，以便受众只能查看您希望他们使用的那些项目/VRS 组件（维度、量度、区段、日期范围）。

>[!NOTE]
>
>产品配置文件是控制用户可以查看哪些组件的主要机制。这些配置文件可通过 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/manage-products-and-profiles.html#createproductprofiles) 进行管理。“策划”是一个次级过滤器。

我们最近改进了策划体验。Here is an overview of what the **[!UICONTROL Show All]** button reveals, in addition to the curated components already available, in different curated experiences and by permission level:

| 策划类型 | 管理员 | 非管理员项目所有者 | 非管理员 |
|---|---|---|---|
| 策划的 VRS | 所有非策划的 VRS 组件 | 此角色拥有或与其共享的非策划的 VRS 组件 | 此角色拥有或与其共享的非策划的 VRS 组件 |
| 策划的项目 | 所有非策划的项目组件 | 所有非策划的项目组件 | 此角色拥有或与其共享的非策划的项目组件 |
| 策划的 VRS 中的策划项目 | 所有非策划的项目，如下所示 **[!UICONTROL Non-Curated Project Components]** 和 **[!UICONTROL Non-Curated VRS Components]** | 此角色拥有或与其共享的所有非策划项目组件以及非策划 VRS 组件 | 此角色拥有或与其共享的非策划的 VRS 和项目组件 |

>[!IMPORTANT]
>
>始终先应用 VRS 策划，再应用项目策划。这意味着即使您的策划项目包含某些组件，但是如果策划 VRS 不包含这些组件，系统也会将这些组件滤除。
