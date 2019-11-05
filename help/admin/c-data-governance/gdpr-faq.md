---
description: 'null'
seo-description: 'null'
seo-title: 常见问题解答
title: 常见问题解答
uuid: 1cd41253-d74f-4b92-92e6-56f9afa3df85
translation-type: tm+mt
source-git-commit: 657b4ac4bd8ef0092ea76c6ce20133dab875da0d

---


# 常见问题解答

<table id="table_FA37A4B3960C4181B9CCDB569A476936"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 问题 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics 如何支持由最终用户（数据主体）提出、并由客户（数据控制者）进行验证的访问请求和删除请求？</b> </p> </td> 
   <td colname="col2"> <p>各种数据隐私法规 (GDPR、CCPA) 正式生效后，Adobe Analytics 将支持处理“数据控制者”向 Experience Cloud 数据隐私 API 提交的验证请求，以实现更加自动化的流程。针对我们的客户在各种 Adobe Experience Cloud 解决方案中存储的数据，Adobe 的数据隐私 API 旨在帮助处理个人权利请求（例如，访问和删除请求）。它具有灵活性和伸缩性，具体情况将依据贵公司从数据主体接收到的数据访问和删除请求数量。此外，数据隐私 API 允许客户检查有关执行数据访问和删除请求的进展状态。 </p> <p>For more details see <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html"> Data Privacy API documentation. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>谁将负责接收、接受和执行来自最终用户的数据隐私请求？</b> </p> </td> 
   <td colname="col2"> <p>“数据控制者”（例如 Adobe 客户）全权负责向数据主体提供个人数据，以回应符合数据隐私法的个人权利请求。另外，“数据控制者”还负责接收和接受请求，即验证数据主体的身份并执行请求，在这个过程中，可能会涉及到使用数据主体的 ID 联系 Adobe，这些 ID 可能与存储在 Adobe Analytics 中的数据关联。作为“数据处理者”，Adobe 必须向控制者提供合理的帮助，以便在可接受的时间范围内处理已验证的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>为了进行数据隐私处理，Adobe 客户（数据控制者）将如何找出哪些数据隐私请求映射到 Adobe Analytics 中的哪些 ID？</b> </p> </td> 
   <td colname="col2"> <p>数据控制者将确定如何解析发出请求的数据主体的身份。可以考虑部署 <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm">Adobe 的数据隐私 ID 检索标记。</a>为了节省时间，您的开发团队可采用下面的方法：使用我们的数据隐私 ID 检索标记捕获用户 ID (Cookie ID)，然后用我们的数据隐私 API 将这些用户 ID 发送到 Adobe Experience Cloud 的相关解决方案中，以进行数据隐私请求处理。 </p> <p>数据隐私 API 可以在多个 Adobe 解决方案中支持范围广泛的客户 ID。如果数据主体提交了一个请求和一个标识符（自定义变量 – prop 或 eVar），Adobe Analytics 则会扫描针对给定标识符收集的所有保留的数据历史记录。For more details about how to configure custom IDs stored in Analytics props or eVars, please refer to the Analytics documentation on <a href="/help/admin/c-data-governance/gdpr-namespaces.md"> Namespaces.</a>
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics 数据管理怎样协助处理数据隐私请求？</b> </p> </td> 
   <td colname="col2"> <p>“数据管理”是 Adobe Analytics 中的一个新工具，它赋与数据控制者在其 Analytics 数据中应用数据控制和分类的能力。这款新工具允许 Adobe 客户自定义其数据隐私数据访问和数据删除请求的处理方式。在“数据管理”控制台中，管理员可以定义多种所需的设置，这些设置应该会应用于 Adobe Analytics 的各种数据列中。一旦定义了这些标签，Adobe 将根据客户所需的标签设置，执行并处理任何下游访问或删除请求。数据控制者有责任进行审查，并就这些标签设置与其法律代表进行协商。Adobe Analytics 鼓励客户于 2018 年 5 月 25 日 GDPR 正式生效之前，在客户端上正确设置数据标签功能，以便允许利用数据隐私 API 自定义请求的完成情况。 </p> <p>“数据管理”工具包含以下数据标签： </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels"> 标识数据标签：用 </a> 于对能够直接识别个人或与其他数据组合识别个人的数据进行分类。 （无、I1、I2） </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels"> 敏感数据标签：用 </a> 于将数据分类为根据适用法律定义为敏感的数据。 （无、S1、S2）请注意，当前通常禁止在 Adobe Analytics 中使用敏感数据，但是根据适用法律正确获得的精确地理位置数据除外，不过在某些司法辖区，这类数据可能会被视为敏感数据。 </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels"> 数据隐私数据标签：用 </a> 于定义可能包含个人标识符的字段，以用于数据隐私请求或应作为数据隐私删除请求的一部分删除的字段。 在某些情况下，这些标签可能会与身份和敏感数据标签重叠。 </li> 
    </ul> <p>For more information on Data Governance labels, see <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels"> Data Privacy Labels for Analytics Variables. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>我该从哪里开始着手准备 Adobe Analytics 以支持数据隐私法？</b> </p> </td> 
   <td colname="col2"> <p>For a step-by-step walkthrough to get ready for Data Privacy rules, see <a href="/help/admin/c-data-governance/an-gdpr-workflow.md"> Adobe Analytics Data Privacy Workflow. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>当涉及到用户参与时，数据控制者应该如何考虑同意管理？</b> </p> </td> 
   <td colname="col2"> <p>GDPR 和 CCPA 是重新考虑您的同意管理策略及惯例的好机会，包括确定何时需要同意并考虑针对用户的价值定位。考虑消费者隐私的价值定位，这有助于推动转化以及提高忠诚度。 </p> <p>同意管理领域（例如，工具、标准、最佳实践）正在快速发展，这是一个需要密切观察的领域。为了最大限度地减少对用户参与的影响，控制者应该与此领域内的供应商及其法律顾问合作，遵循新颁布的欧盟法规以及有关同意和 Cookie 的指导。利用基于品牌、与上下文相关的经验来思考“体验式隐私”是一种很好的策略，这些经验清晰而有条理地阐明了数据收集活动的价值定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>当涉及到数据隐私时，数据控制者应该如何考虑数据保留？</b> </p> </td> 
   <td colname="col2"> <p>通常，数据隐私法规定个人数据的保留时间不应超过为实现收集目的所需的时间。 </p> <p>正如 Adobe 在 2 月份客户沟通会上详细阐明的那样，除非已对客户履行了其他安排（根据客户的通知和授权），否则我们将为大多数客户实施 25 个月的数据保留计划。客户需要先设置其数据保留策略，然后 Adobe 才可以处理数据隐私请求。 </p> <p>Adobe Analytics 要求客户设置其数据保留策略以处理其数据隐私请求。每个报表包的当前数据保留策略都显示在新的数据管理管理员 UI 中。如果客户需要调整其数据保留策略，则应联系其 Adobe 代表。Please, refer to <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html"> Adobe Analytics Data Retention FAQS. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>客户能否缩短或延长默认的数据保留期限？</b> </p> </td> 
   <td colname="col2"> <p>客户可通过致电客户关怀，请求在 25 个月之内删除他们的数据。客户还可以通过购买延期服务，将数据保留期限延长到 25 个月以后。</p><p>
   我们提供的延长期以 1（一）年为单位，按年递增，最多可额外购买 8（八）年，这样数据总计最多可保留十年。延长保留期可能会涉及更新合同条款并需要支付额外费用。
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>从 Adobe Analytics 导出个人数据时，数据控制者应该考虑哪些隐私问题？</b> </p> </td> 
   <td colname="col2"> <p>如果客户使用 Adobe Analytics 数据馈送，将数据从 Analytics 导出到其企业数据仓库或 Adobe 以外的其他系统，则客户（数据控制者）有责任确保对数据应用删除请求。这同样适用于 Adobe Data Workbench (Insight) 的内部部署实施，当前，持续进行的 Adobe Analytics 数据馈送正在填充 Data Workbench 数据。Adobe 会提供一些辅助工具来查找并删除某些类型的数据馈送，其中包括用于 Data Workbench 的数据馈送，但是客户（数据控制者）仍要负责确保删除的数据符合其内部的数据保留和删除策略。 </p> <p>另外，还需要考虑员工可能已经下载了包含个人数据的 Adobe Analytics 报表的情况。如果收到了与数据隐私相关的删除请求中涉及报表内可能存在的 ID，则需要更新或删除这些报表。客户应当与贵公司的法律顾问合作，确定保留期限以及应当应用于这些类型文档的隐私和安全要求。 </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b>我们意外将一些不应该收集的数据发送到了 Adobe Analytics。是否可以使用数据隐私 API 来清理此类数据？</b> </p> </td><td colname="col2"> <p>提供数据隐私 API 是为了帮助您执行对时间敏感的数据隐私请求。Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起数据隐私请求的能力。我们建议您不要将数据隐私 API 用于其他目的，例如清除大量访客意外提交的数据。</p> <p>您还应该了解，对于任何因提交数据隐私删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问次数、反向链接、访问的第一个页面等信息也都将重新统计。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了数据隐私 API 不适合此用途的一个原因。 </p> <p>请联系您的客户经理 (CSM) 来与我们的工程架构师咨询团队进行协调，以进一步审查并提供解决任何 PII 或数据问题的帮助。</p></td></tr> <tr> 
   <td colname="col1"> <p><b>我们的法律团队已经确定我们多年来一直在变量中收集的值，不再符合我们更新的隐私政策。我们是否可以使用数据隐私 API 清除此变量中的所有值？</b> </p> </td><td colname="col2"> <p>提供数据隐私 API 是为了帮助您执行对时间敏感的数据隐私请求。Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起数据隐私请求的能力。我们建议您不要将数据隐私 API 用于其他目的，例如清除大量访客意外提交的数据。</p> <p>您还应该了解，对于任何因提交数据隐私删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问次数、反向链接、访问的第一个页面等信息也都将重新统计。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了数据隐私 API 不适合此用途的一个原因。 </p> <p>请联系您的客户经理 (CSM) 来与我们的工程架构师咨询团队进行协调，以进一步审查并提供解决任何 PII 或数据问题的帮助。</p></td>
 </tbody> 
</table>

其他数据隐私资源：

* [GDPR 常用术语](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud 数据隐私[保护包](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 体验式隐私[博客文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
