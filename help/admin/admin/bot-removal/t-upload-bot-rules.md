---
description: 若要批量导入机器人规则，您可以上载定义规则的 CSV 文件。
seo-description: 若要批量导入机器人规则，您可以上载定义规则的 CSV 文件。
seo-title: 上载机器人规则
solution: Analytics
subtopic: 机器人规则
title: 上载机器人规则
topic: 管理工具
uuid: bd70c199-5817-437e-980d-6d8f95d82f2c
translation-type: tm+mt
source-git-commit: d0bd48684764a60b488d1e39c968ad70c743f1db

---


# 上载机器人规则

若要批量导入机器人规则，您可以上载定义规则的 CSV 文件。

按显示的顺序创建具有以下列的CSV文件：

| 栏目 1 | 栏目 2 | 栏目 3 | 栏目 4 | 栏目 5 |
|--- |--- |---|---|---|
| 机器人名称 | 起始 IP | 终止 IP | Agent Match Rule<br>(contains or starts with)</br> | 代理排除(<br>255个字符限制)</br> |

您可以定义三种类型的机器人规则：

* 用户代理包含或开头
* 单个 IP 地址或通配符匹配
* IP 范围匹配

导入文件中的每行都可以包含唯一一个下列机器人定义：

* **用户代理包含或开头**：提供单个用户代理字符串与“代理包含”列中的内容进行匹配。通过在“代理匹配规则”字段中置入&#x200B;*包含*&#x200B;或&#x200B;*开头*，指定您想要执行的匹配类型。An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. 字符串匹配区分大小写。“起始 IP”和“终止 IP”列都必须为空。

* **单个IP地址或通配符匹配**：要匹配单个IP地址( `10.10.10.1`)或通配符IP地址( `10.10.*.*`)，请在IP开始和IP结束列中放置相同的值。“匹配规则”、“代理包含”和“代理排除”都必须为空。

* **IP 范围匹配**：使用“起始 IP”和“终止 IP”列来定义 IP 地址的范围。Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. “匹配规则”、“代理包含”和“代理排除”都必须为空。

## 使用 OR 组合多个规则

若要使用通过 OR 连接的规则组合（例如，用户代理或 IP 地址）与机器人进行匹配，请在机器人名称字段中为所有要组合的规则提供相同的名称。不支持 AND 匹配。

## 使用上载文件覆盖所有规则

选中&#x200B;**[!UICONTROL 覆盖现有规则]复选框会删除所有现有规则，并会使用上载文件中定义的规则替换现有规则。**

## 导出规则

**[!UICONTROL 导出上传的机器人文件]按钮可以 CSV 格式导出 UI 中定义的所有规则。**
