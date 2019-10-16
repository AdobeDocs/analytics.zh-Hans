---
description: 'null'
seo-description: 'null'
seo-title: 常见问题解答
title: 常见问题解答
uuid: 1cd41253-d74f-4b92-92e6-56f9afa3df85
translation-type: tm+mt
source-git-commit: 90b2ff68e04a2d0027205a906de9091061430d98

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
   <td colname="col1"> <p><b>Adobe Analytics如何支持对由客户（数据控制者）验证的最终用户（数据主体）的访问和删除请求？</b> </p> </td> 
   <td colname="col2"> <p>当各种数据隐私规则(GDPR、CCPA)生效时，Adobe Analytics将支持处理由数据控制者向Experience cloud数据隐私API提交的经过验证的请求，以实现更自动化的流程。 Adobe的数据隐私API旨在帮助处理通过Adobe Experience cloud解决方案存储的客户数据的个人权限请求（例如访问和删除请求）。 它具有灵活性和伸缩性，具体情况将依据贵公司从数据主体接收到的数据访问和删除请求数量。此外，数据隐私API允许客户检查数据访问和删除请求的完成方式。 </p> <p>For more details see <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Data Privacy API documentation </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>谁负责接收、接受和完成来自最终用户的数据隐私请求？</b> </p> </td> 
   <td colname="col2"> <p>数据控制者（即Adobe客户）有责任根据数据隐私下的个人权利请求为数据主体提供个人数据。 数据管理者还单方面负责接收请求和接受请求——验证数据主体的身份，然后完成请求，其中一部分可能涉及使用与Adobe Analytics中存储的数据相关的数据主体的ID与Adobe联系。 作为“数据处理者”，Adobe 必须向控制者提供合理的帮助，以便在可接受的时间范围内处理已验证的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe客户（数据管理者）将如何在Adobe Analytics中查找哪些数据隐私请求映射到哪些ID以进行数据隐私处理？</b> </p> </td> 
   <td colname="col2"> <p>数据控制者将确定如何解析发出请求的数据主体的身份。考虑部 <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> 署Adobe的数据隐私ID检索标签 </a>。 您的开发团队将通过使用我们的数据隐私ID检索标记捕获用户ID(cookie ID)，然后使用我们的数据隐私API将这些用户ID发送到Adobe Experience Cloud的数据隐私请求处理中的相关解决方案，从而节省时间。 </p> <p>数据隐私API可以跨多个Adobe解决方案支持各种客户ID。 如果数据主体提交请求和标识符（自定义变量- prop或eVar），则Adobe Analytics将扫描为给定标识符收集的数据的整个保留历史记录。 有关如何配置存储在Analytics props或eVar中的自定义ID的更多详细信息，请参阅有关命名空间的分析文 <a href="/help/admin/c-data-governance/gdpr-namespaces.md"> 档</a>。
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics数据管理如何帮助处理数据隐私请求？</b> </p> </td> 
   <td colname="col2"> <p>“数据管理”是 Adobe Analytics 中的一个新工具，它赋与数据控制者在其 Analytics 数据中应用数据控制和分类的能力。此新工具使Adobe客户能够自定义其数据隐私数据访问和数据删除请求的处理。 在“数据管理”控制台中，管理员可以定义多种所需的设置，这些设置应该会应用于 Adobe Analytics 的各种数据列中。定义这些标签后，Adobe将根据客户所需的标签设置处理任何下游访问或删除请求。 数据控制者有责任进行审查，并就这些标签设置与其法律代表进行协商。Adobe Analytics鼓励客户在GDPR生效日期（即2018年5月25日）之前正确设置数据标签，以允许使用数据隐私API自定义完成请求。 </p> <p>“数据管理”工具包含以下数据标签： </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels" format="dita" scope="local">身份数据标签</a>：用于对可以直接识别个人或与其他数据结合使用以识别个人的数据进行分类。（无、I1、I2） </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels" format="dita" scope="local">敏感数据标签</a>：用于按照适用的法律，对定义为敏感数据的数据进行分类。（无、S1、S2）请注意，当前通常禁止在 Adobe Analytics 中使用敏感数据，但是根据适用法律正确获得的精确地理位置数据除外，不过在某些司法辖区，这类数据可能会被视为敏感数据。 </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels" format="dita" scope="local"> 数据隐私数据标签 </a>:用于定义可能包含个人标识符的字段以用于数据隐私请求或应作为数据隐私删除请求的一部分删除的字段。 在某些情况下，这些标签可能会与身份和敏感数据标签重叠。 </li> 
    </ul> <p>For more information on Data Governance labels, see <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels" format="dita" scope="local"> Data Privacy Labels for Analytics Variables </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>从何开始使用Adobe Analytics准备数据隐私？</b> </p> </td> 
   <td colname="col2"> <p>有关为准备使用数据隐私规则而进行的分步演练，请参阅 <a href="/help/admin/c-data-governance/an-gdpr-workflow.md" format="dita" scope="local"> Adobe Analytics数据隐私工作流程 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>当涉及到用户参与时，数据控制者应该如何考虑同意管理？</b> </p> </td> 
   <td colname="col2"> <p>GDPR和CCPA是重新考虑同意管理战略和实践的好机会，包括确定何时需要同意以及考虑用户的价值主张。 考虑消费者隐私的价值定位，这有助于推动转化以及提高忠诚度。 </p> <p>同意管理领域（例如，工具、标准、最佳实践）正在快速发展，这是一个需要密切观察的领域。为了最大限度地减少对用户参与的影响，控制者应该与此领域内的供应商及其法律顾问合作，遵循新颁布的欧盟法规以及有关同意和 Cookie 的指导。通过使用品牌上、上下文相关的体验来思考“体验式隐私”问题，从而阐明数据收集活动的价值主张是一个好战略。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>在数据隐私方面，数据管理者应该如何考虑数据保留？</b> </p> </td> 
   <td colname="col2"> <p>数据隐私一般规定，个人数据通常不应保留的时间长于达到收集数据的目的所必需的时间。 </p> <p>正如 Adobe 在 2 月份客户沟通会上详细阐明的那样，除非已对客户履行了其他安排（根据客户的通知和授权），否则我们将为大多数客户实施 25 个月的数据保留计划。在Adobe处理数据隐私请求之前，客户需要设置其数据保留策略。 </p> <p>Adobe Analytics要求客户设置数据保留以处理其数据隐私请求。 每个报表包的当前数据保留策略都显示在新的“数据管理管理员”UI中。 如果客户需要调整其数据保留策略，则应联系其 Adobe 代表。请参考 <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Adobe Analytics 数据保留常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>客户能否缩短或延长默认的数据保留期限？</b> </p> </td> 
   <td colname="col2"> <p>客户可通过致电客户关怀，请求在 25 个月之内删除他们的数据。客户可以通过购买扩展将数据保留期延长到25个月以上。</p><p>
   可以再增加1(1)年，最多可再增加8(8)年（共10年）。 延长保留期可能会涉及更新合同条款并需要支付额外费用。
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>从 Adobe Analytics 导出个人数据时，数据控制者应该考虑哪些隐私问题？</b> </p> </td> 
   <td colname="col2"> <p>如果客户使用 Adobe Analytics 数据馈送，将数据从 Analytics 导出到其企业数据仓库或 Adobe 以外的其他系统，则客户（数据控制者）有责任确保对数据应用删除请求。这同样适用于 Adobe Data Workbench (Insight) 的内部部署实施，当前，持续进行的 Adobe Analytics 数据馈送正在填充 Data Workbench 数据。Adobe可能提供一些工具来帮助从特定类型的数据馈送（包括用于Data Workbench的记录）中查找和删除记录，但客户（数据控制者）仍有责任确保删除数据符合其自己的内部数据保留和删除策略。 </p> <p>另外，还需要考虑员工可能已经下载了包含个人数据的 Adobe Analytics 报表的情况。如果收到与数据隐私相关的删除请求，并且该请求涉及报告中可能存在的ID，则这些报告可能需要更新或删除。 客户应与贵公司的法律顾问合作，确定保留期限，以及应用于这些类型文档的隐私和安全要求。 </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b>我们意外将一些不应该收集的数据发送到了 Adobe Analytics。我们是否可以使用数据隐私API清除此数据？</b> </p> </td><td colname="col2"> <p>提供数据隐私API以帮助您完成数据隐私请求，这些请求是时间敏感的。 Adobe不支持将此API用于其他用途，并可能会影响Adobe为其他Adobe客户及时提供高优先级、由用户发起的数据隐私请求的能力。 我们要求您不要将数据隐私API用于其他用途，如清除意外跨大量访客提交的数据。</p> <p>您还应注意，因数据隐私删除请求而删除（更新或匿名化）点击的任何访客都将重置其状态信息。 这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问编号、反向链接、查看的首页等信息也都将重新显示。如果您要清除数据字段，则不会产生这种副作用，并且会突出说明数据隐私API不适合此用途的一个原因。 </p> <p>请联系您的客户经理(CSM)，与我们的工程架构师咨询团队协调，以进一步审查并提供删除任何PII或数据问题的工作量。</p></td></tr> <tr> 
   <td colname="col1"> <p><b>我们的法律团队已经确定我们多年来一直在变量中收集的值，不再符合我们更新的隐私政策。Can we use the Data Privacy API to clear out all values from this variable?</b> </p> </td><td colname="col2"> <p>提供数据隐私API以帮助您完成数据隐私请求，这些请求是时间敏感的。 Adobe不支持将此API用于其他用途，并可能会影响Adobe为其他Adobe客户及时提供高优先级、由用户发起的数据隐私请求的能力。 我们要求您不要将数据隐私API用于其他用途，如清除意外跨大量访客提交的数据。</p> <p>您还应注意，因数据隐私删除请求而删除（更新或匿名化）点击的任何访客都将重置其状态信息。 这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问编号、反向链接、查看的首页等信息也都将重新显示。如果您要清除数据字段，则不会产生这种副作用，并且会突出说明数据隐私API不适合此用途的一个原因。 </p> <p>请联系您的客户经理(CSM)，与我们的工程架构师咨询团队协调，以进一步审查并提供删除任何PII或数据问题的工作量。</p></td>
 </tbody> 
</table>

其他数据隐私资源：

* [GDPR 常用术语](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud数据隐私 [保护包](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 体验式隐私[博客文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
