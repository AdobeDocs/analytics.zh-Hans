---
description: 有关实施的常见问题，以及指向更多信息的链接。
keywords: Analytics实施；常见问题解答；常见问题解答；evar到期；自定义事件可见性；时间戳；访客ID宽限期；访客id；Experience Cloud访客id；分析访客id；dm；心跳；cookies；跟踪服务器；性能；javascript；数据收集；s_ code版本；s_ code调试；跟踪链接类型；跟踪视频；跟踪移动应用程序；第一方cookie；SSL证书；认证期满；证书到期；插件；数据插入api；500错误；500；管理用户；管理组；用户；groups
seo-description: 有关实施的常见问题，以及指向更多信息的链接。
seo-title: 有关Analytics实施的常见问题解答
solution: Analytics
title: 有关Analytics实施的常见问题解答
topic: 开发人员和实施
uuid: 983d759a-c4 f2-4021-84c8-0486dbb951 b8
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 有关Analytics实施的常见问题解答

有关实施的常见问题，以及指向更多信息的链接。

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>问题</b> </td> 
   <td> <b>回答</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>我该如何管理 Analytics 用户和群组？ </p> </td> 
   <td colname="col3"> <p>For information about managing users and groups, refer to <a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html" format="html" scope="external"> User and Product Management </a> in the Adobe Experience Cloud help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>eVar 过期 - 为什么 eVar 在报表中被赋予“无”的属性？ </p> </td> 
   <td colname="col3"> <p> <span class="uicontrol">过期时间</span>会指定一个时段或事件，eVar 值将在此时段或事件之后过期（即，不再对成功事件计数）。如果在 eVar 过期之后发生成功事件，则由“无”值接收该事件的信用（不激活任何 eVar）。如果选择某个事件作为过期值，则变量仅在该事件发生时过期。如果未发生该事件，则变量从不过期。<a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external">更多信息...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>自定义事件可见性 - 为何自定义事件没有显示在报表菜单中？ </p> </td> 
   <td colname="col3"> <p>在可见性列中，您可以隐藏“菜单”、“量度选择器”、“计算量度生成器”和“区段生成器”中的标准（内置）量度、自定义事件和内置事件。这项设置不影响相关量度或事件的数据收集，而只会影响该量度或事件在用户界面中的可见性。<a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html" format="https" scope="external">更多信息...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>时间戳 - 更改时间戳设置前，需要考虑什么？ </p> </td> 
   <td colname="col3"> <p>使用可选时间戳功能，您可以整合未加盖时间戳的数据和加盖时间戳的数据，且不会造成数据丢失。生成自移动设备的具有时间戳的离线数据可以与网页上未加盖时间戳的实时数据相整合，或是使用客户端时间戳调用与来自任何平台的数据集成。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html" format="https" scope="external">更多信息...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>访客 ID - 访客 ID 宽限期的工作方式，如何启用它？ </p> </td> 
   <td colname="col3"> <p>如果有多个 JavaScript 文件要将数据发送至同一报表包，或者，如果您目前在自己的网站上使用 Flash 视频测量等其他技术，那么我们建议配置一个宽限期。<a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html" format="https" scope="external">更多信息...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>访客 ID - Experience Cloud 访客 ID 与 Analytics 访客 ID 有何区别？ </p> </td> 
   <td colname="col3"> <p>标识服务为您的所有站点访客分配唯一的永久标识符。通过这个 ID，可以在 Experience Cloud 的其他解决方案中共享访客及其数据。此外，这个 ID 可以取代特定于解决方案的 ID（例如 Analytics 访客 ID），或与之共同使用。<a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-overview.html" format="https" scope="external">更多信息...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>访客 ID - 如果阻止 Cookie，如何设置访客 ID？ </p> </td> 
   <td colname="col3"> <p>只要遇到标准 s_vi Cookie 不可用的情况，就会在网站的域中通过一个随机生成的唯一 ID 创建一个回退 Cookie。这个 Cookie 名为 s_fid，具有 2 年期限，可用作今后的回退识别方法。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html" format="https" scope="external">更多信息...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>动态标签管理 - 我的 DTM 规则为何无法触发？ </p> </td> 
   <td colname="col3"> <p>如果基于事件的规则没有触发，则可能是规则的选择器或条件存在问题。在您的网站上查找发生所需事件操作的元素，然后右键单击并选择检查元素。在打开的框中检查突出显示的脚本，并确保目标元素正确。<a href="https://marketing.adobe.com/resources/help/en_US/dtm/c_Troubleshooting.html" format="https" scope="external">更多信息...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>我该如何实施心率视频跟踪？ </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/" format="https" scope="external">本部分</a>包含有关下载心率视频 SDK 的说明以及适用于您的平台的开发人员指南。您在下载 SDK 时，请务必同时下载文档文件夹中的开发人员指南，因为其中包含有关心率视频的特定实施说明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>如何将 Cookie 添加到正确的子域？ </p> </td> 
   <td colname="col3"> <span class="varname"> cookieDomainPeriods </span> 变量通过确定页面URL的域中的句点数来确定Analytics cookie s_ cc和s_ sq的设置域。某些插件还会使用此变量来确定要设置插件 Cookie 的正确域。请参阅[配置变量](/help/implementation/js-implementation/c-variables/configuration-variables. md) </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>跟踪服务器 - 我该如何正确地向跟踪服务器填充数据？ </p> </td> 
   <td colname="col3"> <p>当您配置实施以向 Adobe Analytics 服务器发送数据时，必须将数据发送至正确的位置。如果不能发送至正确的位置，则会导致访客计数虚增或数据丢失。<a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external">更多信息...</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>性能 - 如果因为 Adobe 的网络连接、代理、防火墙或服务中断而导致加载外部 Adobe JavaScript 失败，会影响性能吗？ </p> </td> 
   <td colname="col3"> <p>不会。由于 JavaScript 文件并非是在 Adobe 服务器上托管，因此 Adobe 的故障将不会影响 JavaScript 执行。如果应用动态标签管理，JavaScript 文件是由 Akamai 托管，或者位于由客户决定的服务器上。 </p> <p>请参阅<i>动态标签管理会降低我的网站性能吗？</i>，此问题位于<a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html" format="https" scope="external">动态标签管理常见问题解答</a>区域。 </p> <p>此外，如果您不希望依赖 Akamai 的 CDN，也可以托管您自己的核心动态标签管理文件。请参阅<a href="https://marketing.adobe.com/resources/help/en_US/dtm/?f=deployment" format="https" scope="external">嵌入代码和托管选项</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>性能 - 加载外部 Adobe JavaScript 会导致性能降低吗？ </p> </td> 
   <td colname="col3"> <p> JavaScript 文件首次加载后会缓存在访客的浏览器中，通常情况下，针对每个会话至多下载一次。即使网站上的每个页面都使用该文件，也不会为每个页面下载它。在大多数网站上，用户在每个会话内平均都会查看多个页面，因此将使用多次的 JavaScript 转移到此文件中可减少总体下载数据量。 </p> <p> JavaScript for[！DNL AppMeasurement]压缩：如果您担心Adobe JavaScript客户端的页面重量(大小)，Adobe建议您考虑使用GZIP压缩文件。所有主要浏览器都支持 GZIP，而且与 JavaScript 压缩相比，其压缩和解压缩核心 <span class="filepath">s_code.js</span> JavaScript 文件的效率更高。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>性能 - 将来自浏览器的数据发送至 Adobe 服务会降低性能吗？ </p> </td> 
   <td colname="col3"> <p> Adobe JavaScript 文件在 HTML 页面内创建一个图像对象，浏览器随后从 Adobe 服务器请求该图形对象。如果 Adobe 服务器变得缓慢或无反应，则处理该请求的线程将被延迟，直至图像返回或发生超时。因为浏览器会通过多线程处理图像，而 Adobe 故障仅占用一个线程，其他线程继续工作，因此对页面加载时间会造成一定的影响，但这个影响极小。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>性能 - 来自 Adobe 的 JavaScript 事件会影响系统行为或功能吗？ </p> </td> 
   <td colname="col3"> <p>不会。请参阅前面有关性能方面的回答。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 我该如何根据我自己定义的条件来更改收集的数据？ </td> 
   <td colname="col3"> 使用处理规则可简化数据收集流程，并在数据被发送到报表时对内容进行管理。<a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 哪一个是 s_code 文件的最新版本？ </td> 
   <td> 此部分包含[！DNL AppMeasurement]库跨网络和移动平台。可以通过下面的方法下载每个库的最新版本：“报告与分析”&gt;“管理工具”&gt;“代码管理器”。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/?f=c_release_notes_javascript" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 我该如何调试 s_code 文件？ </td> 
   <td> Adobe Debugger（以前称为 DigitalPulse Debugger）是由 Adobe 提供的一款免费工具，使用它可以查看从您网站上的任意给定页面收集的数据。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=debugger" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 我该如何跟踪不同的链接类型？ </td> 
   <td> 您可以根据 JavaScript AppMeasurement 文件中设置的参数自动跟踪文件下载和退出链接。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=function_tl" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 我该如何跟踪视频？ </td> 
   <td> 可以使用 JavaScript 来跟踪种类繁多的播放器。若要使用 JavaScript 来跟踪，请将代码添加至包含播放器的网页，并使用事件处理程序跟踪播放器。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 我该如何跟踪移动设备应用程序？ </td> 
   <td> 带有唯一跟踪码的采集链接可以在 Adobe Mobile 服务中生成。当用户通过点击生成的链接下载并运行苹果 App Store 应用商店的应用程序时，SDK 会自动收集采集数据并向 Adobe Mobile 服务发送。<a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=acquisition" format="http" scope="external"> iOS</a> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=acquisition" format="http" scope="external">Android </a> </td> 
  </tr> 
  <tr> 
   <td> 我该如何实施视频跟踪？ </td> 
   <td> 您可以通过创建附加在视频播放器事件处理程序中的函数来跟踪媒体播放器。这样您就可以在适当的时候调用 Media.open、Media.play、Media.stop 和 Media.close 等命令。<a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js_events" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 我该如何设置第一方 Cookie？ </td> 
   <td> Analytics 使用 Cookie 来提供有关变量和组件的信息，这类信息无法在图像请求和浏览器会话之间永久保存。这些无害的 Cookie 源自 Adobe 托管的域，称为第三方 Cookie。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_cert" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 我该如何获取 SSL 证书？ </td> 
   <td> 确定网站是否使用的是 https:// 协议。如果使用该协议，则需要请求 CSR 并购买 SSL 证书。注意：如果您没有安全页面或内容，则无需 SSL 证书。如果只在站点上使用https://协议，则可能跳过整个步骤。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_cert" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 我该在何处查找有关证书过期通知的信息？ </td> 
   <td> SSL 证书每年都会到期，也就是说，Adobe 要求在每次证书到期时提交更新的证书请求。证书到期时，FPC 专家将发出充分的警告，然而，建议主动监控证书是否过期并向 Adobe 提供更新的证书。<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_renewals" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 什么是插件？ </td> 
   <td> AppMeasurement for JavaScript 插件是执行多项高级功能的程序或功能。这些插件扩展了 JavaScript 文件的功能，提供了多项基本实施所没有的功能。作为高级解决方案的一部分，Adobe 提供了许多其他插件。如果您希望使用 JavaScript 捕获数据，但又不确定从何处入手，请联系您的客户经理。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=impl_plugins" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 关于数据插入 API 的信息？ </td> 
   <td> Adobe 已创建了多种方法可将数据发送到 Analytics。<a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=usecase_sending_data_to_sc" format="http" scope="external"> 了解更多 </a> </td> 
  </tr> 
  <tr> 
   <td> 什么是“500 错误”？ </td> 
   <td> 与引起“500 查询错误”状态的内部服务器错误相关的信息。<a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=pageType" format="http" scope="external">请参阅pageType变量 </a> </td> 
  </tr> 
 </tbody> 
</table>

