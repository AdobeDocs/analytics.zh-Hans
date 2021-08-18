---
description: '使用A4T和Adobe Analytics虚拟报表包时的特殊注意事项 '
title: 虚拟报表包和Analytics for Target(A4T)
source-git-commit: 6a47ebc58cb36079940cfc4e5cdc80cf99c18a50
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# 虚拟报表包和Analytics for Target(A4T)

在Adobe Target上下文中使用虚拟报表包时，请考虑以下注意事项：

* 您不能将数据直接从Target发送到虚拟报表包，只发送到真实的报表包。
* 您可以在虚拟报表包中报告A4T活动。 但是，A4T数据仅限于与虚拟报表包区段（以及应用的任何其他区段）匹配的行。 例如，如果您为EMEA客户创建了虚拟报表包，则该虚拟报表包中的A4T数据仅反映您的EMEA客户的Target数据。
* 您无法将虚拟报表包中的区段发布回Target以进行激活。