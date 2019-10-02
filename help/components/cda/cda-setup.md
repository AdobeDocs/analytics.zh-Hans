---
title: 设置 Cross-Device Analytics
description: Learn how to set up Cross-Device Analytics after you meet the prerequisites.
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# 设置 Cross-Device Analytics

> [!NOTE] Cross-Device Analytics documentation is subject to change as the feature is further developed. Check back regularly for updates.

Once all prerequisites are met, use the following steps to enable Cross-Device Analytics. 您必须属于产品配置管理员组，或在Adobe Analytics中拥有管理员权限才能执行这些步骤。

> [!IMPORTANT] 在执行这些步骤之前，必须满足所有先决条件。 如果未满足所有先决条件，则该功能不可用或将无法工作。 有关 [先决条件和限制](cda-home.md) ，请参阅跨设备分析。

## 选择将为CDA启用的跨设备报告套件

当您的组织设置为使用CDA时，您可以选择要使用的报表包。 此选择可通过您的Adobe客户经理进行交流。 然后，Adobe将启用您选择的报表包进行CDA处理。

## 创建跨设备虚拟报告套件以查看跨设备视图

有权创建虚拟报表包的管理员可以按如下方式创建CDA虚拟报表包：

1. 导航到 [experiencecloud.adobe.com](https://experiencecloud.adobe.com) ，然后使用AdobeID凭据登录。
2. 单击顶部的9网格图标，然后单击分析。
3. 将指针悬停在顶部的组件上，然后单击虚拟报告包。
4. 单击添加。
5. 输入虚拟报告套件的名称，并确保已选择启用CDA的报告套件。
6. 单击复选框“启用报告时间处理”，此复选框可启用多个选项，包括“跨设备分析”。
7. 单击复选框“拼合跨设备用户访问”。
8. 单击继续，完成虚拟报告包的配置，然后单击保存。

![CDA复选框](assets/cda-checkbox.png)

## Additions and changes to cross-device virtual report suites

When Cross-Device Analytics is enabled on a virtual report suite, note the following changes:

* A new cross-device icon appears next to the virtual report suite name. This icon is exclusive to cross-device virtual report suites.
* New metrics labeled 'People' and 'Unique Devices' are available.
* The metric 'Unique Visitors' is not available, as it is replaced with People and Unique Devices.
* When building segments, the 'Visitor' segment container is replaced with a 'Person' container.

## The Compression calculated metric

The ability for Cross-Device Analytics to stitch devices together depends on a wide range of factors. 可以使用称为压缩的计算度量来测量特征拼接数据的能力的有效性。 导致压缩的因素包括：

* 使用合作图或专用图：一般而言，使用设备合作计划的组织往往比使用专用图表的组织发现更好的压缩率。
* 登录率：登录网站的用户越多，Adobe越能跨设备识别和拼接访客。 登录率较低的站点也具有低压缩率。
* Experience Cloud ID coverage: Only visitors with an ECID can be stitched. 使用ECID访问您网站的访客百分比较低与压缩率较低相关。
* 多种设备使用：如果网站的访问者不使用多种设备，则可以看到较低的压缩率。
* Reporting granularity: Compression by day is typically smaller than compression by month or year. 个人在一天内使用多种设备的机会比整个月内要小。 细分、筛选或使用细分维也可以显示较低的压缩率。

To see your organization's compression for a given time period:

1. 单击顶部的“工作区”，然后单击“创建新项目”。
2. 从空白项目开始，然后单击创建。
3. 将“唯一设备”量度拖到标有“将量度拖到此处”的画布区域上。
4. Drag the People metric onto the canvas directly to the right of the Unique Devices metric header, so the two metrics are side-by-side.
5. Click the '' symbol next to available metrics on the left to open the Calculated Metric builder.`+`
6. Give this calculated metric the following settings:
   * 名称：跨设备压缩
   * 格式：百分比
   * Decimal Places: 2
   * 定义: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] 单击定义区域右上角的“添加”以添加静态数字。 从左侧的可用度量列表中拖动“人员”和“唯一设备”。
7. 单击“保存”。
8. 将新的计算量度直接拖到“人员”量度标题右侧的画布上，因此所有三个量度都是并排的。
9. 可选：默认情况下，工作区加载“天”维。 如果需要其他时间粒度，请将替代日期维度（如周或月）拖动到“日”维度上方。
