---
title: 城市
description: 火灾发源地城市。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---


# 城市

“城市”维度报告了受到冲击的城市。 此维度有助于确定访客访问网站时最受欢迎的城市来源。 您可以利用这些数据来关注这些城市的本地广告，如广告牌或广告。

## 用数据填充此维

此维引用Adobe内部的查找规则。 查找值基于随点击发送的IP地址。 Adobe与Digital Element [携手合作](https://www.digitalelement.com/) ，维护IP地址与城市之间的查找。 此维度适用于所有实施。

>[!TIP]
>
>如果您的组织遵循严格的隐 [私法规，而模糊](/help/admin/admin/general-acct-settings-admin.md) 化IP地址是不够的，您可以请求完全禁用地理位置数据。 使用报表包ID联系客户关怀，并请求关闭报表包的“地理位置”。

## 维项

维度项目包括世界各地的城市。 示例值 `"New York (New York, United States)"`包括 `"Bangalore (Karnataka, India)"`、或 `"London (London, United Kingdom)"`。

## 报告位置与实际位置之间的差异

由于此维度基于IP地址，因此某些情况可能显示报告位置与实际位置之间的差异：

* **代表公司代理的IP地址**: 这些访客可以显示为通过用户公司网络的流量，如果用户远程工作，则可能是不同的位置。
* **移动IP地址**: 移动IP定位工作的级别因位置和网络而异。 许多运营商通过集中或区域存在点回传IP流量。
* **卫星ISP用户**: 识别这些用户的特定位置是困难的，因为他们通常看起来源自上行链路位置。
* **军事和政府知识产权**: 代表在全球各地旅行并通过其家乡（而不是他们目前驻在的基地或办公室）进入的人员。
