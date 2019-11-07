---
description: 'null'
title: 标签功能示例
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: tm+mt
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# 标签功能示例

## 命中数据示例

假设您具有以下命中数据：

* 第一行包含适用于每个变量的标签；
* 第二行是变量的名称；如果它有一个 ID 标签，它将包含括号中分配的命名空间。
* 而第三行是命中数据；

| 标签 | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **变量名称**<br>**（命名空间）** | **MyProp1**<br>**（用户）** | **访客 ID**<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
| 命中数据 | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## 访问请求示例

如果我提交访问请求，摘要文件将包含下表中显示的值。一个请求只返回一个设备文件、一个人员文件，或各一个文件。只有在使用人员 ID 并且 expandIds 为 true 时，会返回两个摘要文件。

| API 值 | API 值 | 返回文件类型 | 摘要访问文件中的数据<br> | 摘要访问文件中的数据<br> | 摘要访问文件中的数据<br> | 摘要访问文件中的数据<br> | 摘要访问文件中的数据<br> |
|--- |--- |--- |---|---|---|---|---|
| **命名空间/ID** | **expandIDs** |  | **MyProp1** | **访客 ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
|  AAID=77 | false | “设备” | 变量不存在 | 77 | 变量不存在 | M、P | X、W |
|  AAID=77 | true | “设备” | 变量不存在 | 77 | 变量不存在 | M、P | X、W |
| user=Mary | false | “人员” | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | “人员” | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | “设备” | 不存在 | 77、88 | 不存在 | N、P | U、W |
| user=Mary AAID=66 | true | “人员” | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary AAID=66 | true | “设备” | 不存在 | 66、77、88 | 不存在 | N、P | U、W、Z |
| xyz=X | false | “设备” | 不存在 | 55、77 | 不存在 | M、R | X |
| xyz=X | true | “设备” | 不存在 | 55、77 | 不存在 | M、P、R | W、X |

请注意，使用 Cookie ID 时，expandIDs 的设置对输出没有任何影响。

## 删除请求示例

通过使用表格第一行中的 API 值来提出删除请求，命中表格将会发生更新。具体情况如下所示：

| AAID=77 expandIDs 值<br>没有影响 | AAID=77 expandIDs 值<br>没有影响 | AAID=77 expandIDs 值<br>没有影响 | AAID=77 expandIDs 值<br>没有影响 | AAID=77 expandIDs 值<br>没有影响 |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | Privacy-7398 | Privacy-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacy-1866 | Privacy-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

> [!NOTE]只有包含 AAID = 77 和 DEL-DEVICE 标签的行中的单元格会受到影响。

| user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-0523 | 77 | Privacy-1866 | Privacy-3681 | X |
| Privacy-0523 | 88 | Privacy-2178 | Privacy-1975 | Y |
| Privacy-0523 | 99 | Privacy-9045 | Privacy-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

> [!NOTE]只有包含 user=Mary 和 DEL-PERSON 标签的行中的单元格会受到影响。另外，实际上，包含 A_ID 的变量可能是 prop 或 eVar，其替换值是以“Privacy-”开头的字符串，后面跟有随机数 (GUID)，而不是用不同的随机数值来替换该数值。

| user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-5782 | 09 | Privacy-0859 | Privacy-8183 | Privacy-9152 |
| Privacy-5782 | 16 | Privacy-6104 | Privacy-2911 | Privacy-6821 |
| Privacy-5782 | 83 | Privacy-2714 | Privacy-0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | Privacy-8216 |
| John | 16 | E | Privacy-2911 | Privacy-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

请注意以下事项：

* 以下单元格会受到影响：包含 `user=Mary` 以及 `DEL-DEVICE` 或 `DEL-PERSON` 标签的行中的单元格，以及包含 `DEL-DEVICE` 标签、且所在的行包含的访客 ID 来自 `user=Mary` 的行。
* 第四行和第五行中的 `MyEvar2` 将会更新，因为这些行包含与第一行和第二行相同的访客 ID 值，因此 ID 扩展会把它们包含在设备级别的删除中。
* 第二行和第五行的 `MyEvar2` 值在删除前后都匹配，但是在执行删除请求后，它们将不再与最后一行中出现的值 N 匹配，因为该行并不作为删除请求的一部分进行更新。
* `MyEvar3` 的行为与不使用 ID 扩展时它的行为非常不同，因为没有 ID 扩展，就没有 `ID-DEVICES` 匹配。现在，前五行中的 `AAID` 匹配了。
