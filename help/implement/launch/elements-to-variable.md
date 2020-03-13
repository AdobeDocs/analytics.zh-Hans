---
description: 'null'
title: 将数据元素映射到分析变量
uuid: null
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# 将启动数据元素映射到分析变量


将数 [据层对象映射到启动数据元素后](https://docs.adobe.com/content/help/en/analytics/implementation/layer-to-elements.md)，您可以将数据元素映射到 [Analytics变量](https://docs.adobe.com/content/help/en/analytics/implementation/vars/overview.html)。

要将启动项数据元素映射到Analytics变量，请执行以下操作：

1. 如果适用，将数据元素指定给全局变量。 某些数据元素(如“页 *面名称* ”)适用于属性中的每个页面。 在这种情况下，您可以通过执行以下操作全局设置变量：

2. 在启动项中，向下滚动并单击“扩 **展目录”**。

   ![扩展目录](assets/extensions.png)

3. 单击 **分析下** 的配置。

   ![Analytics 扩展](assets/configure.png)


4. 在“ **全局变量****”中的eVar下**，选择您设 [置的要与变量关联的eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) 。 选择 **设置为**，然后单击最右侧字段中的桶图标以指定数据元素。

   ![指定eVar](assets/evars.png)

5. 在“选 **择数据元素** ”弹出窗口中，选择要应用到变量的数据元素。

6. 单击&#x200B;**保存**。


或者，如果数据元素与全局变量不关联，您只需创建一个规则 [](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) ，将数据元素分配给prop或evar。
