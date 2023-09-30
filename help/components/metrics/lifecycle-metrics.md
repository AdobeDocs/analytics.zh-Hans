---
name: Mobile lifecycle metrics
description: 量度基于使用Mobile SDK收集的数据。
feature: Metrics
source-git-commit: fa9ba599ccc3d6fe1176e6b2ec20457f30cb5959
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 52%

---

# 移动生命周期量度

| 生命周期量度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| 首次启动次数 | | `a.InstallEvent` |
| 升级 | | `a.UpgradeEvent` |
| 启动项 | | `a.LaunchEvent` |
| 崩溃 | | `a.CrashEvent` |
| 会话总时长 | | 待定 |
| 总操作时间 | | `a.action.time.total` |
| 应用程序中的操作时间 | | `a.action.time.inapp` |
| 生命周期值（事件） | | `a.ltv.amount` |

{style="table-layout:auto"}
