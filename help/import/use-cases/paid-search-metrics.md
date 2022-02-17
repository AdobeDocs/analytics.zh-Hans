---
title: 导入付费搜索量度
description: 配置Adobe Analytics以跟踪您的付费搜索量度(例如，Google AdWords、MSN、Yahoo等)的步骤 使用数据源。
exl-id: b25a2a26-d277-4a51-9194-973acb425095
source-git-commit: 7c5bfadabe2ea851bb881d067d48b4f4700a53c7
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 8%

---

# 导入 [!UICONTROL 付费搜索] 使用量度 [!UICONTROL 数据源]

对于许多营销组织而言，付费搜索是接触新客户和保留现&#x200B;有客户的最有价值、最可靠的方式之一。 的 [!UICONTROL 数据源] Adobe Analytics中的功能，可轻松从Google AdWords等数字广告平台导入高级付费搜索数据。 您可以将其与其他营销数据以及网站行为和客户属性数据相集成，以便更好地分析贵组织的付费搜索工作。

这些步骤将向您展示如何配置与AdWords的集成，以导入关键词数据以及展示次数、点击次数、每次点击成本等量度。

这些步骤说明了如何设置一次性导入每次点击付费数据。 但是， [!UICONTROL 数据源] 允许使用此处所述的文件格式持续导入数据。 根据您的付费搜索平台，您可能可以计划定期导出（每日、每月等），设置自动化流程，将这些导出转换为Adobe Analytics所需的文件格式，并将这些文件上传到Adobe Analytics以进行付费搜索集成报告。

## 先决条件

* 您已实施付费搜索检测。
* 您正在捕获跟踪代码数据。
* 您每个广告群组的跟踪代码各不相同。

## 配置 [!UICONTROL 成功事件]

我们的第一步是准备Adobe Analytics接收量度。 为此，您需要设置一些成功事件。

[!UICONTROL 成功事件是指可跟踪的活动。]您确定 [!UICONTROL 成功事件] 。 为了跟踪 [!UICONTROL 付费搜索] 量度，我们要设置 [!UICONTROL 成功事件] 周围 [!UICONTROL 点击], [!UICONTROL 展示次数], [!UICONTROL 总成本] 启用[!UICONTROL 跟踪代码].

1. 转到 **[!UICONTROL Adobe Analytics >管理员>报表包]**.
1. 选择报表包。
1. 单击&#x200B;**[!UICONTROL 编辑设置 > 转化 > 成功事件]**.

   ![成功事件](assets/success-events.png)

1. 在自定义成功事件下，使用 **[!UICONTROL 新增]** 要创建3个自定义成功事件，请执行以下操作： [!UICONTROL 点击次数] （计数器）、 [!UICONTROL 展示次数] （计数器）和 [!UICONTROL 总成本] （货币）。

   ![新成功事件](assets/new-success-events.png)

1. 单击“保存”。您应会收到一条消息，指出您的保存已获得批准。
1. 导航到 **[!UICONTROL 管理员>报表包>编辑设置>转化>转化变量]**.
1. 通过选中 **[!UICONTROL 跟踪代码]** 在 **[!UICONTROL 促销活动>促销活动变量]**.

   ![促销活动变量](assets/campaign-variable.png)

## 设置数据源

[!UICONTROL 数据源] 允许您与Adobe Analytics共享非点击流数据。 在本例中，我们使用Adobe Analytics来跟踪付费搜索量度。 我们使用跟踪代码作为键值，将付费搜索量度和Adobe Analytics量度这两个数据段绑定在一起。

1. 导航到 **[!UICONTROL Adobe Analytics >管理员>所有管理员>数据源]**.
1. 选择 **[!UICONTROL 创建]** 选项卡来开始激活新数据源。
1. 在 **[!UICONTROL 选择类别]**，选择 **[!UICONTROL 广告营销活动]**.

   ![数据源](assets/data-sources.png)

1. 在 **[!UICONTROL 选择类型]**，选择 **[!UICONTROL 一般每次点击付费服务]**.
1. 单击&#x200B;**[!UICONTROL 激活]**。的 [!UICONTROL 数据源激活向导] 显示：

   ![激活向导](assets/ds-activation-wizard.png)

1. 单击 **[!UICONTROL 下一个]** 并命名数据源。 此名称显示在数据源管理器中。
1. 接受服务协议并单击 **[!UICONTROL 下一个]**.
1. 选择三个标准量度： [!UICONTROL 展示次数], [!UICONTROL 点击次数] 和 [!UICONTROL 总成本] 单击 **[!UICONTROL 下一个]**.
1. 现在，将此新数据源“映射”到我们在中创建的自定义事件 [配置成功事件](/help/admin/admin/c-success-events/t-success-events.md).

   ![映射](assets/data-source-mapping.png)

