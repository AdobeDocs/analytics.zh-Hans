---
description: 有关 Activity Map 中链接跟踪的常见问题解答。
title: 链接跟踪常见问题解答
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: a0b8f61c3728c5867640ce20768614c8d79ca657
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 100%

---

# 链接跟踪常见问题解答

有关 Activity Map 中链接跟踪的常见问题解答。

>[!CAUTION]
>
>启用 Activity Map 跟踪后，**您可能会收集个人身份识别信息 (PII) 数据。**&#x200B;此类数据可用于（单独或与其他信息配合使用）识别、联系或查找个人，或者在上下文中识别个人。

以下是使用 Activity Map 跟踪收集 PII 数据的一些已知案例：

* `Mailto` 链接。Mailto 链接是一种 HTML 链接，它可以激活计算机上的默认邮件客户端来发送电子邮件。
* 用户登录后可能出现在网站页眉/页脚的 `User ID` 链接。
* 在金融机构的网站中，账号可能会显示为链接。单击该链接将收集链接的文本。
* 在医疗保健网站中，PII 数据也可能会显示为链接。单击这些链接将收集链接的文本，进而收集 PII 数据。

## 何时进行链接跟踪？

当用户单击页面时，会开始识别 Activity Map 链接和区域。

## 默认情况下，会跟踪哪些内容？

如果针对某个元素执行了单击事件，则必须对该元素进行一些检查，以确定 AppMeasurement 是否将该元素视为链接。检查内容如下：

* 是否属于包含 `href` 属性的 `A` 或 `AREA` 标记？
* 是否属于设置 `s_objectID` 变量的 `onclick` 属性？
* 是否属于包含值或子文本的 `INPUT` 标记或 `SUBMIT` 按钮？
* 是否属于包含 `IMAGE` 类型和 `src` 属性的 `INPUT` 标记？
* 是否属于 `BUTTON`？

如果以上任一问题的回答为是，则该元素将被视为链接，需要对其进行跟踪。

>[!IMPORTANT]
>
>AppMeasurement 不会将具有属性 type=&quot;button&quot; 的 Button 标记视为链接。请考虑删除按钮标记上的 type=&quot;button&quot;，然后添加 role=&quot;button&quot; 或 submit=&quot;button&quot;。

>[!IMPORTANT]
>
>AppMeasurement 将带有以“#”开头的“href”的锚点标记视为内部目标位置，而不是链接（因为您不会离开页面）。默认情况下，Activity Map 不跟踪这些内部目标位置，而是仅跟踪将用户导航到新页面的链接。

## Activity Map 如何跟踪其他可视化 HTML 元素？

a. 通过 `s.tl()` 函数。

如果单击操作是通过 `s.tl()` 调用发生的，则 Activity Map 也会收到这个单击事件，并且会确认是否能够找到 `linkName` 字符串变量。在 `s.tl()` 执行期间，该 linkName 将被设置为 Activity Map 链接 ID。发起 `s.tl()` 调用的被单击元素将用于确定区域。示例：

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. 通过 `s_objectID` 变量。示例：

    ``` 
    
    &lt;img onclick=&quot;s_objectID=&#39;abc&#39;;&quot; src=&quot;someimageurl.png&quot;/>
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&#39;abc&#39;;&quot; >
    此处为链接文本
    &lt;/a>
    
    ```

>[!IMPORTANT]
>
>在 Activity Map 中使用 `s_objectID` 时，需要以分号 (;) 结尾。

## 能否提供一些将被跟踪的链接示例？

### 示例 1

```
  <a href="/home>Home</a>
```

### 示例 2

```
 <input type="submit" value="Submit"/>
```

### 示例 3

```
  <input type="image" src="submit-button.png"/>
```

### 示例 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### 示例 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## 能否提供一些不被跟踪的链接示例？

1. 原因：锚标记不具备有效的 `href`:
   `<a name="innerAnchor">Section header</a>`

1. 原因：既不存在 `s_ObjectID`，也不存在 `s.tl()`：

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. 原因：既不存在 `s_ObjectID`，也不存在 `s.tl()`：

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. 原因：“src”属性缺少表单输入元素：

   `<input type="image"/>`

