---
description: 用于根据 page_event 值确定点击类型的对照表。
keywords: Data Feed;page;event;page_event;post_page_event
solution: Analytics
title: 页面事件对照
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# 页面事件对照

用于根据 page_event 值确定点击类型的对照表。

| 点击类型 | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| 页面查看 | 0:来自移动SDK的 `trackState` 所有页面查看调用和调用 | 与 `post_page_event` |
| 链接跟踪 | 10:移动SDK的 `trackAction` 11中的自定义链接和<br>调用：下载链接<br>12:退出链接 | 100:移动SDK' `trackAction` s<br>101中的自定义链接和调用：下载链接<br>102:退出链接 |
| 里程碑视频 | 31:媒体开始<br>32:媒体更新（无其他变量处理）<br>33:媒体更新（使用其他变量） | 76:媒体开始<br>77:媒体更新（无其他变量处理）<br>78:媒体更新（使用其他变量） |
| 心率视频 | 50:媒体流开始（非Primetime）<br>51:媒体流关闭（非Primetime）<br>52:媒体流擦洗（非Primetime）<br>53:媒体流保持活力（非Primetime）<br>54:媒体流广告开始（非Primetime）<br>55:媒体流和结束（非Primetime）<br>56:媒体流和擦洗（非Primetime）<br>60:Primetime媒体流起<br>61:Primetime媒体流结束<br>62:Primetime媒体流擦洗<br>63:黄金时段媒体流保持活<br>力64:Primetime媒体流广告<br>65:Primetime媒体流和结束<br>66:Primetime媒体流和擦洗 | 与 `post_page_event` |
| 调查 | 40:从Survey生成的任何调用 | 80:从Survey生成的任何调用 |
| 目标分析 | 70:命中包括目标活动数据 | 与 `post_page_event` |
