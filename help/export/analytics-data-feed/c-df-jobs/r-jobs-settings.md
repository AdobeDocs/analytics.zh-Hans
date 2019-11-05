---
description: 设置馈送后，某些设置可确定处理作业的频率。
keywords: 数据馈送；作业；设置；每日；每小时；每小时数据馈送的数据回填；回填
seo-description: 设置馈送后，某些设置可确定处理作业的频率。
seo-title: 作业设置
solution: Analytics
title: 作业设置
uuid: e124b4f1-0168-4eaa-8657-19207b2f263f
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# 作业设置

设置源时，某些设置会确定处理作业的频率。

使用以下设置来配置作业处理次数。这些设置是在馈送级别，而不是在作业级别设置的。

<table id="table_2070F73212F245E98DADC6B5DFDB1C72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设置 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 每日 </td> 
   <td colname="col2"> <p>每日数据是以单个压缩文件的形式提交的。文件的大小上限为 2GB。如果文件的未压缩数据大于 2GB，则会创建额外文件。您每天会收到一次性提交的所有文件。 </p> <p>每个文件按以下格式命名： </p> <p> <span class="filepath"> <span class="varname"> reportsuite</span>-<span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每小时（默认） </td> 
   <td colname="col2"> <p>每小时的数据以单个压缩文件的形式提交，其中包含该小时内收到的所有数据。您每天收到 24 个不同的提交，每个文件会在该小时的数据经过处理后进行提交。 </p> <p>术语“每小时”描述每次导出数据时发送的数据的时间范围，而不是发送的时间范围。 每小时数据馈送会尽最大努力进行处理和提交。 </p> <p>对于每小时的数据馈送，预期95%的馈送将在该小时的数据结束后的12小时内交付。 对于大流量报表包的数据馈送，可能需要更长的时间进行处理和提交。 </p> <p>接收每小时数据馈送与接收包含多个文件提交的每日馈送有所不同。当接收每小时数据馈送时，每天的数据会根据该小时收集的数据分成 24 个文件，每个文件会在可用时立即提交。以多个文件提交的每日馈送会在处理前一天的数据后每天提交一次，并会根据收集的数据量以 2 GB 增量进行拆分。 </p> <p>每个文件按以下格式命名： </p> <p> <span class="filepath"> <span class="varname"> reportsuite</span>-<span class="varname"> date</span>-<span class="varname"> hour</span>.tar</span> </p> <p>请参阅<a href="/help/export/analytics-data-feed/c-df-contents/jobs-faq.md"  >作业常见问题解答</a>，了解有关影响每小时馈送的因素的详细信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 针对每小时数据馈送的数据回填 </td> 
   <td colname="col2"> <p>如果您在设置新的每小时数据馈送时需要以前的日期数据，那么 60 天之前的日期数据将以每日格式提供，而不会以每小时格式提供。 </p> <p>在此情况下，您不会收到这些日期的 24 个独立交付内容，只会收到以午夜作为时间戳的一个交付内容，其中包含当天的所有数据。如果您需要这种回填类型，请务必确保配置了 ETL，以处理每日的交付内容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

