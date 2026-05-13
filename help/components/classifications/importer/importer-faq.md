---
title: 分类常见问题解答
description: 使用分类的常见问题解答。
feature: Classifications
exl-id: e929d7cb-0bfd-46de-88d1-aea2b4b91911
TQID: https://experienceleague.adobe.com/pIwAdewnHA4AB9hyRDRkH6xXvyxx-BceWvDXMydX-ew
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 86%

---

# 分类导入器常见问题解答

{{classification-importer-deprecation}}

有关使用分类导入器的常见问题解答。

## 如何对维度项目“0”进行分类？

上载键值或分类值为零 (`0`) 的分类文件会导致错误。 这包括仅包含零（`00`、`000` 等）的所有值。 有几种方法可以解决此问题：

* **实施替代值**：使用文本值替代 `"0"` 是解决此问题的最佳且最简单的方法。 例如，将实施中的 `s.campaign = "0";` 更改为 `s.campaign = "Zero";`。

* **使用处理规则**：您可以在报表包中的数据收集与其存储之间修改维度项目。 创建以下处理规则：

  *如果[维度]等于 `0`，则使用自定义值 `Zero` 覆盖[维度]的值。*

* **请求设置 VISTA 规则**：工程服务顾问可为您设置服务器端规则，但需支付额外费用。 请联系您的 Adobe 客户团队以请求 VISTA 规则。

## 是否可以使用分类导入器对尚不存在的维度项目进行分类？

是，*但这样做会将每个维度项目计为一次可计费服务器调用。*

* 已存在的维度项目不会产生任何额外成本。
* 使用分类规则生成器不会对不存在的项目进行分类，因此不会产生任何额外成本。

## 如何对包含特殊字符的值进行分类？

不支持在分类数据和点击数据中使用前导和尾随空格，因为Adobe Analytics会自动截断空白字符。

通常情况下，不建议在报表中使用逗号或双引号之类的特殊字符。 但是，在某些情况下，有必要使用特殊字符。 如果您选择进行分类的报表值包含此类字符，请执行以下步骤：

1. 登录到 Adobe Analytics，然后导航到&#x200B;**[!UICONTROL 管理员]** > **[!UICONTROL 分类导入器]**。
2. 单击&#x200B;**[!UICONTROL 浏览器导出]**&#x200B;选项卡。
3. 配置导出设置，并确保未选中“引用输出”。
4. 单击&#x200B;**[!UICONTROL 导出文件]**，然后在电子表格编辑器中打开下载的文件。
5. 在第 1 行，找到包含值 `v:2.0` 的单元格 C1。 将该值更改为 `v:2.1` 并将所需的分类应用到工作簿。
6. 像上载任何其他分类一样上载该文件。

## 什么是数值 2 分类？

数值 2 分类允许您将维度项目分类为基于时间的量度。 该分类已于 2019 年 7 月在 Adobe Analytics UI 中停用。

## 如何对分类文件中的数据进行转义？

用双引号(`"`)括起包含特殊字符的字段。 可通过将一个双引号字符替换为两个双引号字符 (`" "`) 的方式，让其显示在已转义的单元格内。 例如：

```
My String "of data"
```

转义为：

```
"My String ""of data"""
```
