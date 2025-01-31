---
description: “策划”让您可在共享项目前限制组件。
keywords: Analysis Workspace 策划
title: 策划项目
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 98%

---

# 策划项目

“策划”让您可在共享项目前限制组件（维度、量度、区段、日期范围）。当收件人打开项目时，他们将看到您为其策划的有限组件。策划虽然是一个可选步骤，但建议在共享项目前执行此步骤。

>[!NOTE]
> 产品配置文件是控制用户可以查看哪些组件的主要机制。此类配置文件通过 Adobe Experience Cloud Admin Console 进行管理。“策划”是一个次级过滤器。


>[!BEGINSHADEBOX]

观看演示视频，请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [策划项目](https://video.tv.adobe.com/v/24711?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


## 应用项目策划

1. 单击&#x200B;**[!UICONTROL 共享]** > **[!UICONTROL 策划项目数据]**。将自动添加项目中使用的组件。
   **注意**：如果一个项目有多个报表包，您将在项目中看到每个报表包都有一个“策划”字段。
1. （可选）要添加更多组件，请将要共享的组件从左边栏拖到[!UICONTROL 策划组件]字段。
1. 单击&#x200B;**[!UICONTROL 完成]**。

也可以通过单击&#x200B;**[!UICONTROL 策划和共享]**&#x200B;从[!UICONTROL 共享]菜单中应用策划。此选项会自动将项目策划为项目中使用的组件。您可以按照上述步骤添加更多组件。

![](assets/curation-field.png)

## 应用策划后的项目视图

当收件人打开应用策划后的项目时，他们将只看到您在策划时定义的组件集：

![](assets/curate-project.png)

## 删除项目策划

要删除项目策划并恢复左边栏中的完整组件集，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL 共享]** > **[!UICONTROL 策划项目数据]**。
1. 单击&#x200B;**[!UICONTROL 删除策划]**。
1. 单击&#x200B;**[!UICONTROL 完成]**。

## 虚拟报告包策划

要在报告包级别应用策划，以使其同时适用于多个项目，可[在虚拟报告包中策划组件](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-components.html?lang=zh-Hans)。

>[!NOTE]
> 始终在项目策划之前应用虚拟报告包策划。这意味着即使您策划的项目包含某些组件，如果策划的虚拟报告包不包括这些组件，则也将过滤掉这些组件。

## “显示所有组件”选项

在策划的项目或虚拟报告包中，将为收件人呈现左边栏中的&#x200B;**[!UICONTROL 显示所有组件]**&#x200B;选项。[!UICONTROL 显示所有组件]根据以下各项显示不同的组件集：

* 用户的权限级别（管理员或非管理员）
* 项目角色（所有者/编辑者或非所有者/编辑者）
* 所应用的策划类型（虚拟报告包或项目）
* 由用户拥有或者共享给用户的组件。拥有/共享的组件包括区段、计算量度和日期范围。它们不包括已实施的组件，例如 eVar、prop 和自定义事件。

注意：非管理员视图角色没有对项目中左边栏的访问权限，因此在下表中已忽略。

| 策划类型 | 管理员 | 非管理员项目所有者或编辑角色 | 非管理员重复角色 |
|---|---|---|---|
| 策划的虚拟报告包 | 所有非策划的虚拟报告包组件 | 此角色拥有或与其共享的非策划的虚拟报告包组件 | 此角色拥有或与其共享的非策划的虚拟报告包组件 |
| 策划的项目 | 所有非策划的项目组件 | 所有非策划的项目组件 | 此角色拥有或与其共享的非策划的项目组件 |
| 策划的虚拟报告包中策划的项目 | 所有非策划的组件，如&#x200B;**[!UICONTROL 非策划的项目组件]**&#x200B;和&#x200B;**[!UICONTROL 非策划的虚拟报告包组件]**&#x200B;下所示 | 此角色拥有或与其共享的所有非策划的项目组件和非策划的虚拟报告包组件 | 此角色拥有或与其共享的非策划的虚拟报告包和项目组件 |
