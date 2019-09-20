---
description: 在动态标签管理中创建数据元素。
keywords: 动态标签管理；数据元素；创建新数据元素；名称；类型；默认值；强制小写值；记住
seo-description: 在动态标签管理中创建数据元素。
seo-title: 创建数据元素
solution: Experience Cloud，分析，目标，动态标签管理
title: 创建数据元素
uuid: eacd5c60-6197-4129-a9e1-a39e9a58b38a
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 创建数据元素

在动态标签管理中创建数据元素。

1. [创建 Web 属性](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)（如果尚未创建）。
1. In the web property, click **[!UICONTROL Rules]** &gt; **[!UICONTROL Data Elements]**.
1. 单击&#x200B;**[!UICONTROL 创建新数据元素]**。
1. 填写以下字段和选项：

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> 选项</th> 
      <th class="chdeschd"> 描述</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>名称</strong></td> 
      <td class="chdesc stentry"> <p>营销人员可以识别的数据元素易记名称。例如， 
        <code>
          产品 ID
        </code>. </p> <p> <p>注意：规则生成器引用的是名称，而不是 ID。如果更改数据元素的名称，则必须在使用该数据元素的每个规则中更改其引用。 </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>类型</strong></td> 
      <td class="chdesc stentry"> <p> 指定从何处提取数据，如 JS 对象、CSS 选择器、Cookie、URL 参数或自定义脚本。 </p> <p>根据您选择的类型，显示的选项会有所不同。有关更多信息和示例，请参阅“动态标签管理产品文档”中的<a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html" format="html" scope="external">数据元素类型</a>。 </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>默认值</strong></td> 
      <td class="chdesc stentry"> <p>默认元素。此值可确保数据元素始终包含值，即使在 URL 参数不存在或动态标签管理找不到 URL 参数的情况下也是如此。 </p> <p> <p>注意：如果没有值和默认值，则不会返回任何内容。将不会设置任何引用该数据元素的变量。另外还请注意，如果是“自定义代码”数据元素，将忽略默认值字段。 </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>强制使用小写值</strong></td> 
      <td class="chdesc stentry"> <p>动态标签管理会自动将值转换为小写。 </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>记住此值多久</strong></td> 
      <td class="chdesc stentry"> <p>您希望动态标签管理记住此值多长时间。 </p> <p> 有效的值包括： </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>会话：基于会话的时间会因实施而异。会话数据元素设置为会话 Cookie。但是，此设置可以基于 Web 服务器或浏览器。它和市场营销报告与分析中使用的会话不相关。 </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>页面查看 </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>访客 </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   有关如何使用数据元素的更多信息，请参阅“Adobe 标签管理产品文档”中的[数据元素](https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html)。
1. Click **[!UICONTROL Save Data Element]**.
