---
description: “自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。eVar 可以是基于访问的，其功能与 Cookie 类似。在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。
keywords: eVar
seo-description: “自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。eVar 可以是基于访问的，其功能与 Cookie 类似。在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。
seo-title: 转化变量 (eVar)
solution: Analytics
title: 转化变量 (eVar)
topic: 管理工具
uuid: eed0cb1-0735-4142-be21-43f264216 b50
translation-type: tm+mt
source-git-commit: 26ea8e41b9a45c87c339d4d4d56c914fbc44bae8

---


# 转化变量 (eVar)

“自定义分析转化变量”（或 eVar）置于您网站所选网页的 Adobe 代码中。其主要目的是在自定义市场营销报告中划分转化成功量度区段。eVar 可以是基于访问的，其功能与 Cookie 类似。在预先设定的一段时间内，传递到 eVar 变量的值将始终“跟随”着用户。

为访客设置 eVar 值之后，Adobe 会自动记住该值，直到它过期。eVar 值处于活动状态时，访客遇到的成功事件将计入该 eVar 值。

eVar 最适合用于度量原因和影响，例如：

* 哪些内部促销活动会影响收入
* 哪些横幅广告最终会导致用户注册
* 在下订单前所用的内部搜索次数

如果需要进行流量测量或路径分析，则建议您使用流量变量。

>[!NOTE]
>
>只有一个值可存储在图像请求中的eVar中。如果一个 eVar 值中需要多个值，我们建议您实施[列表变量 (list vars)](https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html)。

## 转化变量 - 描述 {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

