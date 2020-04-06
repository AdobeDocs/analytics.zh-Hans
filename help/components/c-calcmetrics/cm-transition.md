---
description: 这些对计算量度在Analytics中工作方式的更改可能会影响您。
title: 常见问题解答
uuid: 9b7f1cd1-b969-4b15-8af1-969d816b65b8
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 常见问题解答

对计算量度在 [!DNL Analytics] 中的工作方式所做的这些更改可能会影响到您。

[如何访问计算量度生成器？](/help/components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[如何访问计算量度管理器？](/help/components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[为什么我会看到这么多具有相同名称的计算量度？](/help/components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[我的全局计算量度发生了什么情况？](/help/components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[在登录公司之间共享的全局计算量度发生了什么情况？](/help/components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[具有数值或数值 2 分类的计算量度发生了什么情况？](/help/components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[存留期量度发生了什么情况？](/help/components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[有关基于每日/每周/每月/每季/每年独特访客量度的计算量度，我需要了解什么？](/help/components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[通过旧报表包 API 方法创建或管理的计算量度怎么样了？](/help/components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[“当前数据”支持所有类型的计算量度吗？](/help/components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[随迁移的计算量度出现的“未提供名称”是什么意思？](/help/components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[如果用户被删除，那么该用户的计算量度会发生什么情况？](/help/components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[我为什么看到“未知”计算量度对于其他报表包“无效”，即使可以创建这些量度并将其应用于这些报表包？](/help/components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[为什么没有保存我对旧计算量度所做的更改？](/help/components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[为什么我的计算量度没有显示在营销渠道报表中？](/help/components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[为什么某些计算量度显示的公式没有我添加的圆括号？](/help/components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[（仅限 Ad Hoc Analysis）具有嵌套或内联区段定义的计算量度仍然受支持吗？](/help/components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[（仅限 Report Builder）为什么计算量度从我的请求中消失了？](/help/components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[“计算量度合计”是如何计算的？](/help/components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## 如何访问计算量度生成器？{#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Click **[!UICONTROL + Add]** at the top of the Calculated Metric Manager, or
* In any Analytics report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Add]**.

## 如何访问计算量度管理器？{#section_DD0BD13E9EC940268EBE8BC88241A152}

* Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Components]** in the left navigation. 接着，单击 **[!UICONTROL Calculated Metrics]**。

* In any [!DNL Analytics] report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Manage]**.

## 为什么我会看到这么多具有相同名称的计算量度？{#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(以前，全局计算量度不归任何特定管理员用户所有，并且该报表包的所有用户都可见。 这些指标被报告套件隔开。 如果一个报表包中的度量与其他报表包中的度量同名，则在用户切换报表包时，该度量仅会显示为同一度量。)

现在，指标不再由报表包隔开。 如果一个报表包中的度量与其他报表包中的度量同名，则它们将在“计算量度生成器”和“度量选择器”中都可见，并且可能显示为重复度量，即使它们可能具有或可能没有相同的定义。

仅当您取消选中如下所示的（仅限 `<report suite>`）复选框时，您才会看到大量具有相同名称的计算量度（但它们是在不同的报表包中创建的）：

![](assets/report_suite.png)

**您需要做什么**

请考虑合并名称和定义相似的计算量度，但在合并时要小心。 您可以在计算量度管理器中检查报表包中的计算量度，以验证其原始报表包。 在删除潜在重复时，您还应检查量度的定义，以确保正确整合量度。

>[!NOTE] 即使计算量度不再绑定到特定的报表包，并且可在对登录公司可见的任何报表包中使用，在其中创建或上次在其中保存该计算量度的报表包仍然会在计算量度管理器中可见。

>[!NOTE] 即使计算量度被删除，任何引用该量度的书签或功能板报表仍可正常工作。

## 我的全局计算量度发生了什么情况？{#section_7351D4C7361F4ABAA1B43F8E89AAD211}

(以前，管理员可以通过管理工具在报表包中创建计算量度（称为“全局计算量度”或“报表包计算量度”）。

全局计算量度现在由登录公司列表的管理员用户拥有。 默认情况下，它们将与“所有人”共享。 此模式遵循与区段相同的共享模型和迁移计划。

**您需要做什么**

没什么。 但是，新管理员所有者在修改或删除这些计算量度时应小心——这些计算量度可能用在许多已加入书签的报告和仪表板中。

>[!NOTE] 即使计算量度被删除，任何引用该量度的书签或功能板报表仍可正常工作。

## 在登录公司之间共享的全局计算量度发生了什么情况？{#section_59E5CD948ED643AE9AD3D2E4277647F8}

(以前，管理员可以通过管理工具在报表包中创建计算量度（称为“全局计算量度”或“报表包计算量度”）。 然后，通过将报表包添加到多个登录公司，可以在登录公司之间“共享”这些指标。)

全局计算量度无法再跨登录公司共享。 它们不再绑定或绑定到特定报表包，而是绑定到特定登录公司。 跨登录公司共享的计算量度

* 已被迁移到所有可访问该报表包的登录公司。
* 默认设置为“与所有人共享”。
* 将成为与所有其他登录公司无关的副本。

>[!NOTE] 如果计算量度用在书签、功能板、警报或计划报表中，则编辑新副本将不会影响原来存留的计算量度。

## 具有数值或数值 2 分类的计算量度发生了什么情况？{#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(Previously, calculated metrics with a Numeric or Numeric2 classification were only visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs.)

Now, calculated metrics with a Numeric or Numeric2 classification will continue to be visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs. 但是，任何应用了区段的报表将不支持这些量度。

此外，以下组件不支持具有数字或数字2分类的计算量度： [!UICONTROL Ad Hoc Analysis]、 [!UICONTROL Analysis Workspace][!UICONTROL Real-Time] 报告 [!UICONTROL Anomaly Detection]和 [!UICONTROL Contribution Analysis]。 在创建或编辑具有数字或数字2分类的计算量度时，您会看到一条兼容性警告，指出该计算量度与产品的某些区域不兼容。

**您需要做什么**

如果该量度旨在与区段或任何不兼容组件一起使用，请避免使用Numeric1或Numeric2分类创建计算量度。

## 存留期量度发生了什么情况？{#section_AEDB02EF24584DAD8731BED9DDCE4F48}

存留期量度（也称为全时量度）不再受到支持，并且不再显示在 [!UICONTROL Reports & Analytics] UI 或其他任何 UI 中。无法通过报表API查询这些属性。

只要报告中还至少有一个其他有效指标，则包含所有时间指标的任何书签、仪表板、计划报告或警报都将继续运行，而不含该指标。 如果书签、仪表板、计划报表或警报上的唯一度量是全时度量，则该报表将不再运行。

## 有关基于每日/每周/每月/每季/每年独特访客量度的计算量度，我需要了解什么？{#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Calculated metrics based on Unique Visitor metrics will be visible in the following [!DNL Analytics] components: [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and Reporting API.

但是，以下组件不支持这些指标： [!UICONTROL Segments]、 [!UICONTROL Analysis Workspace][!UICONTROL Real-Time] 报告 [!UICONTROL Anomaly Detection]和 [!UICONTROL Contribution Analysis]。 在创建或编辑基于独特访客量度的计算量度时，您将看到一则兼容性警告，指出该量度与产品的某些部分不兼容。

在包含区段的报表上使用基本的唯一访客量度。 您可以创建基于独特访客量度的计算量度；但是，该计算量度不可应用于具有区段的报表，也不能在其中嵌套区段。

## 通过旧报表包 API 方法创建或管理的计算量度怎么样了？{#section_13ED1BAD02634674BDAEB479B060A4B6}

以前，使用（1.3或1.4）API方法ReportSuite.SaveCalculatedMetrics保存计算量度与在管理控制台中创建或更新计算量度相同。 ReportSuite.DeleteCalculatedMetrics同样适用。 此外，在Admin Console中或调用ReportSuite.GetCalculatedMetrics时显示的计算量度的列表相同。

现在，ReportSuite CalculatedMetrics API 方法（1.3 或 1.4）将会继续使用旧存储来保存、删除和检索计算量度。现有计算量度将迁移到新的“计算量度生成器”中，并且可见。 **使用API方法创建的新计算量度将仅在API中可见。 它们仍可用于报告API。**

**您需要做什么**

如果需要同时使用API和Calculated Metric Builder，则应停止使用ReportSuite CalculatedMetrics API方法，而应使用新的CalculatedMetrics API方法（Get、Save、Delete和GetFunctions）。

## “当前数据”支持所有类型的计算量度吗？{#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

当前数据不支持包含细分或统计函数的计算量度。 唯一支持的函数是基本数学函数，如加法、删除、乘法、除法和取反(-x)。

## 随迁移的计算量度出现的“未提供名称”是什么意思？{#section_C90CBB72A67644F38D583301981F8D03}

“未提供名称”表示没有任何量度名称与该迁移的量度关联（只是一个没有描述性名称的公式）。

## 如果用户被删除，那么该用户的计算量度会发生什么情况？{#section_42ED4C15830540879C4A161423690E5A}

此用户创建的所有计算量度也将被删除。 但是，已删除的计算量度仍将作为保存的书签、仪表板或计划报告的一部分工作。

## 我为什么看到“未知”计算量度对于其他报表包“无效”，即使可以创建这些量度并将其应用于这些报表包？{#section_6772818EFDED46E9B7095D64C3B77211}

如果计算量度包含的基本量度或维度在选定报表包中不存在，则用户界面会显示“未知”。

## 为什么没有保存我对旧计算量度所做的更改？{#section_81CDEFCA1FD542579AF183DA1494EAF0}

这可能是由于迁移到2015年6月15日至6月18日之间新计算的度量数据库的时间。

**您需要做什么**

您必须重做对旧版量度所做的更改。

## 为什么我的计算量度没有显示在营销渠道报表中？{#section_FC350359A775433AB5F43C7CAB304D62}

(以前，所有计算的指标都列在具有“首次联系”和“最近联系”选项的营销渠道报告的指标选择器中。)

现在，只有那些在“计算量度”生成器中将其分配类型专门设置为“首次联系”或“最近联系”的计算量度才可在“营销渠道”报表的量度选择器中使用。 请注意，任何已应用于营销渠道报表的计算量度将继续应用并像以前一样工作。 要为营销渠道创建计算量度，请单击量度构建器中的配置图标，然后选择“首次联系”或“最近联系”作为分配类型。 请记住，这样做将使计算量度仅与营销渠道报表兼容，而不可用在其他任何报表中。

## 为什么某些计算量度显示的公式没有我添加的圆括号？{#section_AC0D1E9714AD487F9A1C73359F518B5E}

在迁移过程中，Adobe从一些公式中去掉了多余的括号。 只删除不影响度量计算方式的括号。 这不会更改数据，只是简化了公式。

## （仅限 Ad Hoc Analysis）具有嵌套或内联区段定义的计算量度仍然受支持吗？{#section_B25C924A282F49388AB604E3D826F44C}

在临时分析中创建的计算量度以前可能包含内联区段定义。 这已经不可能了。

**您需要做什么**

您需要明确地保存区段。具有内联区段定义的现有计算量度将继续正常运行，并且可以在 Ad Hoc Analysis 中查看，但是它们在没有显式保存区段的情况下无法被保存。

## （仅限 Report Builder）为什么计算量度从我的请求中消失了？{#section_DA4792FE5D7945218CD5E6328DE08E82}

如果请求是在版本 5.2 中创建的并且包含计算量度，那么这些量度在版本 5.1 或更早版本中不可见。这是因为计算量度现在使用全局ID（非报表包特定ID）。

**您需要做什么**

您需要升级到v5.2才能查看这些指标。

## “计算量度合计”是如何计算的？{#section_57BA3A299C7948ABB82B0392A9B0F33E}

When [!UICONTROL Reports & Analytics] shows a calculated metrics total in [!UICONTROL Reports & Analytics], it&#39;s just applying the formula to the total. 例如，计算的量度“订单／访问”的总数将采用“总订单”并除以“总访问”。 但是，在某些情况下，计算的度量总计不仅是行项目的总和，而是站点的总和。

示例1:访客搜索词：同一访客可能已搜索多个词，因此在这种情况下，总访客不等于行项的总和。

示例2:产品的页面视图:在购物车中，可能有多个产品，因此购物车中有多个页面视图。 有关比较行项目总和与报告总计的详细信息，请参阅 [此知识库文章](https://helpx.adobe.com/cn/analytics/kb/sum-line-items-different-from-total.html)。
