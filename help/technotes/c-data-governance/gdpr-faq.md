---
description: Adobe Analytics 数据管理常见问题解答
title: 数据治理的常见问题解答
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: e26e04e965554f0e9e7f06f0129175f1d24a3f23
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 常见问题解答

+++ **Adobe Analytics 如何支持由最终用户（数据主体）提出、并由客户（数据控制者）进行验证的访问请求和删除请求？**

各种数据隐私法规 (GDPR、CCPA) 正式生效后，Adobe Analytics 将支持处理“数据控制者”向 Experience Cloud 数据隐私 API 提交的验证请求，以实现更加自动化的流程。针对我们的客户在各种 Adobe Experience Cloud 解决方案中存储的数据，Adobe 的数据隐私 API 旨在帮助处理个人权利请求（例如，访问和删除请求）。它灵活且可根据贵公司从数据主体收到的数据访问和删除请求的数量进行扩展。

此外，Privacy ServiceAPI允许客户检查有关如何执行数据访问和删除请求的状态。 有关更多详细信息，请参阅 [](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)Privacy Service API 文档。

+++

+++ **谁将负责接收、接受和执行来自最终用户的数据隐私请求？**

数据控制者负责接收和接受请求。 数据控制者验证数据主体的身份，然后满足请求。 部分责任可能涉及使用数据主体的ID联系Adobe，这些ID可能与存储在Adobe Analytics中的数据关联。

作为数据处理者，Adobe必须向控制者提供合理的帮助，以在可接受的时间内处理已验证的请求。

+++

+++ **为了进行数据隐私处理，Adobe 客户（数据控制者）将如何找出哪些数据隐私请求映射到 Adobe Analytics 中的哪些 ID？**

数据控制者确定如何为来自数据主体的请求解析身份。 可以考虑部署 Adobe 的数据隐私 ID 检索标记。您的开发团队可通过使用我们的数据隐私ID检索标记捕获用户ID(Cookie ID)来节省时间。 然后，他们可以使用我们的数据隐私API将这些用户ID发送到Adobe Experience Cloud中的相关解决方案，以进行数据隐私请求处理。 数据隐私 API 可以在多个 Adobe 解决方案中支持范围广泛的客户 ID。

如果数据主体提交了请求以及标识符(自定义变量 — prop或eVar)，则Adobe Analytics会扫描针对给定标识符收集的数据的整个保留历史记录。 有关如何配置存储在 Analytics prop 或 eVar 中的自定义 ID 的详细信息，请参阅 [Analytics 关于命名空间的文档](/help/technotes/c-data-governance/data-labeling/gdpr-namespaces.md)。

+++

+++ **Adobe Analytics 数据管理怎样协助处理数据隐私请求？**

“数据管理”是Adobe Analytics中的一个新工具，它使“数据控制者”能够在其Analytics数据中应用数据控制和分类。 这款新工具允许 Adobe 客户自定义其数据隐私数据访问和数据删除请求的处理方式。在“数据管理”控制台中，管理员可以定义多种所需的设置，这些设置应该会应用于 Adobe Analytics 的各种数据列中。一旦定义了这些标签，Adobe 将根据客户所需的标签设置，执行并处理任何下游访问或删除请求。数据控制者有责任审查这些标签设置并与其法律代表进行协商。

“数据管理”工具包含以下数据标签：

* **身份数据标签**:用于对可以直接识别个人或与其他数据结合使用以识别个人的数据进行分类。 （无、I1、I2）

* **敏感数据标签**:用于根据适用的法律，对定义为敏感数据的数据进行分类。 （无、S1、S2）请注意，当前通常禁止在 Adobe Analytics 中使用敏感数据，但是根据适用法律正确获得的精确地理位置数据除外，不过在某些司法辖区，这类数据可能会被视为敏感数据。

* **数据隐私数据标签**:用于定义可能包含用于数据隐私请求的个人标识符的字段，或者定义应作为数据隐私删除请求的一部分删除的字段。 在某些情况下，这些标签可能会与身份和敏感数据标签重叠。

有关“数据管理”标签的更多信息，请参阅 [Analytics 变量的数据隐私标签](/help/technotes/c-data-governance/data-labeling/gdpr-labels.md)。

+++

+++ **如何验证Privacy Service请求是否正常运行以从Adobe Analytics中删除数据？**

通常情况下，在向公众发布之前，Analytics 客户会设置一些测试报告包来验证功能。 预生产网站或应用程序会将数据发送到这些测试/开发/QA报表包，以评估在将实际流量发送到生产报表包之前释放代码时工作情况。

但是，在正常配置下，在将请求应用到生产报告包之前，不能先在这些测试报告包上对 GPDR 请求的处理进行测试。这是因为数据隐私请求会自动应用于Experience Cloud组织中的所有报表包，通常是您公司的所有报表包。

但是，在将数据隐私处理应用于所有报表包之前，您仍可以通过以下几种方法对其进行测试：

* 一种选择是，设置一个单独的 Experience Cloud 组织，其中仅包含测试报告包。然后，使用此 Experience Cloud 组织进行数据隐私测试，并使用常规的 Experience Cloud 组织进行实际的数据隐私处理。

