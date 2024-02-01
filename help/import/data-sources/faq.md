---
title: 数据源常见问题解答
description: 有关数据源的常见问题解答。
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 4%

---

# 数据源常见问题解答

有关数据源的常见问题解答。

+++使用数据源的成本是多少？
数据源不会产生任何费用，也不会计入服务器调用使用情况。 [完全处理数据源](full-processing-eol.md) 在停用之前计入服务器调用。
+++

+++数据源如何影响eVar的归因和到期？
如果transactionID在数据源和在线点击之间匹配，则关联的eVar值将假定相同的归因和过期时间，就像它们在在线点击中设置一样。

通过数据源上传的所有其他数据没有任何类型的归因或到期。
+++

+++数据源对默认量度（如页面查看次数、访问次数或独特访客）有何影响？
通过数据源上传的数据不会影响 [页面查看次数](/help/components/metrics/page-views.md)， [访问](/help/components/metrics/visits.md)，或 [独特访客](/help/components/metrics/unique-visitors.md) 不管怎样。 它们影响的唯一默认量度包括 [发生次数](/help/components/metrics/occurrences.md).
+++

+++我是否可以删除使用数据源导入的数据？

**不适用。** 使用数据源上传到报表的数据是 **永久**. 导入后，即使按照Adobe，也无法将其删除。 Adobe强烈建议先将数据源数据上传到测试报表包，然后再上传到生产报表包。
+++

+++一次可导入多少数据？

如果数据总量超过 50 MB，处理便会暂停，并且直到数据总量低于 50 MB 时才会恢复。请确保FTP站点上所有文件的总大小小于50 MB。
+++

+++如果我通过数据源将负值传递到报表，会发生什么情况？

价值会因此而减少。 某些组织使用负数据源值来尝试更正数据。 负数据源值可能会以不希望或意外的方式影响报表。 Adobe建议仅在万不得已时才使用负数据源。
+++

+++文件扩展名是否区分大小写？
是的。文件扩展名为 `.TXT` 或 `.FIN` 不会处理。 确保文件扩展名全部为小写。
+++

+++可以向数据源文件中添加多少列？
您可以根据需要，在数据源文件中包括任意数量的列（如果它们都是有效列）。 请参阅 [文件格式](file-format.md) 以获取有效变量/列名称的列表。
+++

+++我能否在不使用Adobe提供的FTP位置的情况下使用数据源？
您可以使用 [数据源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，允许您直接向Adobe发送API调用。 这些API调用包括 `UploadData` 方法，允许您通过JSON对象有效负载发送数据。
+++
