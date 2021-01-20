---
title: 设置跨设备分析
description: 配置虚拟报表包以启用 CDA。
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 68%

---


# 设置跨设备分析

在满足所有先决条件后，请通过以下步骤启用跨设备分析。您必须是产品配置文件管理员组的一员，或者拥有 Adobe Analytics 管理员权限，才能执行这些步骤。

>[!IMPORTANT]
>
>在执行这些步骤之前，必须满足所有先决条件。如果不满足所有先决条件，该功能将不可用或无法正常工作。请参阅[概述页面](overview.md)和所需的拼合方法（分别为[基于字段的拼合](field-based-stitching.md)或[设备图](device-graph.md)），了解先决条件和限制。

## 联系您的客户成功经理，在跨设备报告套件中设置CDA

CDA是通过Adobe工程在跨设备报表包中设置的。 请联系您的客户成功经理，获得以下信息：

* 您的Adobe Experience Cloud组织ID（以@AdobeOrg结尾的字母数字字符串）
* 要通过CDA启用的跨设备报表包的报表包ID
* 要使用哪种CDA方法(基于字段的拼接、Adobe专用图或Adobe合作图)
* 如果要使用基于字段的拼接，则包含用户ID的prop或eVar

向客户服务经理提供此信息后，他们会与Adobe工程部门合作，以启用您选择的报表包进行CDA处理。

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
* 标记为[已标识状态](../dimensions/identified-state.md)的新维可用。 此维度确定当时设备图是否知晓该点击的 Experience Cloud ID。
* 标记为[People](../metrics/people.md)和[唯一设备](../metrics/unique-devices.md)的新指标可用。
* 度量[唯一访客](../metrics/unique-visitors.md)不可用，因为它被替换为“人员”和“唯一设备”。
* 构建区段后，“访客”区段容器将被替换为“人员”容器。