* 另一种选择是，为测试报告包中的 ID 分配与生产报告包中的 ID 不同的命名空间。例如，您可以在测试报告包中为每个命名空间添加“qa-”作为前缀。当您提交仅带有 qa 前缀的命名空间的数据隐私请求时，这些请求将仅针对您的测试报告包运行。之后，当您提交不带 qa 前缀的请求时，它们将应用于您的生产报告包。**推荐使用此方法，除非您使用 visitorId、AAID、ECID 或 customVisitorId 命名空间。 这些命名空间经硬编码，无法在测试报告包中为其指定替代名称。**

+++

+++ **我该从哪里开始着手准备 Adobe Analytics 以支持数据隐私法？**

有关为数据隐私做好准备的分步说明，请参阅[ Adobe Analytics 数据隐私工作流程](/help/technotes/c-data-governance/an-gdpr-workflow.md)。

+++

+++ **当涉及到用户参与时，数据控制者应该如何考虑同意？**

GDPR和CCPA是重新考虑您的同意管理策略和惯例的好机会。 这包括确定何时需要同意并考虑用户的价值主张。 考虑消费者隐私的价值定位，这有助于推动转化以及提高忠诚度。同意管理领域（例如，工具、标准、最佳实践）正在快速发展，这是一个需要密切观察的领域。为了最大限度地减少对用户参与度的影响，控制者应与此领域的供应商及其法律顾问合作，以确保他们遵循关于同意和Cookie的新法律和指导。 利用基于品牌、与上下文相关的经验来思考“体验式隐私”是一种很好的策略，这些经验清晰而有条理地阐明了数据收集活动的价值定位。

作为数据控制者，您有责任在收集与数据主体相关的数据(可能包括Adobe Analytics数据)之前获得他们的明确同意，并且有责任实施 [选择退出机制](https://www.adobe.com/cn/privacy/opt-out.html#customeruse) 在您的网站上。 这允许您的数据主体选择退出将来的Adobe Experience Cloud数据收集。

+++

+++ **当涉及到数据隐私时，数据控制者应该如何考虑数据保留？**

个人数据通常不应保留超过达到收集目的所需的时间。 Adobe的一般条款适用默认的25个月数据保留计划，除非按照合同约定，另有数据保留期限。 客户需要先设置其数据保留策略，然后Adobe才能处理数据隐私请求。

每个报告包的当前数据保留策略都显示在新的数据管理管理员 UI 中。如果客户需要调整其数据保留策略，则应联系其Adobe代表。 请参阅 [Adobe Analytics数据保留常见问题解答](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=zh-Hans).

+++

+++ **客户能否缩短或延长默认数据保留期？**

客户可通过致电客户关怀，要求在25个月内删除其数据。 此外，客户还可以通过付费，将数据保留期限延长到 25 个月以后。我们提供的延长期以1年为增量，最多可额外购买8年（总计10年）。 延长这些期限将需要更新合同条款并支付额外费用。

+++

+++ **从 Adobe Analytics 导出个人数据时，数据控制者应该考虑哪些隐私问题？**

如果客户使用 Adobe Analytics 数据馈送，将数据从 Analytics 导出到其企业数据仓库或 Adobe 以外的其他系统，则客户（数据控制者）有责任确保对数据应用删除请求。这同样适用于 Adobe Data Workbench 的内部部署实施，当前，持续进行的 Adobe Analytics 数据馈送正在填充 Data Workbench 数据。 Adobe 会提供一些辅助工具来查找并删除某些类型的数据馈送，其中包括用于 Data Workbench 的数据馈送，但是客户（数据控制者）仍要负责确保删除的数据符合其内部的数据保留和删除策略。

此外，还请考虑员工已下载包含个人数据的Adobe Analytics报表的情况。 如果收到与数据隐私相关的删除请求时涉及报表中存在的ID，则可能需要更新或删除这些报表。 客户应与自己公司的法律顾问合作，确定保留期限以及应应用于这些类型文档的隐私和安全要求。

+++

+++ **我们意外将一些不应该收集的数据发送到了 Adobe Analytics。我们能否使用数据隐私API来清理此数据？**

提供[数据 Privacy Service API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 是为了帮助您执行对时间敏感的数据隐私请求。 Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起数据隐私请求的能力。

我们建议您不要将数据隐私 API 用于其他目的，例如清除大量访客意外提交的数据。您还应该了解，对于任何因提交数据隐私删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问次数、反向链接、访问的第一个页面等信息也都将重新统计。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了数据隐私 API 不适合此用途的一个原因。

请联系您的客户经理 (CSM) 来与我们的工程架构师咨询团队进行协调，以进一步审查并提供解决任何 PII 或数据问题的帮助。

+++

+++ **我们的法律团队已确定我们多年来一直在变量中收集的值不再符合我们更新的隐私政策。 我们是否可以使用数据隐私 API 清除此变量中的所有值？**

提供[数据 Privacy Service API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 是为了帮助您执行对时间敏感的数据隐私请求。 Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起数据隐私请求的能力。我们建议您不要将数据隐私 API 用于其他目的，例如清除大量访客意外提交的数据。

您还应该了解，对于任何因提交数据隐私删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问次数、反向链接、访问的第一个页面等信息也都将重新统计。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了数据隐私 API 不适合此用途的一个原因。

请联系您的客户经理 (CSM) 以与我们的工程架构师咨询团队进行协调，以进行进一步审查并提供解决任何 PII 或数据问题的帮助。

+++

其他数据隐私资源：

* [GDPR 常用术语](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud 数据隐私[保护包](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 体验式隐私[博客文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