[编辑转换变量时使用的字段描述](../../../admin/admin/conversion-var-admin/t-conversion-variables-admin.md#task_051920D9B3E24A00A28F32EEBBB0EF97)。

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>元素 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 名称 </span> </p> </td> 
   <td colname="col2"> <p>转化变量的易记名称。此名称是常规报表引用 eVar 时所用的名称，并且该名称将用作左侧菜单中报表的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol">类型</span> </p> <p>（仅限 eVar） </p> </td> 
   <td colname="col2"> <p>变量值类型： </p> <p> <b>文本字符串</b>：</span> 捕获站点中使用的文本值。这是 eVar 最常见的类型，并且是默认设置。它与其他变量类似，其值是静态文本字符串。如果您要跟踪内部促销活动或内部搜索关键词等内容，则这是推荐的设置。 </p> <p> <b>计数器</b>：</span> 计算成功事件之前执行操作的次数。例如，如果使用 eVar 跟踪网站上的内部搜索，则将此值设置为<span class="uicontrol">文本字符串</span>以跟踪搜索词的使用。将此值设置为<span class="uicontrol">计数器</span>可累计搜索的次数，与使用的搜索词无关。例如，您可以使用计数器 eVar 来跟踪某人在进行购买前所用内部搜索的次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 分配 </span> </p> </td> 
   <td colname="col2"> <p>确定变量在成功事件之前收到多个值时，Analytics 如何分配事件的信用。支持的值包括： </p> <p> <b></b>最近：在eVar过期之前，最后一个eVar值始终接收成功事件的信用。 </p> <p> <b>原始值</b>：在eVar过期之前，第一个eVar始终接收成功事件的信用。 </p> <p> <b> 线性</b>：在所有eVar值中平均分配成功事件。由于线性分配实际仅能在一次访问内分配值，所以应将线性分配与 eVar 访问过期结合使用。 </p> <p>注意：将分配切换至线性或从线性切换分配可防止显示历史数据。在报表界面中混合多种分配类型可导致在报表中错报数据。例如，线性分配可能会在大量不同的 eVar 值间划分收入。更改回最近分配后，100% 的收入都与最近单个值关联。这种关联可能会导致用户得出不正确的结论。 </p> <p>为避免在报表中可能产生混淆，Analytics 在界面中不显示历史数据。虽然您不该只是为了访问历史数据而更改 eVar 分配设置，但如果您确定要将给定的 eVar 更改回初始分配设置，则可以查看历史数据。已记录的数据需要新的分配设置时，Adobe 建议使用新的 eVar，而非更改已积累大量历史数据的 eVar 的分配设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 过期时间</span> </p> </td> 
   <td colname="col2"> <p>指定一个时段或事件，eVar 值将在此时段或事件之后过期（即，不再接收成功事件的信用）。如果在 eVar 过期之后发生成功事件，则由“无”值接收该事件的信用（不激活任何 eVar）。 </p> <p>如果选择某个事件作为过期值，则变量仅在该事件发生时过期。如果未发生该事件，则变量从不过期。 </p> <p>可用的过期选项可分为四个主要类别： </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>在页面查看或访问级别。</b>页面查看或访问以外的转化事件与 eVar 无关联。 </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>基于时段，例如日、周、月或年。</b>指定时段以外的转化事件与 eVar 无关联。过期时段从设置变量后开始。eVar 根据为其设置的时间而过期，该时间的单位为秒（分钟、小时、天、月，等等）： 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTE=60 秒 </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">HOUR=3600 秒（60 分钟） </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DAY=86400 秒（24 小时） </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">WEEK=604800 秒（7 天） </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MONTH=2678400 秒（31 天） </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">QUARTER=8035200 秒（93 天 - 3 个月，每个月 31 天） </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">YEAR=31536000 秒（365 天） </li> 
      </ul> <p> </p> <p>如果访问从星期一上午 7:00 开始，并在该访问期间于上午 7:15 设置了 eVar，则过期时间如下所示： </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">一天过期：eVar 在星期二上午 7:15 过期。 </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">一周过期：eVar 在下个星期一上午 7:15 过期。 </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">一个月过期：eVar 在自本星期一起 31 天后的上午 7:15 过期。 </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>特定转化事件。</b>在指定的特定事件之后触发的任何其他转化事件与 eVar 相关联。 </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>从不。</b> 只要<span class="varname"> isitorID</span> cookie保持不变，任何时间量可在eVar和事件之间传递。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 状态</span> </p> <p>（仅限 eVar） </p> </td> 
   <td colname="col2"> <p>定义 eVar 状态： </p> <p><b>禁用</b>：</span> 禁用eVar。从转化变量列表中删除 eVar。 </p> <p> <b>无子关系</b>：</span> 防止您断开子关系的eVar。 </p> <p> <b>基本子关系</b>： </span>允许您按具有完全子关系的任何报告划分eVar(例如产品或营销活动)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol">重置</span> </p> </td> 
   <td colname="col2"> <p>在 eVar 中重置任何现有值。 </p> <p>在重新安排 eVar 的用途时使用此设置，这样可以将旧值混合到新报表中。重置不会擦除历史数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 促销</span> </p> <p>（仅限 eVar） </p> </td> 
   <td colname="col2"> <p>促销变量可遵循以下两种语法之一： </p> <p> <b>产品语法</b>：</span> 将eVar值关联到某个产品。注意：如果选择“产品语法”，则“促销捆绑事件”区域会处于禁用状态，且无法选择该区域来进行编辑。对于此语法，“捆绑事件”不适用。 </p> </p> <p> <b>转换变量语法</b>：</span> 仅在发生绑定事件时将eVar与产品关联。在此情况下，您可以选择充当捆绑事件的事件。 </p> <p>更改此设置时，如果不相应更新 JavaScript 代码，则会导致数据丢失。请参阅<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=var_merchandising" format="http" scope="external">促销变量</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> 促销捆绑事件</span> </p> <p>（仅限 eVar） </p> </td> 
   <td colname="col2"> <p>如果将“促销”设置为<span class="uicontrol">转化变量语法</span>，则所选事件会将当前 eVar 值与产品进行捆绑。 </p> <p>要使用“捆绑事件”，请将“分配”设置为“最近”<span class="uicontrol"></span>。如果将“分配”设为“原始值”<span class="uicontrol"></span>，则第一个 eVar 产品捆绑将在 eVar 过期之前一直有效。 </p> </td> 
  </tr> 
 </tbody> 
</table>