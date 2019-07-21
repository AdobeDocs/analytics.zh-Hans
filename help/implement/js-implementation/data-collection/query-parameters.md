---
description: 下表列出的查询参数包含每个要发送到数据收集的分析变量的值。
keywords: Analytics 实施
seo-description: 下表列出的查询参数包含每个要发送到数据收集的分析变量的值。
seo-title: 数据收集查询参数
solution: Analytics
title: 数据收集查询参数
topic: 开发人员和实施
uuid: 4d5af486-df27-42fe-bb9 c-28938ddf2 b2
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# 数据收集查询参数

下表列出的查询参数包含每个要发送到数据收集的分析变量的值。

可使用该信息的情况包括使用[包分析程序](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258)、手动构造图像请求或使用 [动态变量](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262)时。

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> 参数 </th> 
   <th class="entry"> Analytics 变量 </th> 
   <th class="entry"> 已填充的报表 </th> 
   <th class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> 无 </td> 
   <td colname="col3"> 无 </td> 
   <td colname="col4"> Audience Manager 位置提示（用于 Experience Cloud 共享配置文件集成） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> 无 </td> 
   <td colname="col3"> 无 </td> 
   <td colname="col4"> Audience Manager Blob（用于 Experience Cloud 共享配置文件集成） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> 无 </td> 
   <td colname="col3"> 无 </td> 
   <td colname="col4"> Analytics 访客 ID </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 指示图像请求的开始 </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 指示图像请求的结束，这表明该请求未被截断 </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | 浏览器高度 </td> 
   <td> 浏览器窗口高度（像素） </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | 浏览器宽度 </td> 
   <td> 浏览器窗口宽度（像素） </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | 显示器颜色深度 </td> 
   <td> 颜色质量（位） </td> 
  </tr> 
  <tr> 
   <td> <code> c[ <span class="varname"> key] </code></span> </td> 
   <td> <p>s.contextData </p> </td> 
   <td> <p>无 </p> </td> 
   <td> <p>使用以下任一格式指定键值对： </p> <p> <code> &lt;my.a&gt;red&lt;/my.a&gt; </code> </p> <p>或: </p> <p> <code> &lt;my&gt;&lt;a&gt;red&lt;/a&gt;&lt;/my&gt; </code> </p> <p>每个示例都会将上下文数据值设为 <code>my.a = red</code>。您还可以指定多个键值对。 </p> <p>In the query string, this context data variable would appear as <code> c.&amp;my.a=red </code> </p> </td> 
  </tr> 
  <tr> 
   <td> c1 - c75 </td> 
   <td> s.prop1 - s.prop75 </td> 
   <td> 所有自定义流量报表 </td> 
   <td> 自定义流量报表中使用的流量变量 </td> 
  </tr> 
  <tr> 
   <td> cc </td> 
   <td> s.currencyCode </td> 
   <td> 无 </td> 
   <td> 网站上使用的货币类型 </td> 
  </tr> 
  <tr> 
   <td> cdp </td> 
   <td> s.cookieDomainPeriods </td> 
   <td> 无 </td> 
   <td> 指示用于 Cookie 跟踪的域中的句点数量；手动设置 </td> 
  </tr> 
  <tr> 
   <td> ce </td> 
   <td> s.charSet </td> 
   <td> 无 </td> 
   <td> 图像请求的字符编码 </td> 
  </tr> 
  <tr> 
   <td> cl </td> 
   <td> s.cookieLifetime（s_vi Cookie 生命周期，以秒为单位） </td> 
   <td> 无 </td> 
   <td> 访客 Cookie 的生命周期。 </td> 
  </tr> 
  <tr> 
   <td> ch </td> 
   <td> s.channel </td> 
   <td> 网站内容 | 网站区域 </td> 
   <td> 流量报表中使用的网站区域变量 </td> 
  </tr> 
  <tr> 
   <td> cp </td> 
   <td> 点击类型 </td> 
   <td> 点击类型 </td> 
   <td> 指示行为是直接在前台进行交互的结果，还是设备在没有在后台进行直接交互的情况下发送的信息。 </td> 
  </tr> 
  <tr> 
   <td> ct </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | 连接类型 </td> 
   <td> 连接类型（调制解调器、LAN 等；只能在 IE 浏览器中填充） </td> 
  </tr> 
  <tr> 
   <td> <code> D </code> </td> 
   <td> dynamicVariablePrefix </td> 
   <td> 无 </td> 
   <td> <p>请参阅 <a href="../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262" format="dita" scope="local"> 动态变量 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td> events 或 ev </td> 
   <td> s.events </td> 
   <td> 网站流量 | 购买事件、购物车事件、自定义事件 </td> 
   <td> 页面上发生的商务事件和自定义事件；用于转化报表 </td> 
  </tr> 
  <tr> 
   <td> g </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 页面的当前 URL，最多 255 字节。 </td> 
  </tr> 
  <tr> 
   <td> -g </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 大于 255 字节的 URL 会被拆分，前面的 255 个字节显示在 g 参数中，剩下的字节稍后显示在 -g= 查询参数的查询字符串中。 </td> 
  </tr> 
  <tr> 
   <td> h1 - h5 </td> 
   <td> s.hier1 - s.hier5 </td> 
   <td> 网站内容 | 层次结构报表 </td> 
   <td> 层次结构变量；用于流量报表 </td> 
  </tr> 
  <tr> 
   <td> hp </td> 
   <td> 无 </td> 
   <td> 访客资料 | 访客主页 </td> 
   <td> 指示当前页面是否为浏览器的主页（Y 或 N，只能在 IE 浏览器中填充） </td> 
  </tr> 
  <tr> 
   <td> j </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | Javascript 版本 </td> 
   <td> 显示当前安装的 Javascript 版本（通常为 1.x） </td> 
  </tr> 
  <tr> 
   <td> k </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | Cookie </td> 
   <td> 浏览器是否支持 Cookie（Y、N 或 U） </td> 
  </tr> 
  <tr> 
   <td> l1-l3 </td> 
   <td> s.list1-s.list3 </td> 
   <td> 自定义转换 </td> 
   <td> 一个分隔的值列表，这些值会传入一个变量，然后报告为单独的行项目以便制作报表。 </td> 
  </tr> 
  <tr> 
   <td> mid </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> Experience Cloud 访客 ID </td> 
  </tr> 
  <tr> 
   <td> ndh </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 指示图像请求是否来源于 JS 文件（1 或 0） </td> 
  </tr> 
  <tr> 
   <td> ns </td> 
   <td> s.visitorNameSpace </td> 
   <td> 无 </td> 
   <td> 指定设置 Cookie 所在的域 </td> 
  </tr> 
  <tr> 
   <td> oid </td> 
   <td> s.objectID </td> 
   <td> 网站内容 | 链接 | ClickMap </td> 
   <td> 最后一页的对象标识符；用于 ClickMap </td> 
  </tr> 
  <tr> 
   <td> ot </td> 
   <td> 无 </td> 
   <td> 网站内容 | 链接 | ClickMap </td> 
   <td> 最后一页的对象标记名称；用于 ClickMap </td> 
  </tr> 
  <tr> 
   <td> p </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | Netscape 插件 </td> 
   <td> 由分号分隔的浏览器插件名称 </td> 
  </tr> 
  <tr> 
   <td> pageName（或 gn） </td> 
   <td> s.pageName </td> 
   <td> 网站内容 | 页面 </td> 
   <td> 报表中页面的指定名称 </td> 
  </tr> 
  <tr> 
   <td> pageType（或 gt） </td> 
   <td> s.pageType </td> 
   <td> 网站内容 | 页面未找到 </td> 
   <td> 指示这是否为一个 404 页面（“错误页”或空白页） </td> 
  </tr> 
  <tr> 
   <td> pccr </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 只在有新访客时发生；防止无限次重定向（始终为 true） </td> 
  </tr> 
  <tr> 
   <td> pe </td> 
   <td> s.linkType </td> 
   <td> 网站内容 | 链接 | 退出链接、文件下载、自定义链接 </td> 
   <td> 确定触发的自定义链接点击的类型 </td> 
  </tr> 
  <tr> 
   <td> pev1 </td> 
   <td> 无 </td> 
   <td> 网站内容 | 链接 | 退出链接、文件下载、自定义链接 </td> 
   <td> 发生自定义链接点击的 URL </td> 
  </tr> 
  <tr> 
   <td> pev2 </td> 
   <td> 无 </td> 
   <td> 网站内容 | 链接 | 退出链接、文件下载、自定义链接 </td> 
   <td> 自定义链接易记名称 </td> 
  </tr> 
  <tr> 
   <td> pev3 </td> 
   <td> 无 </td> 
   <td> 所有视频报表 </td> 
   <td> 用于跟踪传统视频报表中的里程碑；由 v15 替代 </td> 
  </tr> 
  <tr> 
   <td> pf </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> 仅限 Adobe 使用。请勿更改。 </td> 
  </tr> 
  <tr> 
   <td> pid </td> 
   <td> 无 </td> 
   <td> 网站内容 | 链接 | ClickMap </td> 
   <td> 最后一页的页面标识符；用于 ClickMap </td> 
  </tr> 
  <tr> 
   <td> pidt </td> 
   <td> 无 </td> 
   <td> 网站内容 | 链接 | ClickMap </td> 
   <td> 最后一页的页面标识符类型；用于 ClickMap </td> 
  </tr> 
  <tr> 
   <td> products（或 pl） </td> 
   <td> s.products </td> 
   <td> 产品 | 产品 </td> 
   <td> 转化报表中使用的产品变量 </td> 
  </tr> 
  <tr> 
   <td> purchaseID（或 pi） </td> 
   <td> s.purchaseID </td> 
   <td> 无 </td> 
   <td> 用于删除重复的购买，以防止收入虚增 </td> 
  </tr> 
  <tr> 
   <td> r </td> 
   <td> s.referrer </td> 
   <td> 所有流量源报表 </td> 
   <td> 反向链接 URL </td> 
  </tr> 
  <tr> 
   <td> s </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | 显示器分辨率 </td> 
   <td> 屏幕分辨率（宽 x 高） </td> 
  </tr> 
  <tr> 
   <td> server（或 sv） </td> 
   <td> s.server </td> 
   <td> 网站内容 | 服务器 </td> 
   <td> 页面服务器；用于流量报表 </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> s.state </td> 
   <td> 访客资料 | 访客所在州 </td> 
   <td> 将状态指定为由变量定义。 </td> 
  </tr> 
  <tr> 
   <td> t </td> 
   <td> （每次发生没有自定义时间戳的点击时自动发送） </td> 
   <td> 无 </td> 
   <td> <p><code>t</code> 参数的格式如下： </p> 
    <code>dd/mm/yyyy&amp; amp；nbsp；hh：mm：ss&amp; amp；nbsp；D&amp; amp；nbsp；OFFINDER </code>
  <p>其中 D 是范围在 <code>0-6</code> 之间的数字，指定星期几，而 <code>OFFSET</code> 则表示： </p> 
    <code>偏移和amp；nbsp；从&amp; amp；nbsp；GMT&amp; amp；nbsp；in&amp; amp；nbsp；小时和amp；nbsp；*&amp; amp；nbsp；60和amp；nbsp；*&amp; amp；nbsp；&amp; amp；nbsp；1 </code>
  <p> 例如： </p> 
    <code>23/09/2016&amp; amp；nbsp；14：00：00&amp; amp；nbsp；&amp; amp；nbsp；420420 </code>
  </td> 
  </tr> 
  <tr> 
   <td> <code> ts </code> </td> 
   <td> <p>timestamp </p> </td> 
   <td> 无 </td> 
   <td> <p>点击时计算并发送的自定义时间戳。通常用于离线跟踪。 </p> </td> 
  </tr> 
  <tr> 
   <td> v </td> 
   <td> 无 </td> 
   <td> 访客资料 | 技术 | Java </td> 
   <td> 启用 Java（Y 或 N） </td> 
  </tr> 
  <tr> 
   <td> v0 </td> 
   <td> s.campaign </td> 
   <td> 促销活动 | 跟踪代码 </td> 
   <td> 转化报表中使用的促销活动变量 </td> 
  </tr> 
  <tr> 
   <td> v1-v75 </td> 
   <td> s.eVar1-s.eVar75 </td> 
   <td> 所有自定义转化报表 </td> 
   <td> 自定义转化报表中使用的转化变量 </td> 
  </tr> 
  <tr> 
   <td> vid </td> 
   <td> <p>s.visitorID </p> </td> 
   <td> 无 </td> 
   <td> 访客唯一 ID，在 访客 ID 变量. </td> 
  </tr> 
  <tr> 
   <td> vmk </td> 
   <td> s.vmk </td> 
   <td> 无 </td> 
   <td> 访客迁移键；用于从第三方迁移到第一方 Cookie。已弃用。 </td> 
  </tr> 
  <tr> 
   <td> vvp </td> 
   <td> s.variableProvider </td> 
   <td> 无 </td> 
   <td> 用于 Genesis 集成 </td> 
  </tr> 
  <tr> 
   <td> xact </td> 
   <td> s.transactionID </td> 
   <td> 无 </td> 
   <td> 交易 ID 用于将在线数据链接到脱机数据 </td> 
  </tr> 
  <tr> 
   <td> zip </td> 
   <td> s.zip </td> 
   <td> 访客资料 | 访客邮政编码 </td> 
   <td> 确定由变量定义的邮政编码 </td> 
  </tr> 
  <tr> 
   <td> 图像请求 URL 中的 /5/（移动协议）或 /1/（非移动协议）。 </td> 
   <td> 无 </td> 
   <td> 无 </td> 
   <td> <p> 控制使用 Cookie 和其他方法识别访客的顺序。 </p> </td> 
  </tr> 
 </tbody> 
</table>

