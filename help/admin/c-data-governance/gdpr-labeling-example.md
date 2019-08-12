---
description: 'null'
seo-description: 'null'
seo-title: 标签功能示例
title: 标签功能示例
uuid: a9a5b937-dbde-4f0 f-a171-005ef4 c79 df9
translation-type: tm+mt
source-git-commit: edafa9ca8dc34bd1f3af8c56b4f23c4a983aa677

---


# 标签功能示例

## 命中数据示例

假设您具有以下命中数据：

* 第一行包含适用于每个变量的标签；
* 第二行是变量的名称；如果它有一个 ID 标签，它将包含括号中分配的命名空间。
* 而第三行是命中数据；

| 标签 | I2<br>ID-PersonDEL-PersonACC-Person<br><br> | I2<br><br>ID-DevicEDEL-DeviceACC-全部<br> | I2<br>DEL-SonAACC-Person<br> | I2<br><br>DEL-DevicEDL-PersonAVC-All<br> | I2<br><br>ID-DevicEDEL-DeviceACC-全部<br> |
|---|---|---|---|---|---|
| **变量名称**<br>**(命名空间)** | **MyProp1**<br>**(用户)** | **访客ID**<br>**(AACID)** | **MyEvar1** | **MyEvar2** | **MyEvar3**<br>**(xyz)** |
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

| API 值 | API 值 | 返回文件类型 | <br>摘要访问文件中的数据 | <br>摘要访问文件中的数据 | <br>摘要访问文件中的数据 | <br>摘要访问文件中的数据 | <br>摘要访问文件中的数据 |
|--- |--- |--- |---|---|---|---|---|
| **Namespace/ ID** | **expandIDs** |  | **MyProp1** | **访客 ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | “设备” | 变量不存在 | 77 | 变量不存在 | M、P | X、W |
| AAID=77 | true | “设备” | 变量不存在 | 77 | 变量不存在 | M、P | X、W |
| user=Mary | false | “人员” | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | “人员” | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | “设备” | 不存在 | 77、88 | 不存在 | N、P | U、W |
| user=Mary AAID=66 | true | “人员” | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary AAID=66 | true | “设备” | 不存在 | 66、77、88 | 不存在 | N、P | U、W、Z |
| xyz=X | false | “设备” | 不存在 | 55、77 | 不存在 | M、R | X |
| xyz=X | true | “设备” | 不存在 | 55、77 | 不存在 | M、P、R | W、X |

请注意，使用 Cookie ID 时，expandIDs 的设置对输出没有任何影响。

## 删除请求示例

通过使用表格第一行中的 API 值来提出删除请求，命中表格将会发生更新。具体情况如下所示：

| AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter | AAID=77 expandIDs value<br>does not matter |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | GDPR-7398 | GDPR-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | GDPR-1866 | GDPR-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] 仅影响包含AID=77和DEL-DEVICE标签的行上的单元格。

| user= maryExpands<br>= false | user= maryExpands<br>= false | user= maryExpands<br>= false | user= maryExpands<br>= false | user= maryExpands<br>= false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| GDPR-0523 | 77 | GDPR-1866 | GDPR-3681 | X |
| GDPR-0523 | 88 | GDPR-2178 | GDPR-1975 | Y |
| GDPR-0523 | 99 | GDPR-9045 | GDPR-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

>[!NOTE] 仅影响包含用户= Mary和DEL-HON标签的行上的单元格。另外，实际上，包含 A_ID 的变量可能是 prop 或 eVar，其替换值是以“GDPR-”开头的字符串，后面跟有随机数 (GUID)，而不是用不同的随机数值来替换该数值。

| user=Mary<br>expandIDs=true | user= maryExpands<br>= true | user= maryExpands<br>= true | user= maryExpands<br>= true | user= maryExpands<br>= true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| GDPR-5782 | 09 | GDPR-0859 | GDPR-8183 | GDPR-9152 |
| GDPR-5782 | 16 | GDPR-6104 | GDPR-2911 | GDPR-6821 |
| GDPR-5782 | 83 | GDPR-2714 | GDPR-0219 | GDPR-4395 |
| John | 09 | D | GDPR-8454 | GDPR-8216 |
| John | 16 | E | GDPR-2911 | GDPR-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

请注意以下事项：

* Cells on rows containing `user=Mary` and a `DEL-DEVICE` or `DEL-PERSON` label are impacted, as well as cells with a `DEL-DEVICE` label on rows containing any Visitor ID that occurred on a row containing `user=Mary`.
* `MyEvar2`第四行和第五行中的 将会更新，因为这些行包含与第一行和第二行相同的访客 ID 值，因此 ID 扩展会把它们包含在设备级别的删除中。
* The values of `MyEvar2` in rows two and five match both before and after the delete, but after the delete no longer matches the value N that occurs in the last row, because that row was not updated as part of the delete request.
* `MyEvar3` 的行为与不包含 ID 扩展时它的行为非常不同，因为没有 ID 扩展，就没有匹配的 `ID-DEVICES`Now `AAID` matches on the first five rows.
