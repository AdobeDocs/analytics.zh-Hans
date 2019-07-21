---
description: 'null'
seo-description: 'null'
seo-title: 常见问题解答
title: 常见问题解答
uuid: cd41253-d74 f-4b92-92e6-56f9 afa3 df85
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
   <td colname="col1"> <p><b>Adobe Analytics如何支持访问和删除最终用户(数据主体)验证的最终用户(数据主体)？</b> </p> </td> 
   <td colname="col2"> <p>GDPR 正式生效后，Adobe Analytics 将支持处理“数据控制者”向 Experience Cloud GDPR API 提交的验证请求，以实现更加自动化的流程。针对我们的客户在各种 Adobe Experience Cloud 解决方案中存储的数据，Adobe 的 GDPR API 旨在帮助处理个人权利请求（例如，访问和删除请求）。它具有灵活性和伸缩性，具体情况将依据贵公司从数据主体接收到的数据访问和删除请求数量。此外，GDPR API 允许客户检查有关执行数据访问和删除请求的进展状态。 </p> <p>更多详细信息，请参阅 <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">GDPR API 文档</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>谁负责接收、接受和履行最终用户的GDPR请求？</b> </p> </td> 
   <td colname="col2"> <p>“数据控制者”（例如 Adobe 客户）全权负责向数据主体提供个人数据，以回应符合 GDPR 的个人权利请求。数据管理者还自行负责接收请求并接受请求-验证数据主体的身份，然后完成请求，其中一部分可能涉及到与Adobe联系的数据主体ID，这些ID可能与存储在Adobe Analytics中的数据相关联。作为“数据处理者”，Adobe 必须向控制者提供合理的帮助，以便在可接受的时间范围内处理已验证的请求。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>为了进行 GDPR 处理，Adobe 客户（数据控制者）将如何找出哪些 GDPR 请求映射到 Adobe Analytics 中的哪些 ID？</b> </p> </td> 
   <td colname="col2"> <p>数据控制者将确定如何解析发出请求的数据主体的身份。Consider deploying <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> Adobe's GDPR ID Retrieval Tag </a>. 为了节省时间，您的开发团队可采用下面的方法：使用我们的 GDPR ID 检索标记捕获用户 ID (Cookie ID)，然后用我们的 GDPR API 将这些用户 ID 发送到 Adobe Experience Cloud 的相关解决方案中，以进行 GDPR 请求处理。 </p> <p>GDPR API 可以在多个 Adobe 解决方案中支持范围广泛的客户 ID。如果数据主体与标识符(自定义变量- prop或eVar)一起提交请求，Adobe Analytics会扫描为给定标识符收集的数据的整个保留历史记录。有关如何配置Analytics props或eVar中存储的自定义ID的更多详细信息，请参阅上的Analytics文档(/help/admin/c-data-communication/gdpr-namespopes. md)。
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Adobe Analytics 数据管理怎样协助处理 GDPR 请求？</b> </p> </td> 
   <td colname="col2"> <p>“数据管理”是 Adobe Analytics 中的一个新工具，它赋与数据控制者在其 Analytics 数据中应用数据控制和分类的能力。这种新工具允许 Adobe 客户自定义其 GDPR 数据访问和数据删除请求的处理方式。在“数据管理”控制台中，管理员可以定义多种所需的设置，这些设置应该会应用于 Adobe Analytics 的各种数据列中。一旦定义了这些标签，Adobe 将根据客户所需的标签设置，执行并处理任何下游访问或删除请求。数据控制者有责任进行审查，并就这些标签设置与其法律代表进行协商。Adobe Analytics 鼓励客户于 2018 年 5 月 25 日 GDPR 正式生效之前，在客户端上正确设置数据标签功能，以便允许利用 GDPR API 自定义请求的完成情况。 </p> <p>“数据管理”工具包含以下数据标签： </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_D7F4E4B60D6D40BEBC86B7004EF42AFF" format="dita" scope="local">身份数据标签</a>：用于对可以直接识别个人或与其他数据结合使用以识别个人的数据进行分类。（无、I1、I2） </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_533E1406F3F24A01B51D94139B94CAEC" format="dita" scope="local">敏感数据标签</a>：用于按照适用的法律，对定义为敏感数据的数据进行分类。（无、S1、S2）请注意，当前通常禁止在 Adobe Analytics 中使用敏感数据，但是根据适用法律正确获得的精确地理位置数据除外，不过在某些司法辖区，这类数据可能会被视为敏感数据。 </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="../../admin/c-data-governance/gdpr-labels.md#section_0C7F9EC4BB414A6D915C69F1D3259F1B" format="dita" scope="local">GDPR 数据标签</a>：用于对以下字段进行定义：包含 GDPR 请求中使用的个人标识符的字段，或者，作为 GDPR 删除请求的一部分而应该删除的字段。在某些情况下，这些标签可能会与身份和敏感数据标签重叠。 </li> 
    </ul> <p>有关“数据管理”标签的更多信息，请参阅<a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local">适用于 Analytics 变量的 GDPR 标签</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>我该从哪里开始着手准备 Adobe Analytics 以支持 GDPR？</b> </p> </td> 
   <td colname="col2"> <p>有关为 GDPR 做好准备的分步说明，请参阅 <a href="../../admin/c-data-governance/an-gdpr-workflow.md#concept_1D1C0C1EAC3B4772AEDF5CC9F0EA604B" format="dita" scope="local">Adobe Analytics GDPR 工作流程</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>当涉及到用户参与时，数据控制者应该如何考虑同意管理？</b> </p> </td> 
   <td colname="col2"> <p>GDPR 是重新考虑您的同意管理策略及惯例的好机会，包括确定何时需要同意并考虑针对用户的价值定位。考虑消费者隐私的价值定位，这有助于推动转化以及提高忠诚度。 </p> <p>同意管理领域（例如，工具、标准、最佳实践）正在快速发展，这是一个需要密切观察的领域。为了最大限度地减少对用户参与的影响，控制者应该与此领域内的供应商及其法律顾问合作，遵循新颁布的欧盟法规以及有关同意和 Cookie 的指导。利用基于品牌、与上下文相关的经验来思考“体验式隐私”是一种很好的策略，这些经验清晰而有条理地阐明了数据收集活动的价值定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>当涉及到 GDPR 时，数据控制者应该如何考虑数据保留？</b> </p> </td> 
   <td colname="col2"> <p>通常，GDPR 规定个人数据的保留时间不应超过为实现收集目的所需的时间。 </p> <p>正如 Adobe 在 2 月份客户沟通会上详细阐明的那样，除非已对客户履行了其他安排（根据客户的通知和授权），否则我们将为大多数客户实施 25 个月的数据保留计划。客户需要先设置其数据保留策略，然后 Adobe 才可以处理 GDPR 请求。 </p> <p>Adobe Analytics 要求客户设置其数据保留策略以处理其 GDPR 请求。每个报表包的当前数据保留策略都显示在新的数据管理管理员 UI 中。如果客户需要调整其数据保留策略，则应联系其 Adobe 代表。请参考 <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Adobe Analytics 数据保留常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>客户能否缩短或延长默认的数据保留期限？</b> </p> </td> 
   <td colname="col2"> <p>客户可通过致电客户关怀，请求在 25 个月之内删除他们的数据。客户可以通过购买扩展，将数据保留延长25个月以外。</p><p>
   扩展的有效期为(一)额外年，最多可增加(8)年(总共10年)。延长保留期可能会涉及更新合同条款并需要支付额外费用。
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>从 Adobe Analytics 导出个人数据时，数据控制者应该考虑哪些隐私问题？</b> </p> </td> 
   <td colname="col2"> <p>如果客户使用 Adobe Analytics 数据馈送，将数据从 Analytics 导出到其企业数据仓库或 Adobe 以外的其他系统，则客户（数据控制者）有责任确保对数据应用删除请求。这同样适用于 Adobe Data Workbench (Insight) 的内部部署实施，当前，持续进行的 Adobe Analytics 数据馈送正在填充 Data Workbench 数据。Adobe 会提供一些辅助工具来查找并删除某些类型的数据馈送，其中包括用于 Data Workbench 的数据馈送，但是客户（数据控制者）仍要负责确保删除的数据符合其内部的数据保留和删除策略。 </p> <p>另外，还需要考虑员工可能已经下载了包含个人数据的 Adobe Analytics 报表的情况。如果报表显示了在接收的 GDPR 或其他与隐私有关的删除请求中所涉及的 ID，则需要更新或删除这些报表。客户应当与贵公司的法律顾问合作，确定保留期以及应用于这些类型文档的隐私和安全要求。 </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b>我们意外将一些不应该收集的数据发送到了 Adobe Analytics。Can we use the GDPR API to cleanup this data?</b> </p> </td><td colname="col2"> <p>已提供GDPR API以帮助您完成GDPR请求，这些请求非常敏感。Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起 GDPR 请求的能力。我们建议您不要将 GDPR API 用于其他目的，例如清除大量访客意外提交的数据。</p> <p>您还应该了解，对于任何因提交 GDPR 删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问编号、反向链接、查看的首页等信息也都将重新显示。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了 GDPR API 不适合此用途的一个原因。 </p> <p>请联系您的客户经理(CSM)，与我们的工程架构师咨询团队进行进一步的审阅，进一步审查并提供删除任何PII或数据问题的工作。</p></td></tr> <tr> 
   <td colname="col1"> <p><b>我们的法律团队已经确定我们多年来一直在变量中收集的值，不再符合我们更新的隐私政策。我们是否可以使用 GDPR API 清除此变量中的所有值？</b> </p> </td><td colname="col2"> <p>已提供GDPR API以帮助您完成GDPR请求，这些请求非常敏感。Adobe 不支持将此 API 用于其他目的，因为这样会影响 Adobe 为其他 Adobe 客户及时提供高优先级服务、执行用户所发起 GDPR 请求的能力。我们建议您不要将 GDPR API 用于其他目的，例如清除大量访客意外提交的数据。</p> <p>您还应该了解，对于任何因提交 GDPR 删除请求后而删除其点击（已更新或匿名）的访客，其状态信息都将会进行重置。这样该访客下次返回您的网站时，将会成为新访客。所有 eVar 归因都将重新开始，访问编号、反向链接、查看的首页等信息也都将重新显示。对于要清除数据字段的情况，这种副作用不尽如人意，因此突显了 GDPR API 不适合此用途的一个原因。 </p> <p>请联系您的客户经理(CSM)，与我们的工程架构师咨询团队进行进一步的审阅，进一步审查并提供删除任何PII或数据问题的工作。</p></td>
 </tbody> 
</table>

其他 GDPR 资源：

* [GDPR 常用术语](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* Experience Cloud GDPR [知识集锦](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf)
* 体验式隐私[博客文章](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
