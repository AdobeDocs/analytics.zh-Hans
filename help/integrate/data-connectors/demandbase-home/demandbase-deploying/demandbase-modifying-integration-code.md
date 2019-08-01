---
description: 在大多数情况下，您无需对由“数据连接器”向导生成的集成代码进行任何修改。
seo-description: 在大多数情况下，您无需对由“数据连接器”向导生成的集成代码进行任何修改。
seo-title: 修改集成代码
title: 修改集成代码
uuid: 3f49a29b-ad38-4967-894a-ef7 ef4 d268 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Modifying the Integration Code{#modifying-the-integration-code}

在大多数情况下，您无需对由“数据连接器”向导生成的集成代码进行任何修改。

但是，如果您需要进行调整，则下面介绍一些代码设置。

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码设置 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">Adobe Analytics图像请求在进入Analytics集合服务器之前等待Demandbase数据的最大毫秒数。 <p>注意：此设置适用于可能通过集成模块运行的所有集成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._key </td> 
   <td colname="col2"> Demandbase API密钥。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ apiURL </td> 
   <td colname="col2"> Demandbase API的URL模板。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._delim </td> 
   <td colname="col2"> 将Demandbase维度值发送到Adobe Analytics时用于分隔Dimenbase维度值的分隔符。更改此设置可能导致默认的分类规则无法正常工作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ sett </td> 
   <td colname="col2">如果为true，则集成代码将尝试使用隐藏mbox将Demandbase维度发送到Adobe Target作为配置文件参数。 <p>注意：这要求页面上存在mbox. js代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ tntVarPrefix </td> 
   <td colname="col2"> 在发送到Adobe Target之前，此字符串会被前缀为每个Demandbase维度名称。例如，如果此设置的值为“db_”，则维度“行业”将作为“db_ industry”发送到Adobe Target。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ DimensArray </td> 
   <td colname="col2"> 发送到Adobe Analytics的标准Demandbase维度。建议您不要修改此设置。“max_ size”属性是在截断之前允许维度的允许字符数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ dimensionSarayCustom </td> 
   <td colname="col2"> 发送到Adobe Analytics的自定义Demandbase维度。“max_ size”属性是在截断之前允许维度的允许字符数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ CName </td> 
   <td colname="col2"> 用于保持Demandbase API通信状态的会话cookie的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ contextName </td> 
   <td colname="col2"> 用于向Adobe Analytics发送标准维度的ContextData变量的名称。建议您不要修改此设置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ ContextNameCMS </td> 
   <td colname="col2"> 用于向Adobe Analytics发送自定义维度的ContextData变量的名称。建议您不要修改此设置。 </td> 
  </tr> 
 </tbody> 
</table>

