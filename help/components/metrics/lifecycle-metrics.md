---
name: Mobile lifecycle metrics
description: 基于使用 Mobile SDK 收集的数据的量度。
feature: Metrics
source-git-commit: fa9ba599ccc3d6fe1176e6b2ec20457f30cb5959
workflow-type: ht
source-wordcount: '38'
ht-degree: 100%

---

# 移动存留期量度

| 存留期量度名称 | 描述 | 上下文数据变量 |
| --- | --- | --- |
| 首次启动次数 | | `a.InstallEvent` |
| 升级次数 | | `a.UpgradeEvent` |
| 启动次数 | | `a.LaunchEvent` |
| 崩溃次数 | | `a.CrashEvent` |
| 会话总时长 | | 待定 |
| 总操作时间 | | `a.action.time.total` |
| 应用程序中的操作时间 | | `a.action.time.inapp` |
| 存留期值（事件） | | `a.ltv.amount` |

{style="table-layout:auto"}
