---
description: 有关 Adobe Analytics 部署的自动配置的常见问题解答。自动配置方法可为您管理 AppMeasurement 代码。
keywords: Dynamic Tag Management;插件;暂存;对当前设置的影响;修订历史记录;潜在风险;报表包 ID;货币代码;跟踪服务器;ssl 跟踪服务器;自定义代码;库管理
seo-description: 有关 Adobe Analytics 部署的自动配置的常见问题解答。自动配置方法可为您管理 AppMeasurement 代码。
seo-title: 关于 Adobe Analytics 工具的常见问题解答
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 关于 Adobe Analytics 工具的常见问题解答
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 关于 Adobe Analytics 工具的常见问题解答

有关 Adobe Analytics 部署的自动配置的常见问题解答。自动配置方法可为您管理 [!DNL AppMeasurement] 代码。

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 通过 DTM 实施 Adobe Analytics 时，我应将插件放在何处？ </p> </td> 
   <td colname="col2"> <p> 如果使用 DTM 手动托管 <code> s_code</code>，则可以将插件添加到与托管的 <code> s_code</code> 相同的编辑器中，就像在常规的 Adobe Analytics 实施中一样。 </p> <p>但是，也可以将插件放入工具设置的<span class="term">自定义页面代码</span>部分的编辑器中。两种实施方法应具有同等效力。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果我在新版工具中更改配置，我能否先在暂存环境中进行测试，然后再发布到生产环境？ </p> </td> 
   <td colname="col2"> <p>能。 </p> <p>在部署到生产环境之前，所有更改均可像往常一样在暂存环境中进行测试。如果您因在暂存环境中发现问题而选择不发布，则生产代码将继续像在发行新集成之前那样运行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果我从手动配置（现有工具的默认设置）切换到自动配置，我当前的设置是否会受到影响？ </p> </td> 
   <td colname="col2"> <p>不会。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果我从手动库管理切换到由 Adobe 管理，我当前的设置或代码是否会受到影响？ </p> </td> 
   <td colname="col2"> <p>您指定的任何用户代码将由 <span class="keyword">AppMeasurement</span> 基本库覆盖。工具配置结束时，您必须将此代码移到新的<span class="wintitle">自定义页面代码</span>部分，以便继续执行代码。通过此方法，可以将 <span class="keyword">AppMeasurement</span> 库与用户的自定义代码分开管理（和升级）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>发行新集成时，<span class="keyword">Adobe Analytics</span> 工具的修订历史记录会保留吗？ </p> </td> 
   <td colname="col2"> <p>能。 </p> </td> 
  </tr> 
 </tbody> 
</table>

请参阅[添加 Adobe Analytics 工具](../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8)获取配置信息。

## 潜在危险 {#section_201BF9E0EB7D4BC2B72A617543C2030B}

如果当前使用的是 [!DNL Adobe Analytics]，则在极少数情况下，集成可能会导致数据收集出现问题。只有在发布之后将库发布到生产时，才会引发这些问题。（在进行发布之前，生产代码保持不变。）

要避免这些问题，请确保：

* 在工具中正确输入报表包 ID。
* 工具中的报表包 ID 与 [!DNL AppMeasurement] 代码中的 ID 匹配。
* 使用支持的值正确设置货币代码、字符集、跟踪服务器和 SSL 跟踪服务器配置字段。
* 在 [!DNL Library Management] 中定义自定义代码。

