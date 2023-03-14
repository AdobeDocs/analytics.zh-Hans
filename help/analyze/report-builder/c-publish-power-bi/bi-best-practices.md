---
description: Power BI 最佳实践。
title: 最佳实践
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

---

# 最佳实践

## 在 Power BI 可视化效果中保留引用 {#section_7ED14FE64D974681A57EB91EF1B47CB6}

创建请求后，该请求将始终在 Power BI 中具有相同的引用。但如果您删除请求，该引用将由您为同一维度创建的新请求使用。

如果您在工作簿中删除请求，请确保 Power BI 中没有任何可视化指向该请求，否则，相应可视化将中断。

* 请尽可能地不要删除您在 Report Builder 中创建的请求
* 如果您确实要删除 Report Builder 中的请求，请确保同时删除 Power BI 中相应的可视化。
* 如果不确定：请删除不再需要的请求，然后重新发布并转到 Power BI 以查看哪些可视化已中断
