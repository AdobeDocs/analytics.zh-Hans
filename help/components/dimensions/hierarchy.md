---
title: 层级
description: 可在报表中使用的自定义维度。
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 22%

---

# 层级

>[!IMPORTANT]
>
>此维度已停用，且在Analysis Workspace中不是可用维度。 Adobe 建议改用 [eVar](evar.md) 和分类。

层级是自定义变量，您可以根据需要随意使用。 它们不会在设置的点击之外继续存在。如果您与Adobe签订的合同支持，则最多5个层级可用。

## 使用数据填充层级

每个层级都从 [`h1` - `h5` 查询字符串](/help/implement/validate/query-parameters.md) 在图像请求中。 例如， `h1` 查询字符串参数为层级1收集数据，而 `h4` 查询字符串参数为层级4收集数据。

AppMeasurement 将 JavaScript 变量编译到图像请求中以用于数据收集，它使用变量 `hier1` — `hier5`。请参阅 [hier](/help/implement/vars/page-vars/hier.md) 中的实施用户指南以了解相关实施指南。

## 维度项

由于层级在您的实施中包含自定义字符串，因此，由您的组织来确定每个层级的维度项目。 确保在 [解决方案设计文档](/help/implement/prepare/solution-design.md).