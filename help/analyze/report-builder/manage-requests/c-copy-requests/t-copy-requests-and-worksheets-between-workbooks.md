---
description: 将源工作簿中的整个电子表格复制为一个或多个目标工作簿中的电子表格。
title: 在工作簿之间复制请求和工作表
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 100%

---

# 在工作簿之间复制请求和工作表

将源工作簿中的整个电子表格复制为一个或多个目标工作簿中的电子表格。

要执行此操作，您必须在同一 Excel 实例中打开至少 2 个工作簿：第一个源工作簿的电子表格（工作表）中包含映射到单元格的请求，而另一个目标工作簿是目标位置。对于每个新目标工作簿，您应该首先登录以访问与源工作簿相同的报表包，然后才能粘贴包含请求的电子表格。
1. 右键单击源工作簿中的电子表格，然后选择&#x200B;**[!UICONTROL 复制带有请求的工作表]**。
1. 在目标工作簿中，右键单击电子表格，然后选择&#x200B;**[!UICONTROL 粘贴带有请求的工作表]**。

   同一 Excel 实例是指在某个时间计算机上只运行一个 Excel 进程 ([!DNL excel.exe])。如果启动两个 Excel 实例，然后尝试将工作表从第一个 Excel 实例中的工作簿复制到第二个 Excel 实例中的工作簿，则 Report Builder 不会在第二个 Excel 实例的快捷菜单中提供粘贴工作表的选项。

   如果登录使用不同报表包的源工作簿和目标工作簿，则粘贴操作后只能看到影响目标工作簿格式的结果。Report Builder 会显示一条消息，指出基于指定报表包（位于源工作簿中）生成的请求相关信息在目标工作簿中不可用。要显示粘贴到目标工作簿的请求，必须登录到使用与源工作簿相同的报表包的目标工作簿。

   您可以将一个或多个请求从一个工作簿的电子表格复制并粘贴到另一工作簿的电子表格，但是第二个工作簿必须在同一 Excel 实例中作为另一文档打开。两个工作簿中的请求必须通过相同的报表包登录创建。
