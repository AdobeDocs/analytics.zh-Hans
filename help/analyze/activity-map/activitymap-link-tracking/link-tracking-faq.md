---
description: 有关 Activity Map 中链接跟踪的常见问题解答。
seo-description: 有关 Activity Map 中链接跟踪的常见问题解答。
seo-title: 链接跟踪常见问题解答
solution: Analytics
title: 链接跟踪常见问题解答
topic: Activity Map
uuid: 10172073-b98 b-4950-8397-67a18 b37 b3 b4 b
translation-type: tm+mt
source-git-commit: d877f86dd5a05d0aa452ecebce47468ebf94cbb2

---


# 链接跟踪常见问题解答

有关 Activity Map 中链接跟踪的常见问题解答。

>[!CAUTION]
>
>By turning on Activity Map tracking, **you may be** **collecting personally identifiable information (PII) data.** This data can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual in context.

以下是使用 Activity Map 跟踪收集 PII 数据的一些已知案例：

* `Mailto` 链接。Mailto 链接是一种 HTML 链接，它可以激活计算机上的默认邮件客户端来发送电子邮件。
* `User ID` 用户登录后在网站的页眉/页脚中显示的链接。
* 在金融机构的网站中，账号可能会显示为链接。单击该链接将收集链接的文本。
* 在医疗保健网站中，PII 数据也可能会显示为链接。单击这些链接将收集链接的文本，进而收集 PII 数据。

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>问：何时进行链接跟踪？</b> <p> </p> </td> 
   <td colname="col2"> 答：当用户单击页面时，会开始识别 Activity Map 链接和区域。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>问：默认情况下，会跟踪哪些内容？</b> <p> </p> </td> 
   <td colname="col2"> 答：如果针对某个元素执行了单击事件，则必须对该元素进行一些检查，以确定 AppMeasurement 是否将该元素视为链接。检查内容如下： 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">是否属于包含 HREF 属性的 &lt;A&gt; 或 &lt;AREA&gt; 标记？ </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">是否属于设置 s_objectID 变量的单击属性？ </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">是否属于包含值或子文本的 INPUT 标记或 SUBMIT 按钮？ </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">是否属于包含 IMAGE 类型和 src 属性的 INPUT 标记？ </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">是否属于 &lt;Button&gt;？ </li> 
    </ul> <p>如果以上任一问题的回答为<b>是</b>，则该元素将被视为链接，需要对其进行跟踪。 </p> <p>重要：AppMeasurement 不会将具有属性 type="button" 的 Button 标记视为链接。请考虑删除按钮标记上的“type='button'”，然后添加 role="button" 或 submit="button"。 </p> <p>重要：包含以“#”开头的href的锚点标签被AppMeasurement视为内部目标位置，而不是链接(因为您不离开页面。)默认情况下，Activity Map不跟踪这些内部目标位置。它只跟踪将用户导航到新页面的链接。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>问：Activity Map 如何跟踪其他可视化 HTML 元素？</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>通过 <code>s.tl()</code> 函数</b> <p>如果单击操作是通过 s.tl 调用发生的，则 Activity Map 也会收到这个单击事件，并且会确认是否能够找到 linkName 字符串变量。在 s.tl 执行期间，该 linkName 将被设置为 Activity Map 链接 ID。发起 s.tl() 调用的被单击元素将用于确定区域。示例： </p> <p> 
       <code>&lt; img&amp; amp；nbsp；onclick="s. tl(true，'o'，'abc')"&amp; amp；nbsp；src=“somimageul. png”/&gt; </code>
  </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>通过 <code>s_objectID</code> 变量</b> <p>示例： </p> <p> 
       <code>&lt; img onclick="s_ objectID='abc'；“src=”somimageul. png"/&gt;&lt; a href="some-url.html"onclick="s_ objectID='abc'；“&gt;将文本链接到&lt;/a&gt; </code>
  </p> <p>重要：请注意，在 Activity Map 中使用 s_objectID 时，需要以分号 (;) 结尾。 </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>问：能否提供一些将被跟踪的链接示例？</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>&lt; a&amp; amp；nbsp；href="/home"&gt;“Home&lt;/a&gt;” </code>
  </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>&lt;输入和amp；nbsp；type=“commit”&amp; amp；nbsp；value=“Submit”/&gt; </code>
  </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>&lt;输入和amp；nbsp；type=“image”&amp; amp；nbsp；src=“commit-button. png”/&gt; </code>
  </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>&lt; p onclick="var s_ objectID='自定义链接id'；“&gt;&lt; span class=”title"&gt;当前Market Rates&lt;/span&gt;&lt; span class=“subtitle”&gt;1.45USD&lt;/span&gt;&lt;/p&gt; </code>
  </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>&lt; div onclick=“s. tl(true，'o'，'custom link id')”&gt;&lt; span class=“title”&gt;“当前市场速率&lt;/span”&gt;&lt; span class=“subtitle”&gt;1.45USD&lt;/span&gt;&lt;/div&gt; </code>
  </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>问：能否提供一些不被跟踪的链接示例？</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">原因：锚标记不具备有效的 href<code>&lt; a&amp; amp；nbsp；name=“innerAnchor”&gt;“章节和amp”；nbsp；header&lt;/a&gt; </code>
  </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;p onclick="showPanel('market rates')"&gt;     &lt;span class="title"&gt;Current Market Rates&lt;/span&gt;&lt;span  class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;input type="radio" onclick="changeState(this)" name="group1" value="A"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="B"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Reason: src property is missing a form input element 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

