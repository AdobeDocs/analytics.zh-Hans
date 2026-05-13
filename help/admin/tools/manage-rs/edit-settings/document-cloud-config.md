---
description: 您可以在 Adobe Analytics 中查看 Document Cloud 数据
title: 配置 Document Cloud 报告
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
TQID: https://experienceleague.adobe.com/2X5YQxmTsMYdnwSWVL4EMr1K1aV9UM6FRMHa2P--Xuc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 140
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
