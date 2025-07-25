---
description: Adobe Analytics 数据管理常见问题解答
title: 数据治理的常见问题解答
feature: Data Governance
role: Admin
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: ht
source-wordcount: '2042'
ht-degree: 100%

---

# 常见问题解答

+++ **Adobe Analytics 如何支持由最终用户（数据主体）提出、并由客户（数据控制者）进行验证的访问请求和删除请求？**

各种数据隐私法规 (GDPR、CCPA) 正式生效后，Adobe Analytics 将支持处理“数据控制者”向 Experience Cloud 数据隐私 API 提交的验证请求，以实现更加自动化的流程。针对我们的客户在各种 Adobe Experience Cloud 解决方案中存储的数据，Adobe 的数据隐私 API 旨在帮助处理个人权利请求（例如，访问和删除请求）。它具有灵活性和伸缩性，具体情况将依据贵公司从“数据主体”接收到的数据访问和删除请求数量。

此外，通过 Privacy Service API，客户还可检查关于如何履行访问和删除数据的请求的状态。有关更多详细信息，请参阅 [](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)Privacy Service API 文档。

+++

+++ **谁将负责接收、接受和执行来自最终用户的数据隐私请求？**

数据控制者全权负责接收和接受请求。数据控制者验证数据主体的身份标识，然后满足请求。此责任的一部分可能涉及使用可能与存储在 Adobe Analytics 中的数据相关联的数据主体 ID 联系 Adobe。

作为“数据处理者”，Adobe 必须向控制者提供合理的帮助，以便在可接受的时间范围内处理已验证的请求。

+++

+++ **为了进行数据隐私处理，Adobe 客户（数据控制者）将如何找出哪些数据隐私请求映射到 Adobe Analytics 中的哪些 ID？**

数据控制者确定如何解析发出请求的“数据主体”的身份标识。可以考虑部署 Adobe 的数据隐私 ID 检索标记。您的开发团队通过使用我们的数据隐私 ID 检索标记来捕获用户 ID (Cookie ID) 来节省时间。然后，他们可以使用我们的数据隐私 API 将这些用户 ID 发送到 Adobe Experience Cloud 中的相关解决方案，以进行数据隐私请求处理。数据隐私 API 可以在多个 Adobe 解决方案中支持范围广泛的客户 ID。

如果数据主体提交了一个请求和一个标识符（自定义变量 – prop 或 eVar），Adobe Analytics 则会扫描为给定标识符收集的完全保留的数据历史记录。有关如何配置存储在 Analytics prop 或 eVar 中的自定义 ID 的详细信息，请参阅 [Analytics 关于命名空间的文档](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md)。

+++

+++ **Adobe Analytics 数据管理怎样协助处理数据隐私请求？**

“数据管理”是 Adobe Analytics 中的一个新工具，它赋与数据控制者在其 Analytics 数据中应用数据控制和分类的能力。这款新工具允许 Adobe 客户自定义其数据隐私数据访问和数据删除请求的处理方式。在“数据管理”控制台中，管理员可以定义多种所需的设置，这些设置应该会应用于 Adobe Analytics 的各种数据列中。一旦定义了这些标签，Adobe 将根据客户所需的标签设置，执行并处理任何下游访问或删除请求。数据控制者有责任进行审查，并就这些标签设置与其法律代表进行协商。

“数据管理”工具包含以下数据标签：

* **身份标识数据标签**：用于对可以直接识别个人或与其他数据结合使用以识别个人的数据进行分类。（无、I1、I2）

* **敏感数据标签**：用于按照适用的法律，对定义为敏感数据的数据进行分类。（无、S1、S2）请注意，当前通常禁止在 Adobe Analytics 中使用敏感数据，但是根据适用法律正确获得的精确地理位置数据除外，不过在某些司法辖区，这类数据可能会被视为敏感数据。

* **数据隐私数据标签**：用于对以下字段进行定义：包含数据隐私请求中使用的个人标识符的字段，或者，作为数据隐私删除请求的一部分而应该删除的字段。在某些情况下，这些标签可能会与身份标识和敏感数据标签重叠。

有关“数据管理”标签的更多信息，请参阅 [Analytics 变量的数据隐私标签](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md)。

+++

+++ **我如何验证隐私服务请求是否运行正常以从 Adobe Analytics 中删除数据？**

通常情况下，在向公众发布之前，Analytics 客户会设置一些测试报告包来验证功能。预生产网站或应用程序将数据发送到这些测试/开发/QA 报告包中，以评估在将实际流量发送到生产报告包之前代码完成时的运行情况。

但是，在正常配置下，在将请求应用到生产报告包之前，不能先在这些测试报告包上对 GPDR 请求的处理进行测试。这是因为数据隐私请求会自动应用于 Experience Cloud 组织中的所有报告包，通常也是您公司的所有报告包。

在将数据隐私请求应用于所有报告包之前，您仍可以使用以下几种方法测试您的数据隐私处理：

* 一种选择是，设置一个单独的 Experience Cloud 组织，其中仅包含测试报告包。然后，使用此 Experience Cloud 组织进行数据隐私测试，并使用常规的 Experience Cloud 组织进行实际的数据隐私处理。

