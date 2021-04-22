---
description: 了解不同的保存选项，包括自动保存、另存为、另存为模板以及打开以前的版本。
title: 保存项目
feature: Workspace 基础知识
role: Business Practitioner, Administrator
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
translation-type: tm+mt
source-git-commit: cfeb681805108c9d9422d88b6d7146d0eb186204
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 54%

---

# 保存项目

要保存对项目所做的更改，请转到工作区的&#x200B;**[!UICONTROL 项目]**&#x200B;菜单。Workspace还在某些情况下自动保存项目。

## 保存项目选项 {#Save}

在&#x200B;**[!UICONTROL 项目]**&#x200B;菜单下，您可以执行不同的保存操作，具体取决于您希望未来以何种方式访问分析。

| 操作 | 描述 |
|---|---| 
| **[!UICONTROL 保存]** | 将更改保存到项目。如果项目已共享，项目的收件人也会看到所做的更改。首次保存项目时，系统会提示您为项目指定名称、（可选）描述和添加（可选）标记。 |
| **[!UICONTROL 同时保存注释]** | 在保存项目之前，添加有关项目中发生更改的注释。 注释随项目版本一起存储，并可供[!UICONTROL Project] > [!UICONTROL 打开以前版本]下的所有编辑器使用。 |
| **[!UICONTROL 另存为]** | 创建项目副本。原始项目不受影响。 |
| **[!UICONTROL 另存为模板]** | 将您的项目另存为[自定义模板](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html)，贵组织可在&#x200B;**[!UICONTROL 项目 > 新建]**&#x200B;下使用该模板 |

![](assets/save-project.png)

## 自动保存 {#Autosave}

每两分钟会将现有项目（即，以前至少保存过一次的项目）自动保存到本地计算机。目前，不会自动保存从未保存过的新项目。

有一些情形可能会使您离开项目而未保存所做的更改，从而导致不同的可用操作。

### 打开另一个工作区项目

Adobe 提供了在离开页面之前进行保存的选项。离开现有项目后，将删除自动保存的本地副本。

![](assets/existing-save.png)

### 离开或关闭选项卡

浏览器会警告“未保存的更改将会丢失”。您可以选择离开或取消。

![](assets/browser-image.png)

### 浏览器崩溃或会话超时

对于&#x200B;**现有**&#x200B;项目，返回Workspace后，您将看到&#x200B;**项目恢复**&#x200B;模式。 选择“是”将从自动保存的本地副本恢复项目。 选择“否”将删除自动保存的本地副本并打开用户保存的最近项目版本。

![](assets/project-recovery.png)

对于从未保存的&#x200B;**新**&#x200B;项目，未保存的更改将无法恢复。

## 打开以前的版本 {#previous-version}

>[!NOTE]
>
>以前的项目版本当前为有限版本。

要打开项目的先前版本，请执行以下操作：

1. 转至&#x200B;**[!UICONTROL Project]** > **[!UICONTROL 打开以前版本]**

   ![](assets/previous-versions.png)

1. 查看先前版本的列表。
   [!UICONTROL 显示] 了“时  间戳”和“编辑器”(Editor)，并  且添加了“注释”(  Note)。没有备注的版本存储90天；包含注释的版本存储1年。
1. 选择以前的版本，然后单击&#x200B;**[!UICONTROL 加载]**。
之前的版本随后随通知一起加载。 单击**[!UICONTROL 保存]**&#x200B;后，之前的版本才会成为项目的当前保存版本。 如果您从加载的版本导航离开，当您返回时，您将看到项目的上次保存版本。
