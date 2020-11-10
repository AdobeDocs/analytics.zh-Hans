---
title: 导入付费搜索指标
description: 配置Adobe Analytics以跟踪您的付费搜索指标的步骤（例如，Google AdWords、MSN、Yahoo等） 使用数据源。
translation-type: tm+mt
source-git-commit: 81592ab80942b802fff3df62d2cd44b1e376aff8
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 8%

---


# 使用 [!UICONTROL 数据源导入] “付费搜 [!UICONTROL 索”指标]

对于许多营销组织而言，付费搜索是触及新客户和保留现&#x200B;有客户的最有价值、最可靠的方式之一。 Adobe Analytics [!UICONTROL 的数据源] (Data Sources)功能使得从Google AdWords等数字广告平台导入高级付费搜索数据变得很容易。 您可以将其与其他营销数据以及现场行为和客户属性数据相集成，以便更好地了解组织的付费搜索工作。

这些步骤向您展示如何配置与AdWords的集成以导入关键字数据以及展示次数、点击次数、每次点击成本等指标。

这些步骤说明如何设置一次性导入的按次点击付费数据。 但是， [!UICONTROL 数据源] (Data Sources)允许使用此处描述的文件格式持续导入数据。 根据您的付费搜索平台，您可以计划定期导出（每日、每月等），设置自动化流程，将这些导出转换为Adobe Analytics需要的文件格式，并将这些文件上传到Adobe Analytics进行付费搜索集成报告。

## 先决条件

* 您已实施付费搜索检测。
* 您正在捕获跟踪代码数据。
* 每个广告组都有唯一的跟踪代码。

## Configure [!UICONTROL Success Events]

我们的第一步是让Adobe Analytics准备好接受指标。 为此，您需要设置一些成功事件。

[!UICONTROL 成功事件是指可跟踪的活动。]You determine what a [!UICONTROL success event] is. 为了跟踪付费搜 [!UICONTROL 索量度] ，我们希望设置点击量、 [!UICONTROL 印象总成] 、 [!UICONTROL 、、支]持和支 [!UICONTROL 持的成]本和启用的成功事件。

1. Go to **[!UICONTROL Adobe Analytics > Admin > Report Suites]**.
1. 选择报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置 > 转化 > 成功事件]**.

   ![成功事件](assets/success-events.png)

1. 在“自定义成功事件” **[!UICONTROL 下，使用]** “添加新”创建3个自定义成功事件: [!UICONTROL 点击] （计数器） [!UICONTROL 、展] 示 [!UICONTROL （计数器）] 和总成本（货币）。

   ![新的成功事件](assets/new-success-events.png)

1. 单击“保存”。您应会收到一条消息，表明您的保存版本已获得批准。
1. 导航到管 **[!UICONTROL 理员>报表包>编辑设置>转换>转换变量]**。
1. 选中“活动”>“活动变量”下“ **[!UICONTROL 跟踪代码]** ”旁 **[!UICONTROL 的复选框，启用跟踪代码]**。

   ![促销活动变量](assets/campaign-variable.png)

## 设置数据源

[!UICONTROL 数据源] 允许您与Adobe Analytics共享非点击流数据。 在这种情况下，我们使用Adobe Analytics跟踪付费搜索指标。 我们使用跟踪代码作为将两个数据片段(付费搜索指标和Adobe Analytics指标)绑定在一起的关键。

1. 导航到 **[!UICONTROL Adobe Analytics>管理>数据源]**。
1. 选择创 **[!UICONTROL 建选项]** 卡以开始激活新数据源。
1. 在选 **[!UICONTROL 择类别]**&#x200B;下，选择 **[!UICONTROL 广告活动]**。

   ![数据源](assets/data-sources.png)

1. 在“ **[!UICONTROL 选择类型]**”下， **[!UICONTROL 选择“通用按点付费服务”]**。
1. 单击&#x200B;**[!UICONTROL 激活]**。The [!UICONTROL Data Source Activation Wizard] displays:

   ![激活向导](assets/ds-activation-wizard.png)

1. 单击 **[!UICONTROL 下一]** 步，然后命名数据源。 此名称显示在数据源管理器中。
1. 接受服务协议并单击“下 **[!UICONTROL 一步]**”。
1. 选择以下三个标准指标： [!UICONTROL 展示次数]、 [!UICONTROL 点击次] 数和总 [!UICONTROL 成本] ，然后单 **[!UICONTROL 击下一步]**。
1. 现在，将此新数据源“映射”到我们在“配置成功”事件中创 [建的自定义事件](/help/admin/admin/c-success-events/t-success-events.md)。

   ![映射](assets/data-source-mapping.png)

