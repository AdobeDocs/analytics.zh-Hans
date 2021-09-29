---
title: 独特设备
description: 独特设备的数量。
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: db88bd439c036e97cca641f31f4fc3101a368636
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 5%

---

# 独特设备

“独特设备”量度是一个[跨设备分析](../cda/overview.md)量度，用于计算独特未识别设备和独特虚拟设备的数量。 未识别的设备是生成匿名点击的设备。 独特虚拟设备是指每台设备识别的不同人员。

## 如何计算此量度

对于每个设备，对与其关联的所有不同人员进行汇总（如果设备包含未拼合的点击，则包括匿名）。

请注意，此量度不等于非CDA报表包中的[独特访客](unique-visitors.md)。 例如，一个设备由3个不同的帐户共享。 如果所有3个帐户都在报表窗口中访问您的网站，则生成的报表将在CDA中显示3个独特设备。 CDA外的相同数据将显示1个独特访客。

## 示例

1. Bob通过广告到达您的网站，但未登录。
1. Bob想要购买产品，但是希望在家庭计算机上进行购买，因为他已经登录了。 他在家用电脑上买东西。
1. 第二天，他在电话上检查命令，并在那里进行验证。
1. Bob的妻子Alice在登录家庭计算机上的帐户时浏览您的网站。
1. Bob的兄弟Charles在登录家庭计算机上的帐户时也浏览了您的网站。

![独特设备计数](/help/components/metrics/assets/Unique_Devices_Count.png)

在[Replay](/help/components/cda/replay.md)可能拼合未经身份验证的点击之前，在CDA虚拟报表包中查看此数据将显示：

* **5个独特设备**:对于未经身份验证的Bob + 2，对于Alice + 1，对于Charles，为1
* **4 [人](people.md)**:1个 [未识别的人](unidentified-people.md) + 3 [个已识别的人](identified-people.md)。
