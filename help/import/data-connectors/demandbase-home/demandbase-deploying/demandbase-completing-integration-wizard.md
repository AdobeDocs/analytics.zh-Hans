---
description: 要激活集成，必须在数据连接器界面中完成配置向导。
seo-description: 要激活集成，必须在数据连接器界面中完成配置向导。
seo-title: 完成Adobe集成向导
title: 完成Adobe集成向导
uuid: 75260b92-a6f5-44b6-b3ea-d5945fdd1ecb
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 完成Adobe集成向导{#completing-the-adobe-integration-wizard}

要激活集成，必须在数据连接器界面中完成配置向导。

1. 导航到Adobe Experience cloud中的数据连接器（以前称为Genesis）区域。
1. 启动Demandbase 2.0集成向导。
1. 选择所需的报表包并提供集成的名称。
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
   <td colname="col2"> （可选）此集成设置的说明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase API密钥 </td> 
   <td colname="col2"> 您可以从Demandbase代表处获取此信息。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自定义Demandbase维度#N </td> 
   <td colname="col2"> 这些是8个可选维的ID。 有关详细信息，请参阅Demandbase自定义维。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发送到Adobe Target </td> 
   <td colname="col2">如果为“true”，则Demandbase维度也将使用隐藏的mbox发送到Adobe Target。 <p>注意： 必须在网页上实现已配置的mbox.js文件，才能收集维度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 配置以下变量映射项：

   | 项目 | 描述 |
   |---|---|
   | Demandbase维度 | 从报表包中选择一个可用的eVar变量。 |
   | Demandbase自定义维度（可选） | 从报表包中选择一个可用的eVar变量。 |

1. 配置自定义维的名称（如果适用）。

   1. 如果您选择在步骤4中包括自定义维，并在步骤5中映射可选eVar，则必须为这些维提供友好名称。 例如，如果选择输入“stock_ticker”作为“自定义维1”，则应将包含“维1”的框更改为“股票报价机”。
   1. 不 **要修改** 标准8维的名称（即Demandbase SID、公司名称、行业等）。

1. 选中此框，自动为您创建Demandbase Integration控制面板（建议）。
1. 查看所有配置项，然后单击“ **[!UICONTROL 立即激活]**”。

