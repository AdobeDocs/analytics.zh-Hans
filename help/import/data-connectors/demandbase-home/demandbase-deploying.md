---
description: 部署此集成的流程非常简单，只需执行以下操作。
title: 部署集成
uuid: 9c116ca8-4dbf-44eb-a832-574527ee88b7
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 98%

---


# 部署集成{#deploying-the-integration}

部署此集成的流程非常简单，只需执行以下操作。

## 完成 Adobe 集成向导{#completing-the-adobe-integration-wizard}

要激活集成，必须在 Data Connectors 界面中完成配置向导。

1. 导航到 Adobe Experience Cloud 中的“Data Connectors”（以前称为 Genesis）区域。
1. 启动 Demandbase 2.0 集成向导。
1. 选择所需的报表包并提供集成的名称。
1. 配置以下项目：

<table id="table_8D60DC7C48C144DC9934749E7F9F65FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 电子邮件地址 </td> 
   <td colname="col2"> 主要联系人的电子邮件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 描述 </td> 
   <td colname="col2"> （可选）对此集成设置的描述。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Demandbase API 密钥 </td> 
   <td colname="col2"> 您可以从 Demandbase 代表处获取此密钥。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 自定义 Demandbase 维度 #N </td> 
   <td colname="col2"> 这些是 8 个可选维度的 ID。有关更多信息，请参阅“Demandbase 自定义维度”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发送到 Adobe Target </td> 
   <td colname="col2">如果为“true”，则 Demandbase 维度也将使用隐藏的 mbox 发送到 Adobe Target。 <p>注意：必须在网页上实施配置的 mbox.js 文件，才能收集维度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 配置以下变量映射项目：

   | 项目 | 描述 |
   |---|---|
   | Demandbase 维度 | 从报表包中选择一个可用的 eVar 变量。 |
   | Demandbase 自定义维度（可选） | 从报表包中选择一个可用的 eVar 变量。 |

1. 配置自定义维度的名称（如果适用）。

   1. 如果您在步骤 4 中选择包括自定义维度，并在步骤 5 中映射可选 eVar，则必须为这些维度提供易记名称。例如，如果您选择输入“stock_ticker”作为“自定义维度 1”，则应将包含“维度 1”的框更改为“股票报价”。
   1. 请&#x200B;**勿**&#x200B;修改 8 个标准维度的名称（即 Demandbase SID、公司名称、行业等）。

1. 选中自动为您创建 Demandbase 集成功能板的框（推荐）。
1. 查看所有配置项目并单击&#x200B;**[!UICONTROL 立即激活]**。

## 部署集成代码{#deploying-the-integration-code}

完成集成向导后，必须将集成代码部署到 Adobe Analytics 部署代码 (s_code)。

>[!NOTE]
>
> 如果您使用 Adobe TagManager 或 Dynamic Tag Management 来部署 Adobe Analytics，则可以使用任意一种工具轻松添加集成代码。

1. 转到&#x200B;**[!UICONTROL 支持]**&#x200B;选项卡，并从集成的“资源”区域下载并保存 `integration code v2_0_1` 资源。

1. 如果适用，对代码进行任何必要的修改。有关更多信息，请参阅“修改集成代码”（位于本页面）。
1. 如果 Adobe Analytics 部署代码中尚不存在集成模块，请包含该模块。
1. 使用下列方法之一部署代码：

   * 使用 Adobe TagManager 或 Dynamic Tag Management 添加代码。
   * 或者，将代码交付给负责更新 Adobe Analytics 部署代码的组织资源。

>[!IMPORTANT]
>
>在将此集成部署到生产环境之前，请确保在开发/暂存环境中测试此集成的部署。

## 修改集成代码{#modifying-the-integration-code}

在大多数情况下，您无需对 Data Connector 向导生成的集成代码进行任何修改。

但是，如果您确实需要进行调整，可参阅下面介绍的一些代码设置。

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 代码设置 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">Adobe Analytics 图像请求在触发 Analytics 收集服务器之前等待 Demandbase 数据的最大毫秒数。 <p>注意：此设置适用于可能通过集成模块运行的所有集成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._key </td> 
   <td colname="col2"> 您的 Demandbase API 密钥。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._apiURL </td> 
   <td colname="col2"> Demandbase API 的 URL 模板。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._delim </td> 
   <td colname="col2"> 用于在Demandbase维度项发送到AdobeAnalytics时分隔这些维度项的分隔符。 更改此设置可能导致默认分类规则无法正常运行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._setTnt </td> 
   <td colname="col2">如果为“true”，则集成代码将尝试使用隐藏的 mbox 将 Demandbase 维度作为配置文件参数发送到 Adobe Target。 <p>注意：这要求页面上存在 mbox.js 代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._tntVarPrefix </td> 
   <td colname="col2"> 在将 Demandbase 维度发送到 Adobe Target 之前，此字符串会附加到每个 Demandbase 维度名称的前面。例如，如果此设置的值为“db_”，则维度“industry”将作为“db_industry”发送到 Adobe Target。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._dimensionsArray </td> 
   <td colname="col2"> 发送到 Adobe Analytics 的标准 Demandbase 维度。建议不要修改此设置。“max_size”属性是在发生截断之前允许的维度字符数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._dimensionsArrayCustom </td> 
   <td colname="col2"> 发送到 Adobe Analytics 的自定义 Demandbase 维度。“max_size”属性是在发生截断之前允许的维度字符数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._cName </td> 
   <td colname="col2"> 用于保持 Demandbase API 通信状态的会话 Cookie 的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._contextName </td> 
   <td colname="col2"> 用于将标准维度发送到 Adobe Analytics 的 contextData 变量的名称。建议不要修改此设置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _db._contextNameCustom </td> 
   <td colname="col2"> 用于将自定义维度发送到 Adobe Analytics 的 contextData 变量的名称。建议不要修改此设置。 </td> 
  </tr> 
 </tbody> 
