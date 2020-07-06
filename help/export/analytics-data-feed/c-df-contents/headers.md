---
title: 数据源头资源
description: 在某些数据源中使用的静态头文件。
translation-type: tm+mt
source-git-commit: 07a9c983b0efa6e75765c1222cf056769417a341
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 0%

---


# 数据源头资源

某些数据服务不仅具有 `hit_data.tsv` 查找表， 这些额外数据文件取决于源的设置，并且通常不在源本身中包含头文件。 以下列表和下载是这些额外数据文件的参考。

## 移动属性

移动属性显示点击中移动设备的属性。 此文件在以下情况下显示：

* 已启用动态查找。 您组织中的支持代表可以使用所需的源ID联系客户关怀以启用动态查找。
* 包 `mobile_id` 含该列。
* 列 `user_agent` 被排除。 由于与DeviceAtlas签订了许可协议，因此需要排除此漏洞。

下 `mobile_attributes_headers.tsv`载或引用列表:

* `mobile_id`
* `Manufacturer`
* `Device`
* `Device Type`
* `Operating System`
* `Diagonal Screen Size`
* `Screen Height`
* `Screen Width`
* `Cookie Support`
* `Color Depth`
* `MP3 Audio Support`
* `AAC Audio Support`
* `AMR Audio Support`
* `Midi Monophonic Audio Support`
* `Midi Polyphonic Audio Support`
* `QCELP Audio Support`
* `GIF87 Image Support`
* `GIF89a Image Support`
* `PNG Image Support`
* `JPG Image Support`
* `3GPP Video Support`
* `MPEG4 Video Support`
* `3GPP2 Video Support`
* `WMV Video Support`
* `MPEG4 Part 2 Video Support`
* `Stream MP4 AAC LC Video Support`
* `Stream 3GP H264 Level 10b Video Support`
* `Stream 3GP AAC LC Video Support`
* `3GP AAC LC Video Support`
* `Stream MP4 H264 Level 11 Video Support`
* `Stream MP4 H264 Level 13 Video Support`
* `Stream 3GP H264 Level 12 Video Support`
* `Stream 3GP H264 Level 11 Video Support`
* `Stream 3GP H264 Level 10 Video Support`
* `Stream 3GP H264 Level 13 Video Support`
* `3GP AMR NB Video Support`
* `3GP AMR WB Video Support`
* `MP4 H264 Level 11 Video Support`
* `3GP H263 Video Support`
* `MP4 H264 Level 13 Video Support`
* `Stream 3GP H263 Video Support`
* `Stream 3GP AMR WB Video Support`
* `3GP H264 Level 10b Video Support`
* `MP4 ACC LC Video Support`
* `Stream 3GP AMR NB Video Support`
* `3GP H264 Level 10 Video Support`
* `3GP H264 Level 13 Video Support`
* `3GP H264 Level 11 Video Support`
* `3GP H264 Level 12 Video Support`
* `Stream HTTP Live Streaming Video Support`