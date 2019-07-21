---
description: 用于根据 page_event 值确定点击类型的对照表。
keywords: 数据馈送；page；活动；page_ event；post_ page_ event
seo-description: 用于根据 page_event 值确定点击类型的对照表。
seo-title: 页面事件对照
solution: Analytics
title: 页面事件对照
topic: Reports & Analytics
uuid: 73af597c-5560-466e-94b2-ddd1 d64797 c8
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# 页面事件对照

用于根据 page_event 值确定点击类型的对照表。

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 点击类型 </th> 
   <th colname="col02" class="entry"> page_event 值 </th> 
   <th colname="col2" class="entry"> post_page_event 值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 页面查看 </td> 
   <td colname="col02"> 与后处理相同 </td> 
   <td colname="col2"> <p>对于所有页面查看均为 0（<code>s.t()</code> 调用） </p> <p>对于来自移动 SDK 的 <code>trackState</code> 调用为 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 链接跟踪 </td> 
   <td colname="col02"> <p>对于“其他链接”为 10 </p> <p>对于来自移动 SDK 的 <code>trackAction</code> 和生命周期调用为 10。 </p> <p>对于“下载链接”为 11 </p> <p>对于“外部或退出链接”为 12 </p> </td> 
   <td colname="col2"> <p>对于“其他链接”为 100 </p> <p>对于来自移动 SDK 的 <code>trackAction</code> 和生命周期调用为 100。 </p> <p>对于“下载链接”为 101 </p> <p>对于“外部或退出链接”为 102 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 里程碑视频 </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 - 媒体开始事件 </p> <p>32 - 仅限媒体更新事件(不执行任何eVar或任何其他变量处理) </p> <p>33 - 媒体 + 其他变量更新事件（包括 eVar 和其他变量处理） </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76 - 媒体开始事件 </p> <p>77 - 仅媒体更新事件（不执行任何 eVar 或任何其他变量处理） </p> <p>78 - 媒体 + 其他变量更新事件（包括 eVar 和其他变量处理） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>心率视频 </p> </td> 
   <td colname="col02"> 与后处理相同 </td> 
   <td colname="col2"> <p> 50 =（非黄金时段）媒体流开始 </p> <p> 51 =（非黄金时段）媒体流关闭（完成/结束） </p> <p> 52 =（非黄金时段）媒体流擦除 </p> <p> 53 =（非黄金时段）媒体流保持连接 </p> <p> 54 =（非黄金时段）媒体流广告开始 </p> <p> 55 =（非黄金时段）媒体流广告关闭（完成/结束） </p> <p> 56 =（非黄金时段）媒体流广告擦除 </p> <p> 60 = 黄金时段媒体流开始 </p> <p> 61 = 黄金时段媒体流关闭（完成/结束） </p> <p> 62 = 黄金时段媒体流擦除 </p> <p> 63 = 黄金时段媒体流保持连接 </p> <p> 64 = 黄金时段媒体流广告开始 </p> <p> 65 = 黄金时段媒体流广告关闭（完成/结束） </p> <p> 66 = 黄金时段媒体流广告擦除 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 调查 </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 目标分析 </td> 
   <td colname="col02"> 70 - 指示包含目标活动数据的点击。70 指示点击量与 Analytics 调用有无关联。 </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