</table>

## 包含集成模块{#including-the-integrate-module}

集成代码要求 Adobe Analytics 部署中存在集成模块。

如果您的部署中尚不存在集成模块，请根据您的实施类型完成以下步骤。

### 对于 AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. 解压缩您从 **[!UICONTROL Analytics]** > **[!UICONTROL 管理员]** > **[!UICONTROL 代码管理器]**&#x200B;下载的 AppMeasurement zip 文件。

1. 打开名为 [!DNL AppMeasurement_Module_Integrate.js] 的文件。
1. 将此文件的内容复制并粘贴到 [!DNL AppMeasurement.js] 主文件中。

   >[!NOTE]
   >
   >将其粘贴到该文件中的“DO NOT ALTER ANYTHING BELOW THIS LINE”注释之前。

### 对于旧版代码 (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. 从 Data Connectors UI 中的“资源”区域（位于“支持”选项卡下）下载集成模块。

   ![](assets/h_code.png)

1. 将该文件的内容复制并粘贴到 [!DNL s_code] 文件中。

   >[!NOTE]
   >
   >将其粘贴到该文件中的“DO NOT ALTER ANYTHING BELOW THIS LINE”注释之前。

## 验证集成{#verifying-the-integration}

通过检查实时跟踪和报表，验证集成是否可成功捕获数据。

### 实时跟踪 {#section-9c20e8ff6b404ae09387ee07d675c9e2}

使用 DigitalPulse 调试器工具验证 Demandbase 维度数据是否会发送到 Adobe Analytics。删除 Cookie 后，在已部署集成代码的网站上重新加载一个页面。假定您的当前 IP 映射到 Demandbase 识别的组织，您应当看到类似于以下内容的结果。

**Reports &amp; Analytics（以前称为 SiteCatalyst）包括两个 Demandbase 上下文数据变量：**

![](assets/debugger1.png)

**Target Mbox 包括 Demandbase 配置文件参数：**
只有在页面上实施了 Target 并且为 Adobe Target 配置了此集成，您才会看到该内容 - 请参阅 Adobe 集成向导中的步骤 4。

![](assets/debugger2.png)

### 报表 {#section-1792fe75dc3249d0ad063dfd87a89162}

使用通过 Adobe 集成向导自动为您创建的功能板（步骤 7），查看 Adobe Analytics 中的 Demandbase 报表。

或者，您也可以导航到 Adobe Analytics 菜单结构中的 Demandbase 报表 - 请参阅以下屏幕快照。

>[!NOTE]
>
>此数据应会在成功部署后的 24-48 小时内显示。

![](assets/reporting1.png)

![](assets/reporting2.png)

### 常见问题解答 {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**“[n/a]”表示什么？**

Demandbase Data Connector 通过设置此默认值来指示属性何时“不可用”。设置默认值的常见情况有两种：

* Demandbase 检测到访客来自不属于某个公司的 IP 地址。
* 使用了“帐户监视”属性（以“watch_list”开头），但公司不在“帐户监视”列表中。

**为什么某些属性会更经常地显示“`[n/a]`”？**

Demandbase 将对所有 IP 地址进行分类，并提供 audience 和 audience_segment 属性，即使访客不来自公司 IP 也是如此。当 audience 返回“Residential”、“Wireless”和“Hospitality”等值时，其余属性可能不可用。

有时，访客的 audience 将为“SMB”，但其他属性将显示“`[n/a]`”。这意味着 Demandbase 能够将访客归类为小型企业，但无法获取完整的公司资料。规模最小的公司通常会发生这种情况，在这种情况下，多个小型企业使用相同的服务提供商或 IP 地址块。

### 开发人员注意事项 {#section-d33fff55bc4b4db99f82dee418ef1bc2}

如果需要调整实施中的默认值，请更新以下代码行：

```
_db._nonOrgMatchLabel = "[n/a]";
```
