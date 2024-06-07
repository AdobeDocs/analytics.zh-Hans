---
description: 用于根据 page_event 值确定点击类型的对照表。
keywords: 数据馈送;页面;事件;page_event;post_page_event
title: 页面事件对照
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '231'
ht-degree: 100%

---

# 页面事件对照

用于根据 page_event 值确定点击类型的对照表。

| 点击类型 | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| 页面查看 | 0：来自 Mobile SDK 的所有页面查看调用和 `trackState` 调用 | 与 `page_event` 的值相同 |
| 链接跟踪 | 10：Mobile SDK 中的自定义链接和 `trackAction` 调用<br>11：下载链接<br>12：退出链接 | 100：Mobile SDK 中的自定义链接和 `trackAction` 调用<br>101：下载链接<br>102：退出链接 |
| 里程碑视频 | 31：媒体开始<br>32：媒体更新（无其他变量处理）<br>33：媒体更新（使用其他变量） | 76：媒体开始<br>77：媒体更新（无其他变量处理）<br>78：媒体更新（使用其他变量） |
| 心率视频 | 50：媒体流开始（非 Primetime）<br>51：媒体流关闭（非 Primetime）<br>52：媒体流删除（非 Primetime）<br>53：媒体流继续存在（非 Primetime）<br>54：媒体流广告开始（非黄金时段）<br>55：媒体流广告结束（非 Primetime）<br>56：媒体流广告删除（非 Primetime）<br>60：Primetime 媒体流开始<br>61：Primetime 媒体流结束<br>62：Primetime 媒体流删除<br>63：Primetime 媒体流继续存在<br>64：Primetime 媒体流广告开始<br>65：Primetime 媒体流广告结束<br>66：Primetime 媒体流广告删除 | 与 `page_event` 的值相同 |
| 调查 | 40：从调查生成的任何调用 | 80：从调查生成的任何调用 |
| Analytics for Target | 70：点击包括 Target 活动数据 | 与 `page_event` 的值相同 |
