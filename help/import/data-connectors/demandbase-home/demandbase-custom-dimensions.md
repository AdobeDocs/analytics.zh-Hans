---
description: 列出可在 Adobe 集成向导的步骤 4 中提供的可选维度标识符。
title: Demandbase 自定义维度
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Demandbase 自定义维度{#demandbase-custom-dimensions}

列出可在 Adobe 集成向导的步骤 4 中提供的可选维度标识符。

如果您不确定要输入到向导中的确切 API ID，请咨询 Demandbase 代表。

>[!IMPORTANT]
>
>强烈建议不要将 IP 地址作为自定义维度包含在内。极高数量的唯一值可能会导致报表出现性能问题。此外，IP 地址已通过 Adobe Data Warehouse 报表提供为报表选项。

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
   <td colname="col3"> 指示已识别的组织是否被分类为 ISP。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 营销别名 </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> 在广告、消息或营销副本中使用的已清理和/或缩短的组织名称（32 个字符或更少）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 帐户监视标记 </td> 
   <td colname="col2"> watch_list（自定义） </td> 
   <td colname="col3">客户定义的不限数量的标记集，可按组织添加到其 API 响应数据中。 <p><b>示例</b>：如果您有一个名为“Q4 Target”的监视标记，则 API 字段将为 </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 财富 1000 强 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> 指示该组织是否列在《财富》1000 强名单中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 福布斯 2000 强 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> 指示该组织是否列在《福布斯》2000 强名单中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 员工计数 </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> 组织雇用的人数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 年销售额 </td> 
   <td colname="col2"> annual_sales </td> 
   <td colname="col3"> 对于公共实体，年收入基于公司报告的全球总部在所有地点的公共记录。对于私营组织，年收入基于对年度销售收入额的一致估计。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 电话号码 </td> 
   <td colname="col2"> phone </td> 
   <td colname="col3"> 已识别的组织的电话号码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 街道地址 </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> 已识别的组织的街道地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 城市 </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> 已识别的组织所在的城市。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 省/自治区/直辖市 </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> 已识别的组织所在的省/自治区/直辖市。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国家/地区代码 </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> 已识别的组织所在国家/地区的 ISO 双字符代码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 国家/地区名称 </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> 已识别的组织所在国家/地区的名称字符串值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 邮政编码 </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> 已识别的组织所在国家/地区/省/自治区/直辖市的邮政编码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 网站 </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> 已识别的组织使用的 URL。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 股票报价 </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> 股票报价（如果已识别的组织已公开交易）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主要 SIC 代码 </td> 
   <td colname="col2"> primary_sic </td> 
   <td colname="col3"> 为已识别的组织分配的一致 SIC 代码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 纬度 </td> 
   <td colname="col2"> latitude </td> 
   <td colname="col3"> 已识别的组织所在位置的纬度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 经度 </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> 已识别的组织所在位置的经度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 流量 </td> 
   <td colname="col2"> traffic </td> 
   <td colname="col3"> 估计为低、中、高或非常高的网站流量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> 指示已识别公司的销售业务主要面向其他企业。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> 指示已识别公司的销售业务主要面向消费者或个人。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 技术分析 </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> 客户通过类别、供应商和产品定义的最多 75 个技术类别，用于定位和/或自定义广告、消息或营销副本。 </td> 
  </tr> 
 </tbody> 
</table>

