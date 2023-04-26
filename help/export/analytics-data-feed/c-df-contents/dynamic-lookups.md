---
title: 动态查找
description: 了解动态查找的含义以及如何启用它们。 包括运营商、移动设备属性和操作系统类型。
source-git-commit: b6084fc34165ea602fce616e13b3adfcd7bdfdbd
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# 动态查找

动态查找允许您在数据馈送中接收其他查找文件，否则将不可用。 此设置允许随每个数据馈送文件一起发送以下查找表：

* **运营商名称**:为 `carrier` 列。 包含的文件名为 `carrier.tsv`.
* **移动设备属性**:为 `mobile_id` 列，包括每个移动设备跟踪的所有功能。 包含的文件名为 `mobile_attributes.tsv`.
* **操作系统类型**:为 `os` 列。 两者兼有 `operating_systems.tsv` 和 `operating_system_type.tsv` 使用 `os` 列作为键，但仅 `operating_system_type.tsv` 是动态查找。

## 启用动态查找

如果要接收上述查找文件，您必须满足以下所有先决条件：

* 键列必须包含在数据馈送中。
   * 对于 `carrier.tsv`，您必须包括 `carrier`.
   * 对于 `mobile_attributes.tsv`，您必须包括 `mobile_id`.
   * 对于 `operating_system_type.tsv`，您必须包括 `os`.
* 以下列必须 **排除**. 如果数据馈送中包含其中任何列，则不会包含其他查找表。
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

在您的数据馈送满足列包含和排除要求后，请联系客户关怀团队，并提供数据馈送ID，并请求启用动态查找。

## 查找头引用

这些查找文件的列标题不会随时间而改变，因此标题不会包含在每个数据馈送文件中。 将这些列标题用作引用，或下载它们各自的 `.tsv` 文件。

+++**运营商名称**
下载 [carrier_headers.tsv](assets/carrier_headers.tsv) 或引用下面的标题。

`carrier`
`Carrier Name`
+++

+++**移动设备属性**
下载 [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) 或引用下面的标题。

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**操作系统类型**
下载 [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) 或引用下面的标题。

`os`
`Operating System Type`
+++