---
title: 数据源常见问题解答
description: 有关数据源的常见问题解答。
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 7%

---

# 数据源常见问题解答

有关数据源的常见问题解答。

+++使用数据源的成本是多少？
数据源不会产生任何费用，也不会计入服务器调用使用情况。 [完全处理数据源](full-processing-eol.md)在停用之前计入服务器调用。
+++

+++数据源如何影响eVar的归因和到期？
数据源没有任何类型的归因或过期。
+++

+++数据源如何影响页面查看次数、访问次数或独特访客等量度？
通过数据源上传的数据不会以任何方式影响[页面查看次数](/help/components/metrics/page-views.md)、[访问次数](/help/components/metrics/visits.md)或[独特访客](/help/components/metrics/unique-visitors.md)。 它们影响的唯一默认量度包括[发生次数](/help/components/metrics/occurrences.md)。
+++

+++通过数据源上传的数据是否通过其他处理（如处理规则）运行？
否。通过数据源上传的数据：

* 未通过[处理规则](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
* 不遵循[营销渠道处理规则](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
* 不遵循[VISTA规则](/help/technotes/vista.md)
+++

+++我是否可以删除使用数据源导入的数据？
是的。您可以使用[数据修复API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)删除此数据。 Adobe强烈建议先将数据源数据上传到测试报表包，然后再上传到生产报表包，以缓解删除数据的需要。
+++

+++一次可以导入多少数据？
如果数据总量超过 50 MB，处理便会暂停，并且直到数据总量低于 50 MB 时才会恢复。请确保FTP站点上所有文件的总大小小于50 MB。
+++

+++如果我通过数据源将负值传递到报表，会发生什么情况？
价值会因此而减少。 某些组织使用负数据源值来尝试更正数据。 负数据源值可能会以不希望或意外的方式影响报表。 Adobe建议只有在万不得已时才在数据源中使用负值。
+++

+++文件扩展名是否区分大小写？
是的。不会处理扩展名为`.TXT`或`.FIN`的文件。 确保文件扩展名全部为小写。
+++

+++可以向数据源文件中添加多少列？
您可以根据需要，在数据源文件中包括任意数量的列（如果它们都是有效列）。 有关有效变量/列名的列表，请参阅[文件格式](file-format.md)。
+++

+++我能否在不使用Adobe提供的FTP位置的情况下使用数据源？
您可以使用[数据源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，它允许您将API调用直接发送到Adobe。 这些API调用包括`UploadData`方法，该方法允许您通过JSON对象有效负载发送数据。
+++
