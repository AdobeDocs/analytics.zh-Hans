---
description: 介绍完成向导后在Lyris中配置什么的步骤。
seo-description: 介绍完成向导后在Lyris中配置什么的步骤。
seo-title: Lynris eMails中的配置
solution: Analytics
title: Lynris eMails中的配置
uuid: 1276176d-e5 e9-451a-9a7 b-9f29 a340 a25 b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configuration within the Lyris EmailLabs{#configuration-within-the-lyris-emaillabs}

介绍完成向导后在Lyris中配置什么的步骤。

1. 完成集成向导后，您必须与Lyris Professional团队合作，完成与Lyris HQ帐户的集成并促进测试。
1. 添加URL查询字符串参数：验证URL追加字符串是否正确输入用户界面的“组织”设置区域。这应包含系列活动级别ID(hq_ m)和收件人级别ID(hq_ v)。

   字符串ID的示例为：

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >If you are applying Lyris’s native analytics tool, *Click Tracks* tags all of the required variables that are added.

