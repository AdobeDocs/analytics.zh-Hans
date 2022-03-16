---
description: 显示一些示例来说明如何标记命中数据、访问请求、删除请求的数据
title: 标记示例
feature: Data Governance
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: ht
source-wordcount: '814'
ht-degree: 100%

---

# 标记示例

## 命中数据示例

假设您具有以下命中数据：

* 第一行包含适用于每个变量的标签。
* 第二行是变量的名称。如果它有一个 ID 标签，它将包含括号中分配的命名空间。
* 而第三行是命中数据；

| 标签 | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **变量名称** <br> **(命名空间)** | **MyProp1** <br> **(用户)** | **访客 ID** <br> **(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **(xyz)** |
| 命中数据 | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## 访问请求示例

如果我提交了访问请求，则摘要文件将包含下表中指示的值。一个请求只返回一个设备文件、一个人员文件，或各一个文件。只有在使用人员 ID 并且 expandIds 为 true 时，会返回两个摘要文件。

<table>
  <tr>
    <th colspan="2" style="text-align:center">API 值</th>
    <th rowspan="2">返回的<br>文件类型</th>
    <th colspan="5" style="text-align:center">摘要访问文件中的数据</th>
  </tr>
  <tr>
    <th>命名空间/ID</th>
    <th>expandIDs</th>
    <th>MyProp1</th>
    <th>访客 ID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td> AAID=77</td>
    <td>false</td>
    <td>“设备”</td>
    <td>不存在</td>
    <td>77</td>
    <td>不存在</td>
    <td>M、P</td>
    <td>X、W</td>
  </tr>
  <tr>
    <td> AAID=77</td>
    <td>true</td>
    <td>“设备”</td>
    <td>不存在</td>
    <td>77</td>
    <td>不存在</td>
    <td>M、P</td>
    <td>X、W</td>
  </tr>
  <tr>
    <td>user=Mary</td>
    <td>false</td>
    <td>“人员”</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary</td>
    <td rowspan="2">true</td>
    <td>“人员”</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td>“设备”</td>
    <td>不存在</td>
    <td>77、88</td>
    <td>A、B、C</td>
    <td>N、P</td>
    <td>U、W</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary<br>AAID=66</td>
    <td rowspan="2">true</td>
    <td>“人员”</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td>“设备”</td>
    <td>不存在</td>
    <td>66、77、88</td>
    <td>A、B、C</td>
    <td>N、P</td>
    <td>U、W、Z</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>false</td>
    <td>“设备”</td>
    <td>不存在</td>
    <td>55、77</td>
    <td>不存在</td>
    <td>M、R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>true</td>
    <td>“设备”</td>
    <td>不存在</td>
    <td>55、77</td>
    <td>不存在</td>
    <td>M、P、R</td>
    <td>W、X</td>
  </tr>
</table>

请注意，使用 Cookie ID 时，expandIDs 的设置对输出没有任何影响。

## 示例删除请求

通过使用表格第一行中的 API 值来提出删除请求，命中表格将会发生更新。具体情况如下所示：

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>（expandIDs 值无关紧要）</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Mary</td>
    <td>42</td>
    <td>A</td>
    <td>Privacy-7398</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>88</td>
    <td>B</td>
    <td>N</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>99</td>
    <td>C</td>
    <td>O</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>42</td>
    <td>D</td>
    <td>Privacy-1866</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>只有包含 AAID = 77 和 DEL-DEVICE 标签的行中的单元格会受到影响。

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary<br>expandIDs=false</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>77</td>
    <td>Privacy-1866</td>
    <td>Privacy-3681</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>88</td>
    <td>Privacy-2178</td>
    <td>Privacy-1975</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>99</td>
    <td>Privacy-9045</td>
    <td>Privacy-2864</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>77</td>
    <td>D</td>
    <td>P</td>
    <td>W</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
>只有包含 user=Mary 和 DEL-PERSON 标签的行中的单元格会受到影响。此外，在实际情况中，包含 A_ID 的变量可能是 prop 或 eVar。其替换值是以“Privacy-”开头的字符串，后跟一个随机数 (GUID)，而不是使用其他的随机数值替换该数值。

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary<br>expandIDs=true</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>09</td>
    <td>Privacy-0859</td>
    <td>Privacy-8183</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>16</td>
    <td>Privacy-6104</td>
    <td>Privacy-2911</td>
    <td>Privacy-6821</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>83</td>
    <td>Privacy-2714</td>
    <td>Privacy-0219</td>
    <td>Privacy-4395</td>
  </tr>
  <tr>
    <td>John</td>
    <td>09</td>
    <td>D</td>
    <td>Privacy-8454</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>16</td>
    <td>E</td>
    <td>Privacy-2911</td>
    <td>Privacy-2930</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

请注意以下事项：

* 包含 `user=Mary` 和 `DEL-PERSON` 标签的行中的单元格会受到影响。
* 由于 ID 扩展，包含 `AAID=77`、`AAID=88` 或 `AAID=99`（它们是包含 `user=Mary` 的行中的 AAID 值）和 `DEL-DEVICE` 标签的行中的单元格会受到影响。 这包括在 `user=Mary` 的行中带有 `DEL-DEVICE` 标签的单元格。 这会导致第 4 行和第 5 行（以及第 1-3 行）中带有 `DEL-DEVICE` 标签（AAID、MyEvar2 和 MyEvar3）的单元格被混淆。
* expandIDs 设置不会展开到调用以包含 MyEvar3（`X`、`Y` 和 `Z`）中存在的值，后者在 `user=Mary` 时具有 ID-DEVICE 标签。 ExpandIDs 仅展开以包含 `user=Mary` 的行中的访客 ID（在本例中为 AAID，但还包括 ECID）。 因此，包含 `X` 和 `Z` 的 MyEvar3 值的最后两行不受影响。
* 在第四行和第五行中的 `MyEvar2` 将更新，因为这两行包含的访客 ID 值（`77` 和 `88`）与第一行和第二行中的值相同。 因此，ID 扩展包括它们以用于设备级别的删除。
* 第二行和第五行中 `MyEvar2` 的值在删除前后均匹配。但是，在删除之后，它们不再匹配最后一行中出现的值 `N`，因为该行没有在删除请求期间更新。
* `MyEvar3` 的行为与不使用 ID 扩展时它的行为非常不同，因为没有 ID 扩展，就没有 `ID-DEVICES` 匹配。现在，`AAID` 在前五行上匹配。
