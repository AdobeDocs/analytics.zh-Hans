---
title: 客户视角
description: 指定当应用程序处于前台或后台时是否发生了移动设备应用程序点击。
feature: Appmeasurement Implementation
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# 客户视角

`customerPerspective`变量指定在应用程序处于前台还是后台时是否发生了移动设备应用程序点击。 它作为`cp`查询参数发送到Adobe数据收集，并填充[点击类型](/help/components/dimensions/hit-type.md)维度。

## 有效值

`customerPerspective`接受以下字符串值：

* `foreground`：点击发生在应用程序处于活动使用状态时。
* `background`：点击发生在应用程序在后台运行时，例如位置更新或由推送通知触发的点击。

## 如何设置此变量

Adobe Mobile SDK（版本4.13.6及更高版本）自动设置`customerPerspective`；通常不会手动进行设置。 通过AppMeasurement从浏览器发送的点击始终报告为`foreground`。 如果点击中不存在变量，则该点击将被视为前台点击。

## 对报告的影响

前台/后台区分会影响访问的处理方式：

* 仅当访问至少包含一次前台点击时才被计数。
* 后台点击仍可归因于转化事件，并可通过虚拟报表包中的[上下文感知会话](/help/components/vrs/vrs-mobile-visit-processing.md)进行分析。 在衡量推送通知的有效性时，此行为非常有用。
