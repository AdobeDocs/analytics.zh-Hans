---
title: 层级
description: 可在报告中使用的自定义维度。
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# 层级

>[!IMPORTANT]
>
>此维度已停用，且在 Analysis Workspace 中不是可用维度。 Adobe 建议改用 [eVar](evar.md) 和分类。

层级是自定义变量，您可以根据需要随意使用。 它们不会在设置的点击之外继续存在。如果您与 Adobe 签署的合同支持，则至多有 5 个层级可供使用。

## 使用数据填充层级

每个层级都从图像请求中的 [`h1` – `h5` 查询字符串](/help/implement/validate/query-parameters.md)中收集数据。 例如，`h1` 查询字符串参数为层级 1 收集数据，而 `h4` 查询字符串参数为层级 4 收集数据。

AppMeasurement 将 JavaScript 变量编译到图像请求中以用于数据收集，它使用变量 `hier1` — `hier5`。请参阅实施用户指南中的[层级](/help/implement/vars/page-vars/hier.md)，了解相关实施指南。

## 维度项

由于层级在您的实施中包含自定义字符串，因此，由您的组织来确定每个层级的维度项目。 请确保在[解决方案设计文档](/help/implement/prepare/solution-design.md)中记录每个层级的用途和典型维度项目。
