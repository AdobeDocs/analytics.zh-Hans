---
description: 列出可在Adobe集成向导的步骤4中提供的可选维标识符。
seo-description: 列出可在Adobe集成向导的步骤4中提供的可选维标识符。
seo-title: Demandbase自定义维度
title: Demandbase自定义维度
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Demandbase自定义维度{#demandbase-custom-dimensions}

列出可在Adobe集成向导的步骤4中提供的可选维标识符。

如果您不确定要进入向导的确切API ID，请咨询Demandbase代表。

>[!IMPORTANT]
>
>强烈建议不要将IP地址作为自定义维包含在内。 极高的唯一值可能导致报告出现性能问题。 此外，IP地址已通过Adobe数据仓库报告提供为报告选项。

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
   <td colname="col2"> isp </td> 
   <td colname="col3"> 指示标识的组织是否被分类为ISP。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 营销别名 </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> 已清理和／或缩短的组织名称（32个字符或更少），可用于广告、消息或营销副本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 帐户监视标记 </td> 
   <td colname="col2"> watch_list（自定义） </td> 
   <td colname="col3">客户端定义的无限组合标记，可按组织添加到其API响应数据中。 <p><b>示例</b>:如果您有一个名为Q4 Target的监视标记，则API字段将 </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 财富1000强 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> 指示该组织是否列在《财富》1000强企业中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 《福布斯2000》 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> 指示该组织是否列在福布斯2000名单中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 员工数 </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> 组织中受雇的人数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年度销售 </td> 
   <td colname="col2"> annual_sales </td> 
   <td colname="col3"> 对于公共实体，年度收入是根据公司报告的全球总部在所有地点的公共记录得出的。 对于私营组织而言，其依据是对年度销售收入数字的一致估计。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 电话号码 </td> 
   <td colname="col2"> 电话 </td> 
   <td colname="col3"> 已识别的组织的电话号码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 街道地址 </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> 组织的街道地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> 城市 </td> 
   <td colname="col3"> 该组织所在的城市已查明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 省/州 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 已确定组织的状态。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国家/地区代码 </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> 已识别组织的ISO双字符国家／地区代码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国家/地区名称 </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> 标识的组织的国家／地区的字符串值国家／地区名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zip </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> 已识别组织的国家／州的邮政编码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 网站 </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> 所标识的组织使用的URL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 股票报价机 </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> 如果确定的组织是公开交易的，那么股票报价机构。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主SIC代码 </td> 
   <td colname="col2"> primary_sic </td> 
   <td colname="col3"> 为所确定的组织分配的一致SIC代码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 纬度 </td> 
   <td colname="col2"> 纬度 </td> 
   <td colname="col3"> 确定的组织位置的纬度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 经度 </td> 
   <td colname="col2"> 经度 </td> 
   <td colname="col3"> 已标识的组织的位置的经度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 流量 </td> 
   <td colname="col2"> 流量 </td> 
   <td colname="col3"> 估计为低、中或高或非常高的网站流量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> 表示标识的公司主要销售给其他业务。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> 指示标识的公司主要向消费者或个人销售产品。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Technology Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 客户通过类别、供应商和产品定义最多75个技术类别，用于定位和／或自定义广告、消息或营销副本。 </td> 
  </tr> 
 </tbody> 
</table>

