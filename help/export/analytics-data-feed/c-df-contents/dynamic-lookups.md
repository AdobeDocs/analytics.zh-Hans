---
title: 动态查找
description: 了解什么是动态查找以及如何启用它们。 包括运营商、移动设备属性和操作系统类型。
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
source-git-commit: 705a1716ed0205594fc6c75023c8805024ce7df7
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---

# 动态查找

动态查找允许您在数据馈送中接收其他查找文件，否则不可用。 此设置允许随每个数据馈送文件发送以下查找表：

* **运营商名称**：为`carrier`列提供其他上下文。 包含的文件名是`carrier.tsv`。
* **移动设备属性**：为`mobile_id`列提供额外的上下文，包括为每个移动设备跟踪的所有功能。 包含的文件名是`mobile_attributes.tsv`。
* **操作系统类型**：为`os`列提供替代上下文。 `operating_systems.tsv`和`operating_system_type.tsv`都使用`os`列作为键，但只有`operating_system_type.tsv`是动态查找。

## 启用动态查找 {#enable-dynamic-lookups}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_dynamic_lookups"
>title="启用动态查找"
>abstract="选择此选项可在数据馈送中接收其他查找文件，否则不可用。 此设置允许随每个数据馈送文件发送以下查找表：<ul><li>运营商名称</li><li>移动设备属性</li><li>操作系统类型</li></ul>"

<!-- markdownlint-enable MD034 -->

如果要接收上述查找文件，则必须满足以下所有先决条件：

* 数据馈送中必须包含键列。
   * 对于`carrier.tsv`，您必须包含`carrier`。
   * 对于`mobile_attributes.tsv`，您必须包含`mobile_id`。
   * 对于`operating_system_type.tsv`，您必须包含`os`。
* 以下列必须为&#x200B;**排除**。 如果数据馈送中包含这些列中的任一列，则不会包含`mobile_attributes.tsv`动态查找。
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

在您的数据馈送满足列包含和排除要求后，请联系客户关怀团队并提供数据馈送ID以启用动态查找。

## 查找标头引用

这些查找文件的列标题不会随着时间的推移而改变，因此标题不会包含在每个数据馈送文件中。 使用这些列标题作为引用，或下载它们各自的`.tsv`文件。

+++**运营商名称**
下载[carrier_headers.tsv](assets/carrier_headers.tsv)或引用下面的标头。

`carrier`
`Carrier Name`
+++

+++**移动设备属性**
下载[mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv)或引用下面的标头。

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
下载[operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv)或引用下面的标头。

`os`
`Operating System Type`
+++
