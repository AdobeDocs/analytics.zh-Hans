---
title: 设置跨设备分析
description: 配置虚拟报表包以启用 CDA。
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 91%

---


# 设置跨设备分析

在满足所有先决条件后，请通过以下步骤启用跨设备分析。您必须是产品配置文件管理员组的一员，或者拥有 Adobe Analytics 管理员权限，才能执行这些步骤。

>[!IMPORTANT]
>
>在执行这些步骤之前，必须满足所有先决条件。如果不满足所有先决条件，该功能将不可用或无法正常工作。请参阅[概述页面](overview.md)和所需的拼合方法（分别为[基于字段的拼合](field-based-stitching.md)或[设备图](device-graph.md)），了解先决条件和限制。

## 选择要启用 CDA 的跨设备报表包

在贵组织准备好使用 CDA 后，请选择要使用该功能的报表包。可通过 Adobe 客户经理来告知您选择的报表包。然后，Adobe 将为您选择的报表包启用 CDA 处理。

## 创建跨设备虚拟报表包以查看跨设备视图

有权创建虚拟报表包的管理员可以按如下方式创建 CDA 虚拟报表包：

1. 导航到 [experiencecloud.adobe.com](https://experiencecloud.adobe.com) 并使用 Adobe ID 凭据登录。
2. 单击顶部的 9 宫格图标，然后单击“Analytics”。
3. 将鼠标指针悬停在顶部的“组件”上，然后单击“虚拟报表包”。
4. 单击“添加”。
5. 输入虚拟报表包的名称，并确保选定已启用 CDA 的报表包。
6. （可选）将区段应用到虚拟报表包。例如，您可以应用一个区段，以将虚拟报表包的日期限制为在 CDA 开启且拼合开始后的日期。此区段允许用户仅查看 VRS 内的拼合日期范围。
7. 单击“启用报表时间处理”复选框，此复选框可启用多个选项，包括跨设备分析。
8. 单击“拼合跨设备用户访问”复选框。
9. 单击“继续”，完成虚拟报表包的配置，然后单击“保存”。

![CDA 复选框](assets/cda-checkbox.png)

## 跨设备虚拟报表包的添加和更改项目

在虚拟报表包中启用跨设备分析后，请注意以下更改：

* 虚拟报表包名称旁边将显示一个新的跨设备图标。此图标仅适用于跨设备虚拟报表包。
* A new dimension labeled [Identified state](../dimensions/identified-state.md) is available. 此维度确定当时设备图是否知晓该点击的 Experience Cloud ID。
* New metrics labeled [People](../metrics/people.md) and [Unique Devices](../metrics/unique-devices.md) are available.
* The metric [Unique Visitors](../metrics/unique-visitors.md) is not available, as it is replaced with &#39;People&#39; and &#39;Unique Devices&#39;.
* 构建区段后，“访客”区段容器将被替换为“人员”容器。
