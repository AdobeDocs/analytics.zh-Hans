---
description: 您可以通过选择预定义的模板或者使用某个现有报表包作为模型，来创建新的报表包。
title: 新报表包 — 设置
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
TQID: https://experienceleague.adobe.com/9wZ2rIgzZtJduhFAx6XcD53H2qzB2SZMr0pbxCopBvk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: f52db89b-2666-4cad-9c50-9da4d3ffcfd0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 541
ht-degree: 73%

---

# 新报表包 — 设置

您可以通过选择预定义的模板或者使用某个现有报表包作为模型，来创建新的报表包。

[创建报表包时](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md)使用的元素的描述。

>[!NOTE]
>
>[虚拟报表包文档](/help/components/vrs/c-workflow-vrs/vrs-create.md)说明了如何创建虚拟报表包。

| 元素 | 描述 |
| --- | --- |
| 报表包 ID | 指定只能包含字母数字字符的唯一ID。 此ID在创建后无法更改。 Adobe 会设置所需的 ID 前缀，该前缀也无法更改。  在创建多个报表包时，请确保使用命名规则获得唯一的报表包 ID。 |
| 网站标题 | 在管理工具中标识报表包。 此标题还可在包标头中的报表包下拉列表中使用。 |
| 时区 | 计划事件和时间戳数据。 |
| 基本 URL | （可选）定义报表包的基本域。 如果您没有明确定义报表包的内部URL过滤器，此URL将用作内部URL过滤器。 |
| 默认页面 | （可选）将默认页面值的发生次数从它遇到的 URL 中剥离开来。 如果最受欢迎页面报表包含 URL 而不是页面名称，则此设置可以防止同一网页有多个 URL。  例如，URL `https://example.com` 和 `https://example.com/index.html` 通常是同一页面。<p> 可移除不相干的文件名，以使这两个 URL 在您的报表中都显示为 `https://example.com` 。 如果不设置此值，Analytics 将从 URL 中自动移除以下文件名：`index.htm`、`index.html`、`index.cgi`、`index.asp`、`default.htm`、`default.html`、`default.cgi`、`default.asp`、`home.htm`、`home.html`、`home.cgi` 和 `home.asp`。 要禁用文件名去除，请指定一个绝不会出现在URL中的“默认页面”值。 |
| 上线日期 | 通知Adobe您希望此报表包生效的日期。 如果您的部署计划有更改，请使用流量管理中的永久性预期流量工具提供更新的流量预估。 |
| 估计每天页面查看次数 | 标识您希望此报表包在一天内支持的页面查看估计次数。 大流量需要较长的批准流程。 为避免处理延迟，请尽可能准确地使用此估计值。 |
| 基本货币 | 指定用于存储所有货币数据的默认货币。 Analytics 报表可以使用收到数据时的最新货币兑换率，将使用其他货币进行的交易转换为基本货币。 Analytics 报表使用 currencyCode JavaScript 变量确定给定交易的货币。 |
| 启用日语关键词处理 | 为报表包启用多字节字符支持。 如果禁用多字节字符支持，则系统会假定数据为 `ISO-8859-1` 格式。 页面必须在 charSet JavaScript 变量中指定其字符集。 <p>多字节字符支持使用 UTF-8 将字符存储在报表包中。 系统在接收数据之后会将其从您的网页字符集转换为 UTF-8 字符集，从而使您可以在市场营销报告中使用任何语言。  要将现有报表包更改为支持多字节字符，请联系您的 Adobe 客户团队或客户关怀团队。 |
| 使用简化的导航菜单 | 此功能是[Reports &amp; Analytics](https://new.express.adobe.com/webpage/WFCyq7w8kijmB？)的一部分，不再受支持。 |

{style="table-layout:auto"}
