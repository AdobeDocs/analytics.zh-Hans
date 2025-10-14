---
description: 了解如何报告来自人工智能聊天机器人的流量
title: 分析来自AI聊天机器人的流量
feature: Metrics, Data Configuration and Collection
source-git-commit: d16214865a037efe41b9f95682758daa577a12ed
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

---

# 分析来自对话式人工智能工具的流量

Adobe Analytics提供了用于分析您网站上的AI流量的工具。

在分析AI流量时，您首先需要了解可以发生的AI流量类型以及哪些类型会生成点击。 然后，您可以在Analysis Workspace中分析流量。

## 了解AI流量

### 了解AI流量的类型

您网站上的AI流量可能会在以下任何情况下发生：

* **在预培训期间**：当网站中的内容被刮取并引入到AI培训数据中时，不常发生。

* **响应按需提示时**：在用户提示人工智能提出问题并且AI聊天机器人响应时发生。 AI聊天机器人执行Web搜索，您网站中的内容包含在响应中。 (此类交互有时称为检索增强型生成(RAG)。)

  某些AI聊天机器人响应包含指向您网站上源材料的链接，而另一些则没有。

* **执行代理工作流时**：当AI代理在浏览器中点击一系列网页以响应用户请求时访问您的网站时发生。 在这种情况下，AI将充当发出请求的用户的代理。

### 了解何时为AI流量生成点击

在页面上执行JavaScript时，会在网页上生成点击。 根据网站上发生的AI流量类型，可能会执行JavaScript，也可能不执行。

| AI流量类型 | 生成点击 | 注意事项 |
|---------|----------|---------|
| **预培训** | 是 | 将网站中的内容引入到AI中时，会在预培训期间生成点击。 但是，预培训并不经常发生，并且包含在AI预培训中的内容可以在未来的响应中重复使用，而无需在网站上生成进一步的点击。 <p>换言之，在AI预培训期间发生的单个点击可以重复用于多个按需响应，而不会在您的网站上生成其他点击。</p><p>有关如何在Analysis Workspace中分析此类AI流量的信息，请参阅[使用机器人检测分析AI流量](#analyze-ai-traffic-using-bot-detection)。</p> |
| **按需提示** | 否 | AI响应不会生成任何点击，因为此响应使用以下项的组合：<ul><li>经过预训练的数据<br/>信息已包含在AI的经过预训练的知识中，因此AI不会在页面上执行JavaScript。</li><li>On-demand Web Search <br/>在Web搜索期间仅获取网页的原始HTML，因此AI不会在页面上执行JavaScript。</li></ul> |
| AI响应中的&#x200B;**Source材料链接** | 是 | 当用户单击指向AI响应中包含的源资料的链接时，会生成点击。 如果响应中包含链接且用户未单击该链接，则不会生成点击。 <p>有些AI聊天机器人响应包含指向源材料的链接，而另一些则没有。 </p><p>有关如何在Analysis Workspace中分析此类型的AI流量的信息，请参阅[按反向链接类型分析AI流量](#analyze-ai-traffic-by-referrer-type)。</p> |
| **代理工作流** | 是 | 当AI代理代表用户通过工作流进行点击时，将在每个页面上生成点击。 <p>有关如何在Analysis Workspace中分析此类型的AI流量的信息，请参阅[按反向链接类型分析AI流量](#analyze-ai-traffic-by-referrer-type)。</p> |

## 在Analysis Workspace中分析AI流量

### 按反向链接类型分析AI流量

您可以使用Analysis Workspace中的反向链接类型维度来分析以下类型的AI流量：

* AI响应中的Source材料链接

* 代理工作流

反向链接类型维度包括[对话AI工具维度项](/help/components/dimensions/referrer-type.md#conversational-ai-tools)。 此维度项包括预定义的AI聊天机器人列表。

有关详细信息，请参阅[反向链接类型](/help/components/dimensions/referrer-type.md)。

### 使用机器人检测分析AI流量

您可以使用Analysis Workspace中的机器人检测来分析来自预训练的AI流量。

