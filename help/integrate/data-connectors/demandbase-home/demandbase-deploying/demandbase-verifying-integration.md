---
description: 通过检查实时跟踪和报告，验证集成成功捕获数据。
seo-description: 通过检查实时跟踪和报告，验证集成成功捕获数据。
seo-title: 验证集成
title: 验证集成
uuid: a9a0746a-4845-41e-919e-e85 d95 c305
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Verifying the Integration{#verifying-the-integration}

通过检查实时跟踪和报告，验证集成成功捕获数据。

## Live Tracking {#section-9c20e8ff6b404ae09387ee07d675c9e2}

使用DigitalPulse调试程序工具验证Demandbase维度数据是否正通过到Adobe Analytics发送。删除cookies后，重新加载已部署集成代码的网站上的某个页面。假定您当前的IP映射到Demandbase所识别的组织，您应当看到类似于下面的结果。

**Reports&amp; Analytics(之前名为SiteCatalyst)包括两个Demandbase上下文数据变量：**

![](assets/debugger1.png)

** Target Mbox包括Demandbase Profile参数：****

只有在页面上实施Target并且已经为Adobe Target配置此集成的情况下，才会看到这一点-请参阅Adobe集成向导中的步骤4。

![](assets/debugger2.png)

## 报表 {#section-1792fe75dc3249d0ad063dfd87a89162}

使用为您自动创建的控制面板(第步)，在Adobe Analytics中查看您的Demandbase报表。

您也可以导航到Adobe Analytics菜单结构中的Demandbase报表-请参阅下面的屏幕截图。

>[!NOTE]
>
>此数据应在成功部署的24-48小时内显示。

![](assets/reporting1.png)

![](assets/reporting2.png)

## 常见问题解答 {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**“[n/a]”是什么意思？**

Demandbase Data Connector通过设置此默认值指示属性何时“不可用”。默认情况下有两个常用的场景：

* Demandbase检测到访客来自不属于公司的IP地址。
* 使用“帐户观察”属性(以“观察_列表”开头)，但公司不在您的帐户观察列表中。

**Why does “[n/a]” appear more often for certain attributes? **

Demandbase对所有IP地址进行分类，并提供受众和受众_细分属性，即使访客不来自公司IP也是如此。当受众返回“住宅”、“无线”和“款待”等值时，其余属性可能不可用。

At times, a visitor’s audience will be “SMB”, but other attributes will show “[n/a]”. 这意味着Demandbase能够将访客分类为小型企业，但整个公司档案不可用。当多个小型企业使用同一服务提供商或IP地址块时，通常会发生这种情况。

## Developer Considerations {#section-d33fff55bc4b4db99f82dee418ef1bc2}

如果需要调整实现中的默认值，请更新该行：

```
_db._nonOrgMatchLabel = "[n/a]";
```

