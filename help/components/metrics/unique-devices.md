---
title: 独特设备
description: 独特设备的数量。
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 16a9c9a2b6692b9b1944cfdb9b5b0411d48db666
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 73%

---

# 独特设备

“独特设备”[指标](overview.md)是一个[跨设备分析](../cda/overview.md)指标，它计算独特的未识别的设备和独特的虚拟设备的数量。 未识别的设备是产生匿名点击的设备。独特的虚拟设备是每个设备识别的不同的人员。

## 如何计算此指标

对于每个设备，合计所有与它相关的不同人员（如果设备包含非拼接的点击，则其中包括匿名人员）。

请注意，此指标与非 CDA 报表包中的[独特访客](unique-visitors.md)不等。例如，一个设备由 3 个不同的帐户共享。如果所有3个帐户都在报表时段中访问您的网站，则生成的报表将在CDA中显示3个独特设备。 CDA 之外的相同数据将显示 1 个独特访客。

## 示例

1. Sally通过广告通过电话访问您的网站，但未登录。
1. Sally 想要购物，但更愿意在家用电脑上操作，因为她在那里已经登录。 她在家用电脑上购物。
1. 第二天，她在手机上查看订单并在那里进行身份验证。
1. Bob 的妻子 Alice 在家庭计算机上登录到自己的帐户时浏览您的网站。
1. Bob 的兄弟 Charles 也在家庭计算机上登录到自己的帐户时浏览您的网站。

![独特设备数](/help/components/metrics/assets/Unique_Devices_Count.png)

在[重放](/help/components/cda/replay.md)（可能会拼接未经身份验证的点击）之前在 CDA 虚拟报表包中查看此数据将显示：

* **5 个独特设备**：1 个表示未经身份验证的 Bob + 2 个表示 Bob + 1 个表示 Alice + 1 个表示 Charles
* **4 个[人员](people.md)**：1 个[未识别的人员](unidentified-people.md) + 3 个[已识别的人员](identified-people.md)。
