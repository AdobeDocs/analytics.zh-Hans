---
description: 您可以在 Adobe Analytics 中查看 Document Cloud 数据
title: 配置 Document Cloud 报告
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 100%

---

# 配置 Document Cloud 报告

您可以配置特定于 PDF 的维度和量度以便在 Adobe Analytics 中可用。

## 启用 PDF 报告时添加的组件

正确配置 PDF 报告后，以下维度和量度在 Adobe Analytics 中可用：

**维度：**

* PDF 搜索项

* PDF 缩放级别

* PDF 操作

* PDF 页面编号

* PDF 文件名

**量度：**

* PDF 查看次数

* PDF 页面查看次数

* PDF 下载次数

* PDF 搜索

* 使用的 PDF 书签数

* PDF 复制文本

* PDF 打印

## 在 Adobe Analytics 中启用 PDF 报告

1. 转到 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报告包]** > **`<select report suite>`** > **[!UICONTROL 编辑设置]** > **[!UICONTROL Document Cloud 管理]** > [!UICONTROL **Document Cloud 报告**]。

1. 在 Adobe Document Cloud 管理页面上，选择&#x200B;[!UICONTROL **启用 PDF 报告**]。

1. 要配置 Adobe Document Cloud 以将数据传输到 Adobe Analytics，请使用 [Adobe Document Cloud Javascript SDK ](https://www.adobe.io/apis/documentcloud/dcsdk.html)。
