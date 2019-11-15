---
description: 'null'
title: 模板
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 模板

## 模板 {#topic_40932F09E18A467983AFBB29908E1CB8}

您可以选择从以下项创建项目：:

* 空白项目（默认）。有关说明，请参 [阅创建Analysis Workspace项目](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)。
* 标准模板。这些模板由 Adobe 创建并且即装即用。
* 自定义模板。这些模板可由具有管理员权限的用户或非管理员（前提是他们获得了“另存为模板”权限）创建。(See [Manage product permissions](https://helpx.adobe.com/enterprise/using/manage-permissions-and-roles.html) in the Admin Console documentation for more information.

![](assets/start_modal.png)

* [创建自定义模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)
* [标准模板](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)

## 创建自定义模板 {#create-custom-template}

具有管理员权限的用户可以将他们创建的任何项目转换为自定义模板。以下是具体操作方法：

1. 打开该项目。
1. Go to **[!UICONTROL Project]** &gt; **[!UICONTROL Save As Template]**.

   ![](assets/save_project_template.png)

   项目将使用当前项目名称再加上“（模板）”一词进行保存。管理员可以通过编辑模板来更改此名称。

   >[!NOTE]
   >
   >默认情况下，项目模板对组织中的每个人都可见。 您可以通过应用标记来组织这些模板。(Go to **[!UICONTROL Project]** &gt; **[!UICONTROL Project Info &amp; Settings]** to edit tags and descriptions.)

### 可对自定义模板执行的操作

![](assets/custom_templates.png)

<table id="table_D7C7B0CA1EE64E108484C03426800EBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 操作 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>编辑模板 </p> </td> 
   <td colname="col2"> <p>允许管理员通过更改模板的数据源、修改组件、可视化、日期范围等内容来编辑模板。 </p> <p>要编辑自定义模板，请 </p> 
    <ul id="ul_2B3A371F83334E14806385753A360903"> 
     <li id="li_EE75E0281B764BA9B56FF1DB1B12D2CC">在 Analysis Workspace 中调出自定义模板列表，选择一个模板，然后单击<span class="uicontrol">编辑模板</span>，或 </li> 
     <li id="li_4934DAAA46204990A295E22A97F81EDA">在 Analytics 中，导航到<span class="ignoretag"><span class="uicontrol">组件</span> &gt; <span class="uicontrol">项目</span></span>，然后对<span class="uicontrol">模板</span>进行过滤。单击要编辑的模板的名称。 </li> 
    </ul> <p> </p> <p>注意：编辑模板之后，根据具体情况，您有两个选项可用：<span class="uicontrol">保存</span>、<span class="uicontrol">另存为</span>。以下是它们的不同之处： 
     <ul id="ul_87E2842C8AA442399585B1C6189F5E16"> 
      <li id="li_AB7B189729E14E40A0141ECE2A24C113"><b>保存</b>：更新所有用户的自定义模板。其他人从该自定义模板创建项目时会看到您做出的更改。 </li> 
      <li id="li_C85B0B9873A3404D8B443BBD30B37CEB"><b>另存为</b>：创建包含您所做更改的自定义模板副本。 </li> 
     </ul> </p> <p>（如果<span class="uicontrol">共享</span> &gt; <span class="uicontrol">共享项目</span>菜单项处于禁用状态，那么您可以据此判断您处于编辑模式当中。） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜索模板 </p> </td> 
   <td colname="col2"> <p>在“自定义模板”对话框中，单击<span class="uicontrol">搜索模板</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>排序模板 </p> </td> 
   <td colname="col2"> <p>您可以按字母顺序、相关性和创建日期对模板进行排序。 </p> <p>在“自定义模板”对话框中，单击<span class="uicontrol">排序:</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将标签应用到模板 </p> </td> 
   <td colname="col2"> <p>打开模板，然后转到<span class="ignoretag"><span class="uicontrol">项目</span> &gt; <span class="uicontrol">项目信息和设置</span></span>。单击<span class="uicontrol">添加标签</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>修改模板描述 </p> </td> 
   <td colname="col2"> <p>打开模板，然后转到<span class="ignoretag"><span class="uicontrol">项目</span> &gt; <span class="uicontrol">项目信息和设置</span></span>。双击该描述并进行编辑。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Standard templates {#concept_4FE900FEEC894E849CB6C6A0E0ADA524}

首次打开工作区时，模板位于左边栏中。 Analysis Workspace 模板涵盖常见用例。它们按所属的垂直领域分组，并填充了不同的维度、区段、量度和可视化，具体取决于您选择的报表包。

您可以按原样使用这些预填充模板，或修改它们以符合您的需要（例如，添加或替换量度或可视化），然后起一个新名称保存它们。

[YouTube上Analysis Workspace中的标准模板](https://www.youtube.com/watch?v=aRgYwPneVXg&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=6) (2:46)

以下是可用的模板以及每个模板有助于回答的问题：

### 广告

>[!IMPORTANT]
>
>只有在您的报表包启用了Advertising cloud时，广告模板才可用。

* **搜索引擎**:此模板可划分广告趋势、广告平台、关键字、帐户、营销活动等。

### 商务

* **马根托：营销和商务**:此模板按营销渠道归因划分您的电子商务转化，并按搜索关键字、登录页面、地理位置等提供分析。 有关视频概述，请参阅&gt;[!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw)

### 媒体

* **音频消耗**:哪些内容被消耗得最多，哪些内容吸引用户？
* **最近——频率——忠诚度**:我的忠实读者是谁？

### 移动设备

>[!IMPORTANT]
>
>移动模板仅在您的报告套件启用了移动时可用。

* **** 消息传递：专注于应用程序内和推送消息的性能。
* **** 位置：包括展示位置数据的地图。
* **** 关键指标：掌握应用程序的关键指标。
* **** 应用程序使用：应用程序有多少个应用程序用户、启动项和首次启动项，平均会话长度是多少？
* **** 收购：了解移动客户获取链接的效果。
* **** 性能：应用程序的性能如何，用户在哪里遇到问题？
* **** 保留：谁是我的忠实用户，他们做什么？
* **** 旅程：我的应用程序的主要使用模式是什么？

### 零售

* **** 营销活动效果：哪些营销活动最能带来收入？
* **** 产品：哪些产品表现最佳？

### Web

* **** 收购：我网站的主要流量驱动因素是什么？
* **** 内容消费：我网站上的热门位置是什么？
* **** 保留：哪些类型的用户可能是我网站的忠实用户？
* **** 技术：访问我的站点的人员使用哪些技术？

### 人员

> [!NOTE] “人员”模板及其关联的“人员”量度仅可作为 [Adobe Experience Cloud Device Co-op的一部分使用](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-people.html)。

基于“人员”量度，为删除了重复数据的独特访客量度版本。通过“人员”量度可测量客户使用多个设备与您的品牌进行交互的频率。该模板允许您

* 将美国/加拿大的数据与世界其它地区的数据进行分段。该设备协作当前仅在北美地区可用。
* 横向比较“人员”与“独特访客”量度。
* 请参阅“压缩率”，该计算量度用于计算“人员”量度小于独特访客的百分比。
* 比较客户使用的设备类型总数
* 查看每人使用的平均设备数量。
* 了解如何对“人员”量度进行分段堆叠。
* 探索如何在您的环境中使用 Experience Cloud ID 来增强“人员”量度的效率。

