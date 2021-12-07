---
title: 独特设备
description: 独特设备的数量。
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 99a6144be155e17a8252e5461b2d6a96e5be641d
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 76%

---

# 独特设备

“独特设备”指标是一个 [Cross-device analytics](../cda/overview.md) 指标，它计算独特的未识别的设备和独特的虚拟设备的数量。未识别的设备是产生匿名点击的设备。独特的虚拟设备是每个设备识别的不同的人员。

## 如何计算此指标

对于每个设备，合计所有与它相关的不同人员（如果设备包含非拼接的点击，则其中包括匿名人员）。

请注意，此指标与非 CDA 报表包中的[独特访客](unique-visitors.md)不等。例如，一个设备由 3 个不同的帐户共享。如果所有 3 个帐户都在报表时段中访问您的网站，则所得的报表将在 CDA 中显示 3 个独特设备。CDA 之外的相同数据将显示 1 个独特访客。

## 示例

1. 莎莉通过广告到达您的网站，但未登录。
1. 萨莉想要购买产品，但是希望在家庭计算机上进行购买，因为她已经登录了。 在家用电脑上，她买了东西。
1. 第二天，她用他的电话查他的订单，并在那里进行验证。
1. Bob 的妻子 Alice 在家庭计算机上登录到自己的帐户时浏览您的网站。
1. Bob 的兄弟 Charles 也在家庭计算机上登录到自己的帐户时浏览您的网站。

![独特设备数](/help/components/metrics/assets/Unique_Devices_Count.png)

在[重放](/help/components/cda/replay.md)（可能会拼接未经身份验证的点击）之前在 CDA 虚拟报表包中查看此数据将显示：

* **5 个独特设备**：1 个表示未经身份验证的 Bob + 2 个表示 Bob + 1 个表示 Alice + 1 个表示 Charles
* **4 个[人员](people.md)**：1 个[未识别的人员](unidentified-people.md) + 3 个[已识别的人员](identified-people.md)。
