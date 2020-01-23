---
title: VRS 和项目策划
description: 了解如何策划 VRS 组件和项目
translation-type: tm+mt
source-git-commit: 3a00162c5899ba2d5bb1b5aaed448b2abe93d56d

---


# VRS 和项目策划

在策划项目或虚拟报表包 (VRS) 时，您实际上可以过滤掉一些组件，以便受众只能查看您希望他们使用的那些项目/VRS 组件（维度、量度、区段、日期范围）。

>[!N注意：]
>产品配置文件是控制用户可以查看哪些组件的主要机制。 They are managed through the [Admin Console](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles). “策划”是一个次级过滤器。

我们最近改进了策划体验。下文除简要介绍了按权限级别在不同策划体验中提供的策划组件之外，还概述了&#x200B;**[!UICONTROL 显示所有]**按钮所显示的内容：

| 策划类型 | 管理员 | 非管理员项目所有者 | 非管理员 |
|---|---|---|---|
| 策划的 VRS | 所有非策划的 VRS 组件 | 此角色拥有或与其共享的非策划的 VRS 组件 | 此角色拥有或与其共享的非策划的 VRS 组件 |
| 策划的项目 | 所有非策划的项目组件 | 所有非策划的项目组件 | 此角色拥有或与其共享的非策划的项目组件 |
| 策划的 VRS 中的策划项目 | 所有非策划的项目，如下所示 **[!UICONTROL Non-Curated Project Components]**and**[!UICONTROL  Non-Curated VRS Components]** | 此角色拥有或与其共享的所有非策划项目组件以及非策划 VRS 组件 | 此角色拥有或与其共享的非策划的 VRS 和项目组件 |

>[!IMPORTANT]
>VRS特选始终在项目特选之前应用。 这意味着即使您的精选项目包含某些组件，如果精选的VRS不包含这些组件，也会过滤掉它们。
