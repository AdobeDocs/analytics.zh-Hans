---
description: 有关 Activity Map 中链接跟踪的常见问题解答。
title: 链接跟踪常见问题解答
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 64%

---


# 链接跟踪常见问题解答

有关 Activity Map 中链接跟踪的常见问题解答。

>[!CAUTION]
>
>启用 Activity Map 跟踪后，**您可能会收集个人身份识别信息 (PII) 数据。**&#x200B;此类数据可用于（单独或与其他信息配合使用）识别、联系或查找个人，或者在上下文中识别个人。

以下是使用 Activity Map 跟踪收集 PII 数据的一些已知案例：

* `Mailto` 链接。Mailto 链接是一种 HTML 链接，它可以激活计算机上的默认邮件客户端来发送电子邮件。
* 用户登录后可能出现在网站页眉/页脚的 `User ID` 链接。
* 在金融机构的网站中，账号可能会显示为链接。单击该链接将收集链接的文本。
* 在医疗保健网站中，PII 数据也可能会显示为链接。单击这些链接将收集链接的文本，进而收集 PII 数据。

<table id="table_0951EAC617344156BAE43000CCD838AF">
 <tbody>
  <tr>
   <td colname="col1"> <b>问：何时进行链接跟踪？</b> </td>
   <td colname="col2"> 答：当用户单击页面时，会开始识别 Activity Map 链接和区域。 </td>
  </tr>
  <tr>
   <td colname="col1"> <b>问：默认情况下，会跟踪哪些内容？</b> </td>
   <td colname="col2"> 答：如果针对某个元素执行了单击事件，则必须对该元素进行一些检查，以确定 AppMeasurement 是否将该元素视为链接。检查内容如下：
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0">
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">这是带有<code>"href"</code>属性的<code>&lt;A&gt;</code>或<code>&lt;AREA&gt;</code>标签吗？ </li>
     <li id="li_77828D24D54343E5B9A1FF7345221781">是否存在设置<code>s_objectID</code>变量的<code>"onclick"</code>属性？ </li>
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">这是带有值或子文本的<code>&lt;INPUT&gt;</code>标记还是<code>&lt;SUBMIT&gt;</code>按钮？ </li>
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">这是<code>&lt;INPUT&gt;</code>标记，类型为<code>&lt;IMAGE&gt;</code>和<code>"src"</code>属性吗？ </li>
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">这是<code>&lt;BUTTON&gt;</code>吗？ </li>
    </ul>
    如果以上任一问题的回答为<b>是</b>，则该元素将被视为链接，需要对其进行跟踪。<br/>
     <br/>
    重要说明：AppMeasurement不将具有该属 <code>type="button"</code> 性的按钮标签视为链接。请考虑在按钮标签上删除<code>type="button"</code>并改为添加<code>role="button"</code>或<code>submit="button"</code>。 <br/>
     <br/>
    重要说明：AppMeasurement将具有该开始 <code>"href"</code> 的锚 <code>"#"</code> 点标签视为内部目标位置，而不是链接（因为您不会离开页面）。默认情况下，Activity Map 不跟踪这些内部目标位置，而是仅跟踪将用户导航到新页面的链接。 </td> 
  </tr>
  <tr>
   <td colname="col1"> <b>问：Activity Map 如何跟踪其他可视化 HTML 元素？</b> </td>
   <td colname="col2">
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5">
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>通过 <code>s.tl()</code> 函数</b>  <br/>
       <br/>
      如果通过调用进行 <code>s.tl()</code> 了单击，则Activity Map还将收到此单击事件，并确定是否 <code>linkName</code> 找到字符串变量。在执行<code>s.tl()</code>期间，将该<code>linkName</code>设置为Activity Map链接ID。 发起<code>s.tl()</code>调用的已点击元素将用于确定区域。 <br/>
       <br/>
      示例：  <br/>
       <br/>
      <code>&lt;img&nbsp;onclick="s.tl(true,'o','abc')"&nbsp;src="someimageurl.png"/&gt;</code><br/>
       
     </li>
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>通过 <code>s_objectID</code> </b> <br/>
       <br/>
      variableExample: <br/>
       <br/>
      <code>&lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt;</code><br/>
      <code>&lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;</code><br/>
      <code>&nbsp;&nbsp;Link&nbsp;Text&nbsp;Here</code><br/>
      <code>&lt;/a&gt;</code> <br/>
       <br/>
      重要说明：请注意，在Activity Map中使<code>;</code>用时需要尾随分 <code>s_objectID</code> 号()。
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>问：能否提供一些将被跟踪的链接示例？</b> </td>
   <td colname="col2">
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA">
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0">
      <code>&lt;a&nbsp;href="/home"&gt;Home&lt;/a&gt;</code>
     </li>
     <li id="li_76F3DB36ED734132A2386871E6EB4929">
      <code>&lt;input&nbsp;type="submit"&nbsp;value="Submit"/&gt;</code>
     </li>
     <li id="li_10CF9EDA224645169E7CDF74956DB98B">
      <code>&lt;input&nbsp;type="image"&nbsp;src="submit-button.png"/&gt;</code>
     </li>
     <li id="li_9FA171D7F49547E798DE21869F73A402">
      <code>&lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code>
     </li>
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF">
      <code>&lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/div&gt;</code>
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>问：能否提供一些不被跟踪的链接示例？</b> </td>
   <td colname="col2">
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547">
     <li id="li_99372060646B43EF94C13A9C682CE693">原因：锚标记不具备有效的 <code>"href"</code> <br/>
       <br/>
      <code>&lt;a&nbsp;name="innerAnchor"&gt;Section&nbsp;header&lt;/a&gt;</code><br/>
       
     </li>
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">原因：<code>s_ObjectID</code>和<code>s.tl()</code>都不存在<br/>
       <br/>
      <code>&lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code><br/>
       
     </li>
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">原因：<code>s_ObjectID</code>和<code>s.tl()</code>都不存在<br/>
       <br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;</code><br/>
       
     </li>
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">原因：<code>"src"</code>属性缺少表单<code>input</code>元素<br/>
       <br/>
      <code>&lt;input&nbsp;type="image"/&gt;</code><br/>
       
     </li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>
