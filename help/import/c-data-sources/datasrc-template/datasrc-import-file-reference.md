---
description: 有关数据源 .txt 模板的信息。
seo-description: 有关数据源 .txt 模板的信息。
seo-title: 导入文件引用
solution: Analytics
subtopic: 数据源
title: 导入文件引用
topic: 开发人员和实施
uuid: cc58f8d8-cb6 e-4908-846f-0a41 c da805 d
translation-type: tm+mt
source-git-commit: cce2c1c54f21244f856385aeaad811d89f2fda7f

---


# 导入文件引用

有关数据源 .txt 模板的信息。

使用数据源向导可生成导入模板。数据源导入文件包含以下数据：

* 井号键 (#) 可将行标识为注释。
* 您可以根据需要向文件添加其他注释。
* 列出模板文件标题的注释。
* 列出在[!UICONTROL 数据源激活向导]中指定的外部量度和数据维度名称的注释。

列标题可用于识别数据源文件每一列中的数据。列标题有三种类型：

**日期**：（必需）对应文件中每个数据行的时间戳。

**变量**：映射到数据源数据维度的报告变量的名称。

**事件**：映射到数据源量度的事件的名称。

使用数据源模板创建数据源文件，其中包含要上载的数据。在创建数据源文件时，请记住以下事项：

* 实际上，数据源中的每一行都包含一个数据记录，而这其中的每一个记录都是由一系列制表符分隔字段组成的。数据源模板中的列标题定义这些字段的顺序。例如：

   ```
     #Sample data file for mycorp_report_suite 
     #Imported data for ad impressions applied to Event 6
     Date     Tracking Code      Event 6 
     1/1/2009     NYT8453A      8754
     1/1/2009     WSJ4453B      9492
     1/1/2009     BHG44563      10553
     1/2/2009     NYT8453A      6452
     1/2/2009     WSJ4453B      7237
     1/2/2009     BHG44563      9031
   ```

* 如果要上载多个数据文件，则数据源会以字母顺序载入它们。需要按时间顺序处理的文件必须命名，以使其字母顺序与时间顺序对应。例如：

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* 若要加快数据源文件的处理速度，Adobe 建议按日期将事件（量度）数据汇总到一行。

   例如，如果您的数据源文件将广告显示次数数据映射到事件 6，请创建一个包含每日广告显示总次数的数据行，而无需为某一特定日期发生的每一次广告显示创建一个单独的数据行条目。
* 如果需要从报表包创建日期之前的日期上载数据，请联系您的帐户管理员更改可运行报表的最早日期。

**.FIN 文件**

填写完数据源文件后，您可以将其FTP转换为Analytics。但是，若要使您的数据得以处理，还需要一个额外文件。You will need to upload an empty text file with the same name of your data file, but with a [!DNL .fin] extension.

For example, if you upload a (tab-delimited) data file called [!DNL myproductdata.txt], you would also need to upload an empty text file called [!DNL myproductdata.fin]. Without the [!DNL .fin] file, data would never be processed.
