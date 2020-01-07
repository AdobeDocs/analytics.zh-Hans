---
description: 部署 Analytics 时，动态标签管理中用于链接跟踪的字段描述。
keywords: Dynamic Tag Management;link tracking;enable clickmap;track download links;download extensions;track outbound links;keep url parameters
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: 链接跟踪
uuid: 982b744b-5696-4c31-b1d1-410486b0eedd
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 链接跟踪

部署 Analytics 时，动态标签管理中用于链接跟踪的字段描述。

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL   ![](assets/settings_gear.png)

编辑工具]** &gt; **[!UICONTROL 链接跟踪]**

<table id="table_F23FB0B284E74B66A107B1D69D22A51C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 启用 ClickMap </td> 
   <td colname="col2"> <p>确定是否收集访客点击图数据。 </p> <p>有关更多信息，请参阅<a href="/help/implement/js-implementation/c-variables/configuration-variables.md"  >s.trackInlineStats</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 跟踪下载链接 </td> 
   <td colname="col2"> <p>跟踪网站上可下载文件的链接。 </p> <p>请参阅<a href="/help/implement/js-implementation/c-variables/configuration-variables.md">配置变量</a>。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 下载扩展名 </td> 
   <td colname="col2"> <p>如果您网站上包含的链接可转到具有任何所列扩展名的文件，则这些链接的 URL 将在报表中显示。 </p>请参阅<a href="/help/implement/js-implementation/c-variables/configuration-variables.md">配置变量</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 跟踪出站链接 </td> 
   <td colname="col2"> <p>确定点击的任何链接是否为退出链接。 </p> <p>请参阅<a href="/help/implement/js-implementation/c-variables/configuration-variables.md">配置变量</a>。 </p> <p><b>单页面应用程序注意事项：</b>由于某些 SPA 网站的编码方式，指向 SPA 网站上页面的内部链接的外观可能与出站链接类似。 </p> <p>您可以使用以下方法之一跟踪来自 SPA 网站的出站链接： </p> 
    <ul id="ul_A4179633ED0644C3BA5F548A58CA4EC9"> 
     <li id="li_1959FBF14E42469FA8724B37EB58BC54"> <p>如果不希望跟踪来自 SPA 的任何出站链接，则在“<span class="wintitle">从不跟踪</span>”部分添加一个条目。 </p> <p>例如 <span class="filepath">https://testsite.com/spa/#</span> </p> <p>指向此主机的所有 # 链接都会被忽略。并跟踪指向其他主机的所有出站链接，如 <span class="filepath"></span>https://www.google.com。 </p> </li> 
     <li id="li_37DD4D37887243FB928C9C04ACE9D39E"> <p>如果希望跟踪 SPA 上的某些链接，则使用“<span class="wintitle">总是跟踪</span>”部分。 </p> <p>例如，如果希望跟踪 <span class="filepath">spa/#/about</span> 页面，则可以将“about”放置在“<span class="wintitle">总是跟踪</span>”部分。 </p> <p>“about”页面是唯一跟踪的出站链接。不会跟踪页面上的任何其他链接（例如 <span class="filepath"></span>https://www.google.com）。 </p> </li> 
    </ul> <p>请注意，这两个选项相互排斥。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 保留 URL 参数 </td> 
   <td colname="col2"> <p>保留查询字符串。 </p> <p>请参阅<a href="/help/implement/js-implementation/c-variables/configuration-variables.md">配置变量</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
