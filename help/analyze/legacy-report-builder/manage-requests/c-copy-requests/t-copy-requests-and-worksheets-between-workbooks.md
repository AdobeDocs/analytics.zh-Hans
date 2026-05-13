---
description: 了解如何将电子表格从源工作簿复制到一个或多个目标工作簿。
title: 如何在工作簿之间复制请求和工作表
uuid: 6b2c4259-d8cb-430e-819f-38e213dd2661
feature: Report Builder
role: User, Admin
exl-id: 1a2363da-603e-4d1d-aefa-14ce71554247
TQID: https://experienceleague.adobe.com/0GVqb80fMIVJlip2dWGgzllmCGG2Hc8368WZlThzzh0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 379
ht-degree: 14%

---

# 在工作簿之间复制请求和工作表

{{legacy-arb}}

将源工作簿中的整个电子表格复制到一个或多个目标工作簿中的电子表格。 要实现此目的，您必须在同一Excel实例中至少打开两个工作簿：

* 第一个源工作簿包含电子表格（工作表），其中请求映射到单元格。

* 其他目标工作簿是目标。 对于每个新的目标工作簿，在粘贴包含请求的电子表格之前，您应该登录到与源工作簿相同的报表包。

>[!NOTE]
>
>您必须使用与源工作簿相同的报表包登录到目标工作簿。 必须使用相同的报表包登录名创建两个工作簿中的请求。

1. 右键单击源工作簿中的电子表格，然后选择&#x200B;**[!UICONTROL 复制带有请求的工作表]**。
1. 在目标工作簿中，右键单击电子表格，然后选择&#x200B;**[!UICONTROL 粘贴带有请求的工作表]**。

   同一 Excel 实例是指在某个时间计算机上只运行一个 Excel 进程 ([!DNL excel.exe])。 如果您启动两个Excel实例，并尝试将工作表从第一个Excel实例的工作簿复制到第二个Excel实例的工作簿，则Report Builder不会提供在第二个Excel实例的快捷菜单中粘贴工作表的选项。

   如果您使用不同的报表包登录到源工作簿和目标工作簿，则您在粘贴操作中看到的唯一结果就是那些影响目标工作簿格式化的结果。 Report Builder会显示一条消息，声明从指定报表包（在源工作簿中）派生的请求的信息在目标工作簿中不可用。 要显示粘贴到目标工作簿的请求，必须使用与源工作簿相同的报表包登录到目标工作簿。

   您可以将一个或多个请求从一个工作簿中的电子表格复制并粘贴到另一个工作簿中的电子表格，只要第二个工作簿作为同一Excel实例中的另一个文档打开。 必须使用相同的报表包登录名创建两个工作簿中的请求。
