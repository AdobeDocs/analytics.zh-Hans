---
description: 'null'
seo-description: 'null'
seo-title: 最佳实践
title: 最佳实践
uuid: 6d55a9aa-030e-4e4d-963c-ec9 cc38 e1731
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 最佳实践

## 保留 Power BI 可视化中的引用 {#section_7ED14FE64D974681A57EB91EF1B47CB6}

创建请求后，该请求将始终在 Power BI 中具有相同的引用。但如果您删除请求，该引用将由您为同一维度创建的新请求使用。

如果您在工作簿中删除请求，请确保 Power BI 中没有任何可视化指向该请求，否则，相应可视化将中断。

* 请尽可能地不要删除您在 Report Builder 中创建的请求
* 如果您确实要删除 Report Builder 中的请求，请确保同时删除 Power BI 中相应的可视化。
* 如果不确定：请删除不再需要的请求，然后重新发布并转到 Power BI 以查看哪些可视化已中断

