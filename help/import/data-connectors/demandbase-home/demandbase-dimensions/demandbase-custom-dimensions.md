---
description: 列出可在Adobe集成向导的步骤中提供的可选维度标识符。
seo-description: 列出可在Adobe集成向导的步骤中提供的可选维度标识符。
seo-title: Demandbase自定义维度
title: Demandbase自定义维度
uuid: d162104-3aa2-46b9-a536-4a8 fb792 b69 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Demandbase自定义维度{#demandbase-custom-dimensions}

列出可在Adobe集成向导的步骤中提供的可选维度标识符。

如果您不确定要输入到向导中的确切API ID，请咨询Demandbase代表。

>[!IMPORTANT]
>
>强烈建议不要将IP地址包含为自定义维度。极少的唯一值可能会导致报告出现性能问题。此外，IP地址已经通过Adobe数据仓库报告提供作为报告选项。

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 维度 </th> 
   <th colname="col2" class="entry"> API ID </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> ISP </td> 
   <td colname="col3"> 指示识别的单位是否归类为ISP。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marketing Alias </td> 
   <td colname="col2"> marketing_ alias </td> 
   <td colname="col3"> 已清理和/或缩短组织名称(32个或更少)，用于广告、消息或营销副本中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 帐户观察标记 </td> 
   <td colname="col2"> seat_ list(custom) </td> 
   <td colname="col3">客户端定义的标记数量不限，可根据组织的API响应数据添加。 <p><b></b>示例：如果您有一个名为Q Target的Watch标签，则API字段将 </p> <code> watch_ list_ q4_ target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 财富1000 </td> 
   <td colname="col2"> 财富_1000 </td> 
   <td colname="col3"> 指示该组织是否位于“财富1000”列表中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> 指示组织是否位于Forbes2000列表中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 员工计数 </td> 
   <td colname="col2"> employee_ count </td> 
   <td colname="col3"> 组织任职人数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年度销售 </td> 
   <td colname="col2"> annual_ Sales </td> 
   <td colname="col3"> 对于公共实体，年度收入基于公司在所有地点的全球HQ公开记录。对于私营组织，其基于年度销售收入数字的共识估算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 电话号码 </td> 
   <td colname="col2"> 电话 </td> 
   <td colname="col3"> 所标识单位的电话号码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 街道地址 </td> 
   <td colname="col2"> stage_ address </td> 
   <td colname="col3"> 所标识组织的街道地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> 所标识的组织城市。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 省/州 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 所标识组织的状态。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国家/地区代码 </td> 
   <td colname="col2"> countrie_ code </td> 
   <td colname="col3"> 标识单位的ISO双字符国家/地区代码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国家/地区名称 </td> 
   <td colname="col2"> countrie_ name </td> 
   <td colname="col3"> 所标识组织的国家/地区的字符串值国家/地区名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zip </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> 所标识组织的国家/地区的邮政编码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 网站 </td> 
   <td colname="col2"> web_ site </td> 
   <td colname="col3"> 单位所使用的URL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stock Photker </td> 
   <td colname="col2"> stock_ ticker </td> 
   <td colname="col3"> 如果所标识的组织是公开上市的，则股票行情报价人。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主要SIC Code </td> 
   <td colname="col2"> mary_ sic </td> 
   <td colname="col3"> 为所标识组织分配的一致SIC代码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 纬度 </td> 
   <td colname="col2"> 纬度 </td> 
   <td colname="col3"> 确定单位所在组织的纬度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 经度 </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> 发行商确定所标识组织的位置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 流量 </td> 
   <td colname="col2"> 流量 </td> 
   <td colname="col3"> 网站流量的数量，估计为低、中、高或非常高。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> 表示确定的公司主要向其他企业销售。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> 表示确定的公司主要向消费者或个人销售。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 技术洞察 </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 客户通过类别、供应商和产品定义的最多75种技术类别，用于使用定位和/或自定义广告、消息或营销副本。 </td> 
  </tr> 
 </tbody> 
</table>

