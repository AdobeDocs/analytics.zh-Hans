---
title: 分类集作业管理器
description: 查看从分类集生成的当前和已完成的分类作业。
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 100%

---

# 分类集作业管理器

通过分类集作业管理器，可以查看从分类集生成的当前和已完成的分类作业。 您还可以使用此界面下载特定作业的分类数据或模板，或将其他数据上载到作业。

>[!NOTE]
>
>此功能当前正在进行小范围发布。 如果您想访问此功能，请联系 Adobe 客户关怀部门或您的客户经理，他们可以将您的请求转发给分类团队进行配置。

**[!UICONTROL “组件”]**>**[!UICONTROL “分类集”]**>**[!UICONTROL “作业”]**

请注意，您无法从此界面创建作业。 相反，您可以通过将数据上载到分类集、请求下载文件或请求模板文件来创建作业。

## 筛选分类集

分类集作业管理器的左侧提供筛选条件设置以定位所需作业。 单击过滤器图标可切换过滤器设置的可见性。 您可以通过&#x200B;**[!UICONTROL “分类集”]**、**[!UICONTROL “完成时间”]**&#x200B;或者&#x200B;**[!UICONTROL “状态”]**&#x200B;筛选分类集。

![分类集作业过滤器](../assets/classification-set-job-filters.png)

分类集作业管理器列上方提供了其他筛选选项：

* **[!UICONTROL 按标题搜索]**：按文件名搜索作业。
* **[!UICONTROL 加载更多]**：分类集作业管理器最初最多显示 1000 个作业。 单击此按钮可加载 1000 多个作业。
* **显示/隐藏列**：切换除[!UICONTROL 文件名]和[!UICONTROL 完成时间]之外的任何列的可见性。

## 分类集作业管理器列

分类集作业管理器中有以下列：

* **[!UICONTROL 文件名]**：上传或下载文件的名称。
* **[!UICONTROL 分类集]**：文件应用于的分类集的名称。 您可以单击分类集名称以访问分类集的[设置](settings.md)。
* **[!UICONTROL 大小]**：文件大小。
* **[!UICONTROL 状态]**：处理文件的作业的状态。
   * **[!UICONTROL 已创建]**：作业已提交。
   * **[!UICONTROL 排队]**：文件已准备好处理，正在等待分类服务器处理该文件。
   * **[!UICONTROL 已验证]**：文件有效，正在等待处理。
   * **[!UICONTROL 验证失败]**：文件格式不正确或无效。 文件未经过处理。
   * **[!UICONTROL 处理]**：Adobe 正在积极处理文件。
   * **[!UICONTROL 处理失败]**：文件处理失败。
   * **[!UICONTROL 完成]**：处理完成。 分类数据在报告中可见。
   * **[!UICONTROL 失败]**：与验证或处理无关的一般性失败。
* **[!UICONTROL 类型]**：作业类型。
* **[!UICONTROL 文件下载]**：仅适用于下载作业，例如下载分类数据或下载模板。下载就绪后，此列将提供下载链接。
* **[!UICONTROL 完成时间]**：作业完成（或失败）的日期和时间。