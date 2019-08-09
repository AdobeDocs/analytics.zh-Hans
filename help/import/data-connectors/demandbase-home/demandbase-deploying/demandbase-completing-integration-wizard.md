---
description: 要激活集成，您必须在数据连接器界面中完成配置向导。
seo-description: 要激活集成，您必须在数据连接器界面中完成配置向导。
seo-title: 完成Adobe集成向导
title: 完成Adobe集成向导
uuid: 75260b92-a6 f5-44b6-b3 ea-d5945 fdd1 bu
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 完成Adobe集成向导{#completing-the-adobe-integration-wizard}

要激活集成，您必须在数据连接器界面中完成配置向导。

1. 导航到Adobe Marketing Cloud中的数据连接器(以前称为Genesis)区域。
1. 启动Demandbase2.0集成向导。
1. 选择所需的报表包，并提供集成的名称。
1. 配置以下项目：

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 电子邮件地址 </td> 
   <td colname="col2"> 主要联系人的电子邮件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 描述 </td> 
   <td colname="col2"> (可选)此集成设置的说明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase API密钥 </td> 
   <td colname="col2"> 您可以从Demandbase代表获得此信息。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Custom Demandbase Dimension# N N </td> 
   <td colname="col2"> 这些是可选维度的ID。有关详细信息，请参阅Demandbase自定义维度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发送到Adobe Target </td> 
   <td colname="col2">如果为“true”，则也会使用隐藏mbox将Demandbase维度发送到Adobe Target。 <p>注意：必须在网页上实现配置的mbox. js文件才能收集维度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 配置以下变量映射项目：

   | 项目 | 描述 |
   |---|---|
   | Demandbase Dimensions | 从报表包中选择可用的eVar变量。 |
   | Demandbase Custom Dimensions(可选) | 从报表包中选择可用的eVar变量。 |

1. 配置自定义维度的名称(如果适用)。

   1. 如果选择在步骤中包含自定义维度，并在步骤中映射可选的eVar，则必须为这些维度提供友好名称。例如，如果选择输入“stock_ ticker”作为Custom Dimension1，则应将包含“Dimension1”的框更改为“Stock Timker”。
   1. **请勿** 修改标准维度的名称(即Demandbase SID、公司名称、行业等)。

1. 选中此框，将自动为您创建Demandbase Integration仪表板(建议)。
1. 查看所有配置项目，然后单击 **[!UICONTROL “立即激活]**”。