1. 选择数据维选中“跟踪代码”旁边的框，然后单击“下 **[!UICONTROL 一步]**”。
1. 映射数据Dimension。
将导入的数据维（属性）映射到要存储它的Adobe Analytics属性。 这可能是标准尺寸或eVar。 单击“下 **[!UICONTROL 一步]**”后，生成的映射显示在摘要中：

   ![概要](assets/data-source-summary.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 单击 **[!UICONTROL “下载]** ”以下载此数据源的模板文件。
文件名与您最初指定的数据源类型相对应——在本例中为“Generic Pay-Per-Click Service template.txt”。
1. 在您喜欢的文本编辑器中打开模板。
文件已填充度量、维及其映射。

## 导出PPC数据并将其上传到Analytics

与Google Adwords、MSN、Yahoo和其他PPC帐户的这些工作相似的步骤。

### 导出数据

1. 登录您的PPC帐户并创建新报告或导出。
确保导出包含以下字段：日期、目标URL(登陆页)、印象、点击和成本。 导出可以包括其他字段，但您将按照以下步骤删除这些字段。
1. 如果可能，将报告另存为制表 `.csv` 符分隔的文件。 这样，在以下步骤中可以更轻松地进行工作。
1. 在Microsoft Excel中打开文件。

### 在Microsoft Excel中编辑文件

1. 在Microsoft Excel中，删除除上述列以外的所有列。
1. 删除顶部的任何额外行。
1. 要从目标URL分离跟踪代码，请执行以下操作：a.从所有列复制和粘贴数据。
b.单击 **[!UICONTROL 数据>文本到列]**。
c.在向导的步骤1中，确保选中“分 **[!UICONTROL 隔]** ”，然后单击“下 **[!UICONTROL 一步”]**。
d.在向导的步骤2中，根据您创建URL的方式指定分隔符(? 或&amp;)，然后单击“下 **[!UICONTROL 一步]**”。
e.在向导的步骤3中，预览数据并确保其中一列为“trackingconodame=trackingcode”。 如果您有其他变量，请重复这些步骤（使用&amp;作为分隔符）。
f.删除除跟踪代码、印象、点击和费用外的所有列。 添加一个名为“日期”的新列，并按以下顺序组织列：日期：:跟踪代码：:展示次数：点击：成本。
1. 将此数据添加到您在上面的“设置数据源”部分下载的模板。
现在，您已准备好上传文件。

### 通过FTP将文件上传到Adobe Analytics

返回“数据源”向导以获取说明并通过FTP上传文件：

![上传FTP](assets/upload-ftp.png)

## 创建计算量度

添加计算指标有助于您做出按点击付费决策。

例如，您可以添加以下计 [算量度](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics):

| 名称 | 公式 | 量度类型 | 描述 |
| --- | --- | --- | --- |
| 每次访问页面查看次数 | 页面查看/访问 | 数值 | 应用于网站级别时：显示每次访问的平均页面数量。应用于“最受欢迎页面”报表时：显示每次访问时特定页面的平均查看次数。 |
| 平均订购值 | 收入/订购 | 货币 | 显示每次订购的平均收入。 |
| 每次访问的收入 | 收入／访问 | 货币 | 显示每次访问的平均收入。 |
| 点进率(CTR) | 点击次数／展示次数 | 数值 | 衡量在线广告或电子邮件营销活动的点击率与展示次数之比。 |
| 利润 | 收入——成本 | 货币 | 显示活动的收入减去成本。 |
| 每印象利润(PPI) | （收入——成本）/印象 | 货币 | 显示每次展示广告时产生的收入与成本之间的平衡。 |
| 广告支出回报(ROAS) | 销售额／广告支出 | 货币 | (ROI)表示在相应广告上每美元所赚得的美元。 |

## 配置和运行报告

最后一步是将数据源指标和任何计算指标添加到“跟踪代码”报告，并深入活动，立即了解每个广告组的表现。

1. 在“ **[!UICONTROL Adobe Analytics”]**>“报告”中，选择已导入数据源的报告包。
1. 导航到 **[!UICONTROL 报表>活动>跟踪代码>跟踪代码]**。
1. 选择日期范围。
1. 单击 **[!UICONTROL 指标>添加]** ，并添加标准指标列表中的数据源指标（点击量、展示次数、总成本）。
1. 对可能已添加的任何计算量度执行相同操作。 在您添加量度时，报告将更新。
