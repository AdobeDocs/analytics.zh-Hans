---
description: 虚拟报表包可对您的 Adobe Analytics 数据进行分段，以便您能够控制每个区段的访问权限。
title: 虚拟报表包概述
feature: VRS
exl-id: 45d18d14-d95a-42fe-b00a-cfce5f936e37
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 90%

---

# 虚拟报表包概述

虚拟报表包可对您的 Adobe Analytics 数据进行分段，以便您能够控制每个区段的访问权限。

许多客户都有数据流入全局报表包，但也有数据流入较小的报表包。他们为此设置了一个对应多个报表包的变量，并将其数据发送到多个报表包。此方法称为&#x200B;*多包标记*&#x200B;或&#x200B;*基础/父报表包*。

例如，所有数据可能会收集在一个报表包中，但是您可以随后设置辅助报表包，以便贵公司的其他人员能够访问部分数据，而不是全部数据。数据可以按区域划分。您可能拥有针对不同国家/地区的不同网站。其他示例可能还有一些隶属于较大公司的特定品牌，但每一个品牌又具有它们各自的营销团队。

*虚拟报表包*&#x200B;允许您使用区段而不是多个报表包来重现此分支概念。 数据会被发送到一个报表包，然后根据区段进行划分。就拿多个品牌的示例来说，您可以为某个项目所属的品牌设置一个 prop。使用区段，可以报告分配给每个 prop 的项目。这其中的每个区段都会成为其自身的视图，从而有效地创建新报表包。您并没有将数据专门发送到该区段，而只发送到了全局报表包，但是它在您的报表中发挥的作用就像是一个不同的报表包一样。

虚拟报表包会继承基础报表包的大部分服务级别，如 eVar 设置、处理规则和分类等。以下设置不会被继承：

* 报表包 ID (RSID)
* 报表包名称
* 权限群组（可将虚拟报表包分配给其自身的权限群组）

## 虚拟报表包的优点 {#section_3420422FE6DF46EAB151FD9442AAFDC4}

客户需要为辅助服务器调用支付费用，因此减去这些调用可节省大量开支。虚拟报表包还是完全可追溯的。如果全局报表包已经包含数据，则相关数据会自动包含在一个新的虚拟报表包中。新的辅助报表包将仅在创建后才开始收集数据，因此它不会包含任何历史数据。在实施 Analytics 时，您只需将数据发送到一个报表包，而不必为全局报表包和每个辅助报表包都创建实施。

虚拟报表包具有以下用处：

* 通过允许您在所有网站/域中使用单个报表包 ID (RSID) 来简化实施。随着我们向下一代 Adobe Analytics 的过渡，将所有数据放在单个报表包中可实现客户分析。
* 让贵组织中的业务用户始终只看到与其相关的数据区段。
* 通过允许管理员用户在实施后更轻松、更精细地控制数据访问来提升安全性。
* 人员指标
* 单个客户数据视图（将来会提供）
* 能够创建不限数量的虚拟报表包以细分数据

## 虚拟报表包的限制 {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

虚拟报表包存在以下限制：

* 任何区段限制也都适用于虚拟报表包

  虚拟报表包无非就是一个应用于报表包的区段。由于每个报表包均具有其自身的数据仓库和数据馈送，因此使用多个报表包会带来区段所不具备的某些好处。
* 实时报表
* 设置和变量名称无法像在完整报表包中那样进行自定义

## 虚拟报表包与多包标记 {#section_317E4D21CCD74BC38166D2F57D214F78}

| 功能 | 虚拟报告包 | 多包标记 |
|--- |--- |--- |
| 提供实时或“当前数据”报表 | 否 | 是 |
| 在所有 Analytics 工具（Analysis Workspace、Report Builder 等等）中工作 | 是。**注意：**&#x200B;您只能在[!UICONTROL Analytics] > [!UICONTROL 组件] > [!UICONTROL 虚拟报表包]中进行编辑并将它们标识为虚拟报表包。 但是，在其他工具中，您可以从报表包下拉菜单中选择虚拟报表包。<p>**重要信息**： Adobe Report Builder当前不支持具有报表时间处理和变量自定义的虚拟报表包。 | 是 |
| 可向其上载数据（通过 分类、数据馈送等） | 否 | 是 |
| 支持创建 DL 报表、书签、功能板、目标、警报、区段和计算量度... | 是 | 是 |
| 可单独添加至权限群组 | 是 | 是 |
| 可使用“管理员”功能修改此报表包的各个设置（管理员 > 报表包） | 否（从父项继承设置） | 是 |

{style="table-layout:auto"}

## 将虚拟报表包与多包标记结合使用 {#section_026FA3FCD7314DD18220E73EC5702AFF}

在某些情况下，同时使用虚拟报表包和多包标记会带来一些好处。

例如，一家零售商可以对每个品牌使用一个报表包，然后再对每个品牌使用虚拟报表包来按区域划分数据。同样，一家体育组织可以对每支运动队使用一个报表包，然后使用虚拟报表包将该运动队所在区域内的爱好者与该区域以外的爱好者划分开。
