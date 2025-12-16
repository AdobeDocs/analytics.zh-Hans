---
title: 分类集规则
description: 了解如何使用分类集规则来定义分类数据的规则。
feature: Classifications
hide: true
hidefromtoc: true
source-git-commit: 0f80bb314c8e041a98af26734d56ab364c23a49b
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 10%

---


# 分类集规则

在关键维度不断更改的情况下，可使用规则支持自动分类。 通过上载或自动化来更新分类会变成一个繁琐的过程，或落后于对新维度值的正确分类。 例如，内部营销活动、跟踪代码或产品SKU。 维度必须包含的值允许您应用一个或多个规则，以便从这些值中派生分类数据。

您可以在分类集的上下文中定义规则。 此上下文意味着将规则（激活时）应用于订阅分类集的所有报表包和键维度组合。 此实施与旧版分类规则生成器的工作方式略有不同。 在分类规则生成器中，将一个或多个规则单独定义为规则集的一部分，然后将规则集与一个或多个报表包关联。 在新界面中，分类集中的规则也称为规则集。 但是，规则集是在配置其他分类集属性的同一界面中定义的。


要为分类集定义规则集，请执行以下操作：

1. 从Adobe Analytics顶部菜单栏中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 分类集]**。
1. 在&#x200B;**[!UICONTROL 分类集]**&#x200B;中，选择&#x200B;**[!UICONTROL 分类集]**&#x200B;选项卡。
1. 在&#x200B;**[!UICONTROL 分类集]**&#x200B;管理器中，选择要为其定义规则的分类集。
1. 在&#x200B;**[!UICONTROL 分类集：_分类集名称_]**&#x200B;对话框中，选择&#x200B;**[!UICONTROL 规则]**&#x200B;选项卡。

   * 如果您是首次访问分类集的&#x200B;**[!UICONTROL 规则]**&#x200B;界面，或者您目前决定继续使用旧版规则生成器界面，则将显示一个对话框，允许您选择如何开始使用。

     ![规则迁移](assets/rules-migration.png)

     选项包括：

      * **迁移现有规则**。 导入当前分类规则，并在新界面中继续使用这些规则。 您的现有规则将被保留并转换为新格式。
         * 选择&#x200B;**[!UICONTROL 迁移规则]**&#x200B;以继续。
         * 在&#x200B;**[!UICONTROL 确认迁移]**&#x200B;对话框中，阅读迁移的影响。
            * 选择&#x200B;**[!UICONTROL 迁移规则]**&#x200B;以确认迁移。 迁移完成后，使用[规则集接口](#rule-set-interface)创建新规则并编辑现有迁移规则。
            * 选择&#x200B;**[!UICONTROL 取消]**&#x200B;以取消迁移

      * **重新开始**。 使用新的规则生成器从头开始创建新分类规则。 如果要重新设计分类逻辑或使用新的分类规则从头开始，请选择此选项。
         * 选择&#x200B;**[!UICONTROL 创建新规则]**&#x200B;以继续。
         * 在&#x200B;**[!UICONTROL 确认重新开始]**&#x200B;对话框中，阅读重新开始的含义。
            * 选择&#x200B;**[!UICONTROL 重新开始]**&#x200B;以确认重新开始并放弃任何现有规则。 使用[规则集接口](#rule-set-interface)创建新规则。
            * 选择&#x200B;**[!UICONTROL 取消]**&#x200B;即可取消。


      * **使用旧版接口**。 继续使用以前的规则生成器界面。 您可以在准备就绪后随时迁移到新Experience。
         * 选择&#x200B;**[!UICONTROL 转到旧版接口]**&#x200B;以继续。 您将被定向到旧版&#x200B;**[!UICONTROL 分类规则生成器]**&#x200B;界面。

   * 如果您已经为分类集迁移规则或创建新规则，则最终将直接进入规则集界面。



## 规则集界面 {#rule-set-interface}

>[!CONTEXTUALHELP]
>id="classificationsets_rules_samplekeys"
>title="示例键"
>abstract="键入或粘贴测试键以测试规则集。 每一行是一个单独的键值。 选择&#x200B;**[!UICONTROL 测试规则集]**&#x200B;以显示包含结果的对话框。"


要创建或编辑规则，请使用规则集界面。

![规则集接口](assets/rulesets-ui.png)

