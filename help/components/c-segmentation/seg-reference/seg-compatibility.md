---
description: 区段生成器中创建的所有区段并非都与 Data Warehouse 兼容。此表列出了受支持的功能。
seo-description: 区段生成器中创建的所有区段并非都与 Data Warehouse 兼容。此表列出了受支持的功能。
seo-title: Data Warehouse 区段兼容性
solution: Analytics
title: Data Warehouse 区段兼容性
topic: 区段
uuid: 370258c5-8614-4434-871c-41753ed77f5c
translation-type: tm+mt
source-git-commit: 26bba9528873c983852754056a5495c4004d25e6

---


# Data Warehouse 区段兼容性

Not all segments created in the Segment Builder are compatible with [!DNL Data Warehouse]. 此表列出了受支持的功能。

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis </th> 
   <th colname="col3" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>排除</b> </td> 
   <td colname="col2"> 在任何级别都受支持 </td> 
   <td colname="col3"> 只在顶级的特殊案例中受支持 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>顺序区段</b> </td> 
   <td colname="col2"> 受支持 </td> 
   <td colname="col3"> 不受支持 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>AND 和 OR 可自由组合不受限制</b> </td> 
   <td colname="col2"> 受支持 </td> 
   <td colname="col3"> 存在一些限制 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>嵌套的容器</b> </td> 
   <td colname="col2"> 受支持 </td> 
   <td colname="col3"> 一些限制（必须减小范围，例如访客可以包含点击，但点击不能包含访客） </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>维度</b> </td> 
   <td colname="col2">将维度拖动到区段生成器的“定义”<span class="uicontrol"></span>字段中，以便了解其产品兼容性的相关信息。例如，这些维度仅在Analysis Workspace、Reports&amp; Analytics和Ad Hoc Analysis中受支持： 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">登录服务器 </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">登录类别 </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">登录日期 </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">所有搜索页面排名 </li> 
    </ul> </td> 
   <td colname="col3"> 将维度拖动到区段生成器的“定义”<span class="uicontrol"></span>字段中，以便了解其产品兼容性的相关信息。例如，这些维度只在“Data Warehouse”中受到支持： 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">IP 地址 </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">页面 URL </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">访客 ID </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">Experience Cloud 访客 ID </li> 
    </ul> <p>The following dimensions <b>cannot </b>be used in Data Warehouse segments: </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">所有搜索页面排名 </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">上午/下午 </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">日期 </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">每周时间 </li> 
     <li id="li_4008565353084611BD782B98D50C0611">每年的某一天 </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">登录业务单位 </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">登录（以“登录”开头的所有维度，“登录页面”除外） </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">退出（以“退出”开头的所有维度，“退出链接”和“退出页面”除外） </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">层次结构（以层次结构开头的所有维度） </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">点击深度 </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">点击类型 </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">小时 </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">月份 </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">页面未找到 </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">付费搜索 </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">季度 </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">回访频度 </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">单页面访问量 </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">发生事件之前逗留的时间 </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">页面逗留时间 - 已存储 </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">每次访问逗留时间 - 分段统计 </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">跟踪选择退出的原因 </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">美国各州 </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">工作日/周末 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>区段堆栈</b> </td> 
   <td colname="col2"> 受支持 </td> 
   <td colname="col3"> 不受支持 </td> 
  </tr> 
 </tbody> 
</table>

