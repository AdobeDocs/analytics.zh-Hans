---
title: 移动存留期量度
description: 基于使用 Mobile SDK 收集的数据的量度。
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 40
ht-degree: 100%

---

# 移动存留期量度

| 存留期量度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| 首次启动次数 | | `a.InstallEvent` |
| 升级次数 | | `a.UpgradeEvent` |
| 启动次数 | | `a.LaunchEvent` |
| 崩溃次数 | | `a.CrashEvent` |
| 会话总时长 | | |
| 总操作时间 | | `a.action.time.total` |
| 应用程序中的操作时间 | | `a.action.time.inapp` |
| 存留期值（事件） | | `a.ltv.amount` |

{style="table-layout:auto"}
