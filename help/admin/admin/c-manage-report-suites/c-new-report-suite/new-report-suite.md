---
description: 您可以通过选择预定义的模板或者使用某个现有报表包作为模型，来创建新的报表包。
title: 新报表包 — 设置
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 100%

---

# 新报表包 — 设置

您可以通过选择预定义的模板或者使用某个现有报表包作为模型，来创建新的报表包。

[创建报表包时](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)使用的元素的描述。

>[!NOTE]
>
>[虚拟报表包文档](/help/components/vrs/c-workflow-vrs/vrs-create.md)说明了如何创建虚拟报表包。

| 元素 | 描述 |
| --- | --- |
| 报表包 ID | 指定一个唯一 ID，其中仅可包含字母数字字符。此 ID 一经创建，即无法更改。Adobe 会设置所需的 ID 前缀，该前缀也无法更改。在创建多个报表包时，请确保使用命名规则获得唯一的报表包 ID。 |
| 网站标题 | 在管理工具中标识报表包。此标题还可在包标头中的报表包下拉列表中使用。 |
| 时区 | 计划事件和时间戳数据。 |
| 基本 URL | （可选）定义报表包的基本域。如果没有为报表包明确定义内部 URL 过滤器，那么此 URL 将作为内部 URL 过滤器使用。 |
| 默认页面 | （可选）将默认页面值的发生次数从它遇到的 URL 中剥离开来。如果最受欢迎页面报表包含 URL 而不是页面名称，则此设置可以防止同一网页有多个 URL。例如，URL `https://example.com` 和 `https://example.com/index.html` 通常是同一页面。<p> 可移除不相干的文件名，以使这两个 URL 在您的报表中都显示为 `https://example.com` 。如果不设置此值，Analytics 将从 URL 中自动移除以下文件名：`index.htm`、`index.html`、`index.cgi`、`index.asp`、`default.htm`、`default.html`、`default.cgi`、`default.asp`、`home.htm`、`home.html`、`home.cgi` 和 `home.asp`。 要禁止剥离文件名，可以输入永远不会在您的 URL 中出现的默认页面值。 |
| 起始日期 | 通知 Adobe 您希望此报表包变为活动状态的日期。如果您的部署计划有更改，请使用流量管理中的永久性预期流量工具提供更新的流量预估。 |
| 估计每天页面查看次数 | 确定您预计此报表包在一天内支持的估计页面查看次数。大流量需要的批准过程较长。为避免处理延迟，请尽量确保此估计值的准确性。 |
| 基本货币 | 指定用于存储所有货币数据的默认货币。Analytics 报表可以使用收到数据时的最新货币兑换率，将使用其他货币进行的交易转换为基本货币。Analytics 报表使用 currencyCode JavaScript 变量确定给定交易的货币。 |
| 禁用多字节字符支持 | 禁用对报表包的多字节字符支持。如果禁用多字节字符支持，则系统会假定数据为 `ISO-8859-1` 格式。 页面必须在 charSet JavaScript 变量中指定其字符集。 <p>多字节字符支持使用 UTF-8 将字符存储在报表包中。系统在接收数据之后会将其从您的网页字符集转换为 UTF-8 字符集，从而使您可以在市场营销报告中使用任何语言。要将现有报表包更改为支持多字节字符，请联系您的 Adobe 客户团队或客户关怀团队。 |

{style="table-layout:auto"}
