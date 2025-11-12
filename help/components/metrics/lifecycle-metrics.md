---
name: Mobile lifecycle metrics
description: 基于使用 Mobile SDK 收集的数据的量度。
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '37'
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
