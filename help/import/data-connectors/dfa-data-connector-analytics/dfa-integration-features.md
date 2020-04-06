---
description: '激活后，Data Connectors DFA 集成为您的 Adobe Analytics 报表提供以下量度 '
keywords: DFA
title: 集成功能
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 集成功能{#integration-features}

激活后，Data Connectors DFA 集成为您的 Adobe Analytics 报表提供以下量度:

* 视图率
* DFA单击
* 展示次数
* （可选）DFA成本数据
* （可选）DFA查询错误，超时

>[!NOTE] 此集成不支持点击跟踪器（以前称为点击命令）。单击跟踪器用于记录对文本链接、电子邮件中的链接或网站上硬编码的其他元素的点击次数。

数据连接器DFA集成会根据DFA返回的数据自动构建DFA跟踪代码。 这些跟踪代码被构造为唯一标识广告及其关联的位置和创意。 下面根据集成版本概述了跟踪代码的结构。 版本1.5如下所示：

![](assets/DFA_id_struct1_5.png)

版本2.0如下所示：

![](assets/DFA_id_struct2.png)

这些ID用作Genesis和DFA之间的共享密钥，以关联正确的分类和指标。

| 网站 ID | 承载广告的第三方站点。 站点名称分类提供此站点ID的描述性名称。 |
|---|---|
| 广告 ID | 交付给用户的商业消息的ID。 广告名称分类包含由您的组织在DFA系统中定义的广告名称。 例如：`Hybrid Coup Textlink - Build`。 |
| 版面 ID | 网站的DFA帐户、网站的一部分或您购买广告空间的网站组中的表示形式。 |
| 创作 ID | 要显示给访客的图像、Flash SWF或其他资源。 “创意名称”分类包含您在DFA界面中为此创意提供的名称。 |

其他两个分类(投放工具（广告商的DoubleClick）和渠道（横幅广告）对于任何DFA活动具有相同的值，并有助于区分DFA导入的数据。

## SearchCenter重复数据消除 {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

DFA 集成现在支持 Adobe SearchCenter 感知。通过 Data Connectors 向导启用 SearchCenter 重复数据删除，搜索驱动型访客将不会导致数据从 DFA 的 Floodlight 服务器中提取，并且 DFA 不会填充 *`s.campaign`*，从而允许 SearchCenter 对其进行填充。此外，DFA和SearchCenter现在将重复数据消除值填充到每个产品的变量中。

下面的列表概述了启用SearchCenter重复数据消除时启用的逻辑：

如果 **[!UICONTROL DFA]** 在向 **[!UICONTROL SearchCenter deduplication]** 导中选择了>:

* 对于 DFA 点进，集成会将字符串“DFA Clickthrough”填入配置的 SCM eVar。
* 对于 DFA 显示到达，集成会将字符串“DFA Viewthrough”填入 SCM eVar。

如果 **[!UICONTROL SearchCenter]** 在向 **[!UICONTROL DFA deduplication]** 导中选择了>:

* 对于 DFA 显示到达，集成会将字符串“DFA Viewthrough”填入 SCM eVar。

>[!NOTE] 如果启用“SearchCenter”>“DFA 重复数据删除”，并设置了 SearchCenter 查询字符串参数，则访问将不考虑进行 DFA 处理。这意味着 SearchCenter 查询字符串参数应当不同于 DFA 点进参数，并且没有任何显示广告应设置 SearchCenter 查询字符串参数。

