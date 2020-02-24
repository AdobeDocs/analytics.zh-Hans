---
description: 'null'
title: Adobe Campaign 报告
uuid: 0919ae9f-84eb-43a5-8282-6cd6dec63dc1
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Campaign 报告

有关如何配置此集成的更多信息，请参阅 [Adobe Campaign 文档](https://helpx.adobe.com/cn/campaign/standard/integrating/using/about-campaign-analytics-integration.html)。

Adobe Analytics 与 Adobe Campaign 之间的此集成

* 允许您将 KPI（关键绩效指标）数据从 Adobe Campaign Standard 共享到 Adobe Analytics。
* 通过 Adobe Analytics 参数丰富了跟踪公式。
* 在 **[!UICONTROL Analytics]** > **[!UICONTROL 报表]** > **[!UICONTROL Adobe Campaign]** 下添加了新报表。
* 添加了 5 个新的 Adobe Campaign 分类。
* 添加了 10 个新的 Adobe Campaign 量度。
* 添加了 6 个新的 Adobe Campaign 维度。
* 每隔 15 分钟将数据同步到 Analytics。

## 步骤 1. 启用 Adobe Campaign 报告功能 {#section_C685EF10505045708A6536BB13F6CD58}

要在 Analytics 中查看 Campaign 数据，您首先需要启用 Campaign 报表功能。

1. 导航至 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL <select report suite>]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign 报告]**。
1. 单击&#x200B;**[!UICONTROL 启用 Campaign 报表]**。

   ![](assets/enable-campaign.png)

## 步骤 2. 查看 Adobe Campaign 报表 {#section_9C18A29F3CC54BD4AC5EA96417F17B33}

Adobe Campaign Standard 与 Adobe Analytics 之间的集成在 **[!UICONTROL Analytics]** > **[!UICONTROL 报表]**&#x200B;下添加了以下报表

<table id="table_3627F40DC90646A7B5E217A88B6FD630"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 报表 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Campaign 执行的提交 ID </p> </td> 
   <td colname="col2"> <p>显示从 Adobe Campaign 导入的有关发送自 Adobe Campaign 的电子邮件的数据。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 步骤 3. 使用 Adobe Campaign 分类 {#section_74A28AF3F4CA4091943789DE4D8B2B63}

**[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 报表包]** > **[!UICONTROL <select report suite>]** > **[!UICONTROL 编辑设置]** > **[!UICONTROL Adobe Campaign]** > **[!UICONTROL Adobe Campaign 分类]**

在为您的报表包启用了 Adobe Campaign 后，可以使用以下分类：

* 提交 ID（您在 Campaign 中看到的内部提交名称）
* 提交标签（Campaign 中的提交 - 单个提交/循环提交/交易提交）
* 促销活动 ID（您在 Campaign 中看到的促销活动名称）
* 促销活动标签（Adobe Campaign 中的促销活动）
* 执行的提交标签（执行的各个提交的列表）

## Adobe Analytics 中可用的 Adobe Campaign 维度和量度 {#section_F33385C9660644AF84172EC39601469B}

在 Adobe Analytics 报表包的 Campaign 中可以使用以下&#x200B;**量度**：

* Adobe Campaign 已发送
* Adobe Campaign 已打开
* Adobe Campaign 已点击
* Adobe Campaign 已处理
* Adobe Campaign 已提交
* Adobe Campaign 唯一打开
* Adobe Campaign 唯一点击
* Adobe Campaign 已取消订阅
* Adobe Campaign 总跳出次数
* Adobe Campaign 执行的提交 ID 实例

在 Adobe Analytics 报表包的 Campaign 中可以使用以下&#x200B;**维度**：

| 维度名称 | 定义 |
|--- |--- |
| 促销活动 ID | 在活动持续期间为其发送了 KPI 的所有促销活动的 ID |
| 促销活动标签 | 促销活动 ID 的标签 |
| 提交 ID | 在活动持续期间为其发送了 KPI 的所有提交的 ID。还包含循环提交和交易提交的主提交的 ID。示例：循环提交 DM1 是计划的提交，DM2、DM3、DM4 和 DM5 是该循环提交的子提交。提交 ID 将显示从 DM1 到 DM5 的所有提交的结果。 |
| 提交标签 | 提交 ID 的标签 |
| 执行的提交 ID | 仅执行的提交的 ID。不包含循环/交易主提交的 ID。示例：循环提交 DM1 是计划的提交，DM2、DM3、DM4 和 DM5 是该循环提交的子提交。执行的提交 ID 显示从 DM2 到 DM5 的所有提交（即已实际执行的提交）的结果。 |
| 执行的提交标签 | 执行的提交 ID 的标签 |