1. 选择数据维度选中跟踪代码旁边的框，然后单击 **[!UICONTROL 下一个]**.
1. 映射数据Dimension。
将导入的数据维度（属性）映射到要将其存储在其中的Adobe Analytics属性。 这可以是标准维度或eVar。 在单击 **[!UICONTROL 下一个]**，则生成的映射将显示在摘要中：

   ![概要](assets/data-source-summary.png)

1. 单击&#x200B;**[!UICONTROL 保存]**。
1. 单击 **[!UICONTROL 下载]** 下载此数据源的模板文件。
文件名对应于您最初指定的数据源类型 — 在本例中为“Generic Pay-Per-Click Service template.txt”。
1. 在您喜爱的文本编辑器中打开模板。
文件中已填充量度和维度及其映射。

## 导出PPC数据并将其上传到Analytics

与Google Adwords、MSN、Yahoo和其他PPC帐户的工作步骤类似。

### 导出数据

1. 登录到您的PPC帐户并创建新报告或导出。
确保导出包含以下字段：日期、目标URL（登陆页面）、展示次数、点击次数和成本。 导出可以包含其他字段，但您将按照以下步骤删除这些字段。
1. 如果可能，将报表另存为 `.csv` 或以制表符分隔的文件。 这样，在执行以下步骤时，便于使用。
1. 在Microsoft Excel中打开文件。

### 在Microsoft Excel中编辑文件

1. 在Microsoft Excel中，删除除上述列以外的所有列。
1. 删除顶部的任何额外行。
1. 要将跟踪代码与目标URL隔离，请执行以下操作：a.复制并粘贴所有列中的数据。
b.单击 **[!UICONTROL 数据>文本到列]**.
c.在向导的步骤1中，确保 **[!UICONTROL 分隔]** 选中并单击 **[!UICONTROL 下一个]**.
d.在向导的第2步中，根据URL的创建方式指定分隔符(? 或)，单击 **[!UICONTROL 下一个]**.
e.在向导的步骤3中，预览您的数据，并确保其中一列为“trackingcodename=trackingcode”。 如果您有其他变量，请重复这些步骤（使用和作为分隔符）。
f.删除除跟踪代码、展示次数、点击次数和成本之外的所有列。 添加一个名为Date的新列，并按以下顺序组织列：日期：跟踪代码：:展示次数：单击次数：:成本。
1. 将此数据添加到您在上面“设置数据源”部分下载的模板中。
现在，您已准备好上传文件。

### 通过FTP将文件上传到Adobe Analytics

有关说明，请返回数据源向导，并通过FTP上传文件：

![上传FTP](assets/upload-ftp.png)

## 创建计算量度

在做出每次点击付费决策时，添加计算量度将会很有帮助。

例如，您可以将 [计算量度](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics):

| 名称 | 公式 | 指标类型 | 描述 |
| --- | --- | --- | --- |
| 每次访问页面查看次数 | 页面查看/访问 | 数值 | 应用于网站级别时：显示每次访问的平均页面数量。应用于“最受欢迎页面”报表时：显示每次访问时特定页面的平均查看次数。 |
| 平均订购值 | 收入/订购 | 货币 | 显示每次订购的平均收入。 |
| 每次访问收入 | 收入/访问 | 货币 | 显示每次访问的平均收入。 |
| 点进率(CTR) | 点击次数/展示次数 | 数值 | 测量在线广告或电子邮件营销活动的点击次数与展示次数的比率。 |
| 利润 | 收入 — 成本 | 货币 | 显示促销活动的收入减去成本。 |
| 每次展示盈利(PPI) | （收入 — 成本）/展示次数 | 货币 | 显示每次显示广告时产生的收入量，并与成本平衡。 |
| 广告支出回报率(ROAS) | 销售额/广告支出 | 货币 | (ROI)表示在相应广告上花费的每美元收入。 |

## 配置和运行报表

最后一步是将数据源量度和任何计算量度添加到跟踪代码报表，并深入到营销活动中，以立即查看每个广告组的表现。

1. 在 **[!UICONTROL Adobe Analytics >报表]**，请选择您已将数据源导入到的报表包。
1. 导航到 **[!UICONTROL 报表>促销活动>跟踪代码>跟踪代码]**.
1. 选择日期范围。
1. 单击 **[!UICONTROL 量度>添加]** 并从标准量度列表中添加您的数据源量度（点击量、展示次数、总成本）。
1. 对可能添加的任何计算量度执行相同操作。 在您添加量度时，报表将会更新。
