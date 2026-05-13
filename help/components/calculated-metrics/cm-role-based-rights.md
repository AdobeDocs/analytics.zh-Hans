---
description: 计算指标权限在管理员级别的用户和非管理员用户之间有所不同。
title: 基于角色的权限
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
TQID: https://experienceleague.adobe.com/M2ZwpkhpvhavBOwrVsDxcEYsS9kAFGAcuCl5TSUzxXU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 69%

---

# 基于角色的权限

计算指标权限在管理员级别的用户和非管理员用户之间有所不同。

|  | 创建 | 共享 | 查看/管理 | 批准 | 应用 |
|--- |--- |--- |--- |--- |--- |
| 管理员级别的用户 | 管理员可创建计算指标以及在 Admin Console 中创建产品配置文件以限制用户创建计算指标的权利。 | 可与整个公司、用户组和个别用户共享。 | Report Builder：可查看/编辑/删除/等等自身的计算指标和与他共享的计算指标。 | 可以批准计算指标作为规范。 | 可以在整个组织内应用任何计算指标。 |
| 非管理员级别的用户 | 默认情况下，用户可以创建计算指标。 但是，管理员可能会限制这些权限。 | 只能与个人用户共享 | 只能查看/编辑/删除/等等他们自己的计算指标。 非管理员用户必须具有所有组件事件的访问权限，才能查看共享量度（管理控制台中的权限仍然是必需的）。  如果与非管理员用户共享功能板或计划报表，并且他们没有与其共享的指标，则报表将随应用的指标一起运行（假定他们有权查看事件）。 但是，他们将无法查看定义或编辑指标。 | 只能使用批准的计算指标，无法将计算指标标记为已批准。 | 可以应用他们自己的计算指标以及与他们共享的区段。 |