* 另一种选择是，为测试报告包中的 ID 分配与生产报告包中的 ID 不同的命名空间。例如，您可以在测试报告包中为每个命名空间添加“qa-”作为前缀。当您提交仅带有 qa 前缀的命名空间的数据隐私请求时，这些请求将仅针对您的测试报告包运行。之后，当您提交不带 qa 前缀的请求时，它们将应用于您的生产报告包。**推荐使用此方法，除非您使用 visitorId、AAID、ECID 或 customVisitorId 命名空间。 这些命名空间经硬编码，无法在测试报告包中为其指定替代名称。**

+++

+++ **我该从哪里开始着手准备 Adobe Analytics 以支持数据隐私法？**

有关为数据隐私做好准备的分步说明，请参阅[ Adobe Analytics 数据隐私工作流程](/help/admin/admin/c-data-governance/an-gdpr-workflow.md)。

+++

+++ **当涉及到用户参与时，数据控制者应该如何考虑同意管理？**

GDPR 和 CCPA 是重新考虑您的同意管理策略和实践的好机会。这包括确定何时需要同意并考虑用户的价值主张。考虑消费者隐私的价值定位，这有助于推动转化以及提高忠诚度。同意管理领域（例如，工具、标准、最佳实践）正在快速发展，这是一个需要密切观察的领域。为了最大限度地减少对用户参与的影响，控制者应该与此领域内的供应商及其法律顾问合作，确保他们遵守有关同意和 Cookie 的新法律和指南。利用基于品牌、与上下文相关的经验来思考“体验式隐私”是一种很好的策略，这些经验清晰而有条理地阐明了数据收集活动的价值定位。

作为数据控制者，您有责任在收集与数据主体相关的数据（可能包括 Adobe Analytics 数据）之前获得他们的明确同意，并且有责任在您的网站上实施[选择退出机制](https://www.adobe.com/cn/privacy/opt-out.html#customeruse)。该机制允许您的数据主体退出以后的 Adobe Experience Cloud 数据收集。

+++

+++ **当涉及到数据隐私时，数据控制者应该如何考虑数据保留？**

通常，个人数据的保留时间不应超过为实现收集目的所需的时间。Adobe 的一般条款适用默认的 25 个月数据保留计划，除非在合同中约定了不同的数据保留期限。客户需要先设置其数据保留策略，然后 Adobe 才可以处理数据隐私请求。

每个报告包的当前数据保留策略都显示在新的数据管理管理员 UI 中。如果客户需要调整其数据保留策略，则应联系其 Adobe 代表。请参阅 [Adobe Analytics 数据保留常见问题解答](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=zh-Hans)。

+++

+++ **客户能否缩短或延长默认的数据保留期限？**

客户可通过致电客户关怀，请求在 25 个月之内删除他们的数据。此外，客户还可以通过付费，将数据保留期限延长到 25 个月以后。我们提供的延长期以 1 年为单位，按年递增，最多可额外购买 8 年，这样数据总计最多可保留十年（共 10 年）。延长保留期会涉及更新合同条款并需要支付额外费用。

+++

+++ **从 Adobe Analytics 导出个人数据时，数据控制者应该考虑哪些隐私问题？**

如果客户使用 Adobe Analytics 数据馈送，将数据从 Analytics 导出到其企业数据仓库或 Adobe 以外的其他系统，则客户（数据控制者）有责任确保对数据应用删除请求。这同样适用于 Adobe Data Workbench 的内部部署实施，当前，持续进行的 Adobe Analytics 数据馈送正在填充 Data Workbench 数据。 Adobe 会提供一些辅助工具来查找并删除某些类型的数据馈送，其中包括用于 Data Workbench 的数据馈送，但是客户（数据控制者）仍要负责确保删除的数据符合其内部的数据保留和删除策略。

另外，还需要考虑员工已经下载了包含个人数据的 Adobe Analytics 报告的情况。如果收到了与数据隐私相关的删除请求中涉及报告内存在的 ID，则需要更新或删除这些报告。客户应当与自己公司的法律顾问合作，确定保留期以及应用于这些类型文档的隐私和安全要求。

+++

+++ **我们意外将一些不应该收集的数据发送到了 Adobe Analytics。是否可以使用数据隐私 API 来清理此类数据？**

提供[数据 Privacy Service API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 是为了帮助您执行对时间敏感的数据隐私请求。Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起数据隐私请求的能力。

我们建议您不要将数据隐私 API 用于其他目的，例如清除大量访客意外提交的数据。您还应该了解，对于任何因提交数据隐私删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问次数、反向链接、访问的第一个页面等信息也都将重新统计。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了数据隐私 API 不适合此用途的一个原因。

请联系您的 Adobe 帐户团队与我们的工程架构师咨询团队进行协调，以进一步审查并努力解决任何 PII 或数据问题。

+++

+++ **我们的法律团队已经确定我们多年来一直在变量中收集的值，不再符合我们更新的隐私政策。我们是否可以使用数据隐私 API 清除此变量中的所有值？**

提供[数据 Privacy Service API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) 是为了帮助您执行对时间敏感的数据隐私请求。 Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起数据隐私请求的能力。我们建议您不要将数据隐私 API 用于其他目的，例如清除大量访客意外提交的数据。

您还应该了解，对于任何因提交数据隐私删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问次数、反向链接、访问的第一个页面等信息也都将重新统计。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了数据隐私 API 不适合此用途的一个原因。

请联系您的 Adobe 帐户团队与我们的工程架构师咨询团队进行协调，以进一步审查并努力解决任何 PII 或数据问题。

+++

其他数据隐私资源：

* [GDPR 常用术语](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud 数据隐私[保护包](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 体验式隐私[博客文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