| | 名称 | 描述 |
|---|---|---|
| 1 | **[!UICONTROL 函数]** | 您可以使用&#x200B;**[!UICONTROL 函数]**&#x200B;区域选择函数，并将函数拖放到规则集生成器中。 |
| 2 | **规则集生成器** | 您可以使用一个或多个规则来构建规则集。 规则是函数的实现，并且始终只与一个函数关联。 一个函数可以有多个运算符。 通过将函数拖放到规则集生成器中来创建规则。 函数类型定义规则的接口。 <br/>有关详细信息，请参阅[规则接口](#rule-interface)。<br/>您可以在任何位置插入函数，这些函数将按顺序执行，以确定分类的最终值。<br/>使用&#x200B;**[!UICONTROL 全部折叠]**&#x200B;折叠所有规则，并使用&#x200B;**[!UICONTROL 全部展开]**&#x200B;展开所有规则。 |
| 3 | **[!UICONTROL 状态]** | 显示规则集的状态和上次修改日期。 <br/>选择&#x200B;**[!UICONTROL 激活]**&#x200B;以激活规则集。 <br/>选择&#x200B;**[!UICONTROL 停用]**&#x200B;以停用规则集。 |
| 4 | **[!UICONTROL 回顾]** | 指定规则集的回顾时间范围。<br/>从下拉菜单中选择一个选项（从1个月到6个月）。<br/>选择&#x200B;**[!UICONTROL 执行回溯]**&#x200B;以使用所选回溯时段执行回溯。 |
| 5 | **[!UICONTROL 测试选项]** | 使用示例关键维度值测试分类： <ul><li>在&#x200B;**[!UICONTROL 示例键]**&#x200B;文本区域中添加或粘贴值。<br/>检查&#x200B;**[!UICONTROL 记住示例键]**，以确保示例键在规则集接口的不同用法之间保持不变。</li><li>选择&#x200B;**[!UICONTROL 测试规则集]**&#x200B;以测试您的规则集。</li></ul> |


## 规则界面

您可以在规则界面的规则集中定义每个单独的规则。 该界面包含以下元素：

![规则接口](assets/rule-ui.png)

| | 描述 |
|---|---|
| 1 | 选定函数的名称和为该函数输入的输入。 |
| 2 | 选定函数的输入。 输入取决于所选的函数。 例如，对于&#x200B;**[!UICONTROL 正则表达式]**&#x200B;函数，输入是正则表达式。 对于&#x200B;**[!UICONTROL Split]**&#x200B;函数，输入是一个令牌。 输入特定函数的相应输入。 例如，`^(.+)\:(.+)\:(.+)$`表示在内部促销活动代码中标识三个分类的正则表达式。 |
| 3 | 每个操作都会将特定分类设置为一个值。 <br/>从&#x200B;**[!UICONTROL 设置分类]**&#x200B;下拉菜单中选择一个分类，并输入&#x200B;**[!UICONTROL 到]**&#x200B;的值。 <br/>使用![CrossSize400](/help/assets/icons/CrossSize400.svg)从列表中删除操作。 |
| 4 | 选择![添加](/help/assets/icons/Add.svg) **[!UICONTROL 添加操作]**&#x200B;以向函数添加其他操作。 |
| 5 | 选择![ChevronDown](/help/assets/icons2/ChevronDown.svg)以折叠规则。 选择![ChevronLeft](/help/assets/icons/ChevronLeft.svg)展开规则。<br/>选择![CrossSize400](/help/assets/icons/CrossSize400.svg)以删除规则。 |

## 函数参考

对于每个受支持的函数，请查找以下有关所需输入和示例用例的详细信息。


### 开始于……

根据关键维度以开头的特定值设置分类。

+++ 详细信息 

#### 必需输入

输入&#x200B;**[!UICONTROL Starts With]**&#x200B;的值。 例如：`em`。

#### 用例

当关键维度“内部营销活动”的值以`Email`开头时（例如： **[!UICONTROL ），要定义一个规则以将]**&#x200B;分配为`em`Channel`em:FY2025:Summer Sale`分类的值。

>[!BEGINTABS]

>[!TAB 规则]

![规则 — 开头为](assets/rule-startswith.png)

>[!TAB 测试结果]

![规则 — 从测试结果开始](assets/rule-startswith-test.png)

>[!ENDTABS]

+++



### 结束于……

根据键维度结束的特定值设置分类。

+++ 详细信息 

#### 必需输入

输入&#x200B;**[!UICONTROL Ends With]**&#x200B;的值。 例如：`2025`。

#### 用例

当关键维度Internal Campaign的值包含`2025`时（例如：**[!UICONTROL ），要定义规则以将]**&#x200B;分配为`2025`Year`em:Summer Sale:FY2025`分类的值。

>[!BEGINTABS]

>[!TAB 规则]

![规则 — 结束于](assets/rule-endswith.png)

>[!TAB 测试结果]

![规则 — 以测试结果结束](assets/rule-endswith-test.png)

>[!ENDTABS]

+++


### 包含……

根据键维度包含的特定值设置分类。

+++ 详细信息 

#### 必需输入

输入&#x200B;**[!UICONTROL Contains]**&#x200B;的值。 例如：`Winter`。

#### 用例

当Internal Campaign的键维度值包含`Winter Sale`时（例如：**[!UICONTROL ），要定义规则以将]**&#x200B;分配为`Winter`Type`fb:Winter:FY2024`分类的值。


>[!BEGINTABS]

>[!TAB 规则]

![规则 — Contains](assets/rule-contains.png)

>[!TAB 测试结果]

![规则 — 包含结果](assets/rule-contains-test.png)

>[!ENDTABS]

+++


### 匹配

根据与键维度值匹配的特定值设置分类。

+++ 详细信息 

#### 必需输入

输入&#x200B;**[!UICONTROL Matches]**&#x200B;的值。 例如：`em:Summer:2025`。

#### 用例

您要定义一个规则以将`Email`分配为&#x200B;**[!UICONTROL Channel]**&#x200B;分类的值，将`Summer Sale`分配为&#x200B;**[!UICONTROL Type]**&#x200B;分类的值，并将`2025`分配为&#x200B;**[!UICONTROL Year]**&#x200B;分类的值。 但仅当关键维度“内部营销活动”的值与`em:Summer:2025`匹配时。


>[!BEGINTABS]

>[!TAB 规则]

![规则 — 匹配项](assets/rule-matches.png)

>[!TAB 测试结果]

![规则 — 匹配项](assets/rule-matches-test.png)

>[!ENDTABS]

+++


### 正则表达式

根据应用于键维度值的正则表达式设置一个或多个分类。

+++ 详细信息 

#### 必需输入

输入&#x200B;**[!UICONTROL 正则表达式]**&#x200B;的值。 例如：`^(.+)\:(.+)\:FY(.+)$`。

#### 用例

要定义规则以分配值给&#x200B;**[!UICONTROL Channel]**、**[!UICONTROL Type]**&#x200B;和&#x200B;**[!UICONTROL Year]**&#x200B;分类，方法是应用正则表达式`^(.+)\:(.+)\:FY(.+)$`并将匹配组（`$1`、`$2`和`$3`）用于关键维度Internal Campaign的值。

>[!BEGINTABS]

>[!TAB 规则]

![规则 — 正则表达式](assets/rule-regex.png)

>[!TAB 测试结果]

![规则 — 正则表达式测试结果](assets/rule-regex-test.png)

>[!ENDTABS]

+++


### 拆分

根据令牌将键维度值拆分为一个或多个分类。

+++ 详细信息

#### 必需输入

输入&#x200B;**[!UICONTROL Split]**&#x200B;的值。 例如：`:`。

#### 用例

要定义一个规则，以根据&#x200B;**&#x200B;**&#x200B;令牌&#x200B;**[!UICONTROL 将关键维度Internal Campaign的值拆分到]** Channel **[!UICONTROL 、]** Type`:`和&#x200B;**[!UICONTROL Year]**&#x200B;分类。

>[!BEGINTABS]

>[!TAB 规则]

![规则 — 拆分](assets/rule-split.png)

>[!TAB 测试结果]

![规则 — 拆分测试结果](assets/rule-split-test.png)

>[!ENDTABS]

+++


#### 参考表 {#section_0211DCB1760042099CCD3ED7A665D716}

| 正则表达式 | 描述 |
|---|---|
| `(?ms)` | 根据多行输入匹配整个正则表达式，允许`.`通配符匹配任何新行字符 |
| `(?i)` | 匹配整个正则表达式以区分大小写 |
| `[abc]` | 单个字符：a、b 或 c |
| `[^abc]` | 除以下字符外的任意单个字符：a、b 或 c |
| `[a-z]` | a 到 z 之间的任意单个字符 |
| `[a-zA-Z]` | a 到 z 或 A 到 Z 之间的任意单个字符 |
| `^` | 行的开始（匹配行的开始） |
| `$` | 匹配行的结尾（或结尾处的新行之前） |
| `\A` | 字符串的开始 |
| `\z` | 字符串的结尾 |
| `.` | 匹配任意字符（不包括新行） |
| `\s` | 任意空白字符 |
| `\S` | 任意非空白字符 |
| `\d` | 任意数字 |
| `\D` | 任意非数字 |
| `\w` | 任意单词字符（字母、数字、下划线） |
| `\W` | 任意非单词字符 |
| `\b` | 任意单词边界 |
| `(...)` | 捕获包含的任何内容 |
| `(a\b)` | a 或 b |
| `a?` | 零个或一个 a |
| `a*` | 零个或多个 a |
| `a+` | 一个或多个 a |
| `a{3}` | 恰好 3 个 a |
| `a{3,}` | 3 个或更多 a |
| `a{3,6}` | 3 到 6 个 a |



## 规则优先级

如果满足以下条件，则最后一个规则将确定分类的值：

* 关键维度值匹配到多个规则。
* 规则集包含具有相同&#x200B;**[!UICONTROL 设置分类]**&#x200B;操作的规则。

因此，您应该将最重要的&#x200B;**[!UICONTROL 设置分类]**&#x200B;操作作为规则集中最后一个规则的一部分进行排名。

如果创建的多个规则不共享同一&#x200B;**[!UICONTROL 设置分类]**&#x200B;操作，则处理顺序无关紧要。


### 示例

您要使用分类&#x200B;**[!UICONTROL 类型]**&#x200B;来分类，用户如何使用搜索字符串作为关键维度来搜索团队、泛型类型或播放器。 例如，通过使用此规则集：

+++ 详细信息


>[!BEGINTABS]

>[!TAB 规则]

![规则 — 优先级](assets/rule-priority.png)

>[!TAB 测试结果]

![规则 — 优先级测试结果](assets/rule-priority-test.png)

>[!ENDTABS]

+++ 

