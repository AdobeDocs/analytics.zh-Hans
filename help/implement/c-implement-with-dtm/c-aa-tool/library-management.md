---
description: 动态标签管理“库管理”设置中各个字段和选项的描述。
keywords: 库管理；页面代码；加载库；由adobe管理；自定义；代码托管；s_ code托管
seo-description: 动态标签管理“库管理”设置中各个字段和选项的描述。
seo-title: 库管理
solution: Marketing Cloud，动态标签管理
title: 库管理
uuid: 4cfa47f9-ae98-4b-a58 d-a3 a6 e45 f8 d5 b
translation-type: tm+mt
source-git-commit: 3489f00bd7dddefda0420fc361056416f6f10d3f

---


# 库管理

动态标签管理“库管理”设置中各个字段和选项的描述。

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL 编辑工具]** &gt; **[!UICONTROL 库管理]**

>[!NOTE]
>
>如果在单个Web资产中使用了多个Adobe Analytics工具，则每个工具必须具有唯一的跟踪器变量名称。如果一个 Web 属性中的多个 Adobe Analytics 工具之间存在重复的对象变量名称，则将会引发冲突。

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>页面代码已存在 </p> </td> 
   <td colname="col2"> <p> 如果您的网站上已存在 <span class="keyword">Adobe Analytics</span> 页面代码，请阻止动态标签管理安装此代码。 </p> <p>这项功能允许您使用动态标签管理向现有的实施执行添加操作，而不是从头开始。选中此框时，请确保正确设置了您的跟踪器变量名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>库加载位置 &lt;<span class="term"> 页面顶部</span> 或 <span class="term"> 底部页面</span>&gt; </p> </td> 
   <td colname="col2"> <p>指定页面代码加载的位置和时间。无论选择任何内容，使用 Analytics 工具的任何规则都将需要具有相同的设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>由 Adobe 管理（推荐） </p> </td> 
   <td colname="col2"> <p>启用动态标签管理来管理您的库。 </p> <p>如果选择此选项，则以下选项将变为可用： </p> <p> <b>库版本：</b>从“<span class="wintitle">库版本</span>”菜单中选择最新版本。动态标签管理会在新版本可用时通知您。您可以根据需要还原至以前的版本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 自定义 </p> </td> 
   <td colname="col2"> <p>您可以配置库代码。 </p> <p>如果选择此选项，则以下选项将变为可用： </p> <p> <b>使用下面的自定义代码设置报表包：</b>选中此框后，动态标签管理会在您的自定义代码中查找名为 <span class="varname"> s_account</span>. 此变量应当包含要向其发送数据的报表包列表（以逗号分隔）。 </p> <p> <b>托管代码：</b>选择用来托管 <span class="filepath">s_code</span> 的选项： </p> 
    <ul id="ul_FC395283365A4BBAA8A5FE5871D16EC6"> 
     <li id="li_36D733C533CE40F1868309130551D4DE"> <b>在 DTM 中</b>：您可以在动态标签管理中托管 <span class="filepath">s_code</span>。单击<span class="uicontrol">编辑代码</span>，直接将文件剪切并粘贴到编辑器中。 </li> 
     <li id="li_A64734C66D254079A5E16DC8DBEDA3F6"> <b>URL</b>：如果您拥有一个完好的 <span class="filepath">s_code</span> 文件并且愿意更新它，则可以在此处提供指向该文件的 URL。动态标签管理随后会使用此 <span class="filepath">s_code</span> 文件来实施 <span class="keyword">Adobe Analytics</span>。 </li> 
    </ul> <p> <b>打开编辑器： </b>允许 <a href="../../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658" format="dita" scope="local"> 插入核心AppMeasurement代码</a>。This code is populated automatically when using the automatic configuration method described in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8" format="dita" scope="local"> Adobe Analytics Settings</a>. </p> <p> <b>跟踪器变量名称： </b>如果要并行运行两个 <span class="keyword"> Adobe Analytics</span> 实例(一个在动态标签管理中和一个本机)，则可以重命名主 <span class="term"> 对象</span> 。重命名对象名称可避免发生冲突。 </p> </td> 
  </tr> 
 </tbody> 
</table>

