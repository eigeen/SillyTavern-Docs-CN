# 世界信息

**世界信息（又称 Lorebooks 或 Memory Books）可增强AI对世界细节的理解。**

它的功能就像一个动态字典，只有当消息文本中出现与世界信息条目相关的关键字时，才会插入这些条目的相关信息。

SillyTavern 引擎会激活并将适当的 Lore 无缝整合到提示词中，为AI提供背景信息。

*需要注意，虽然世界信息有助于引导AI找到你期望的 Lore，但并不保证其会出现在生成的输出消息中。*

### 进阶提示

* AI 不会在上下文中插入触发关键词，因此每个世界信息条目都应是全面、独立的描述。
* 为了创建丰富详尽的世界传说（world lore），条目之间可以相互链接和参考。
* 为了节约 Token，条目内容最好简洁明了，一般建议每个条目不超过 50 个 Token。

## 角色 Lore (Character Lore)

可以选择将一个世界信息文件分配给一个角色，作为该角色所有聊天（包括群组）的专用 Lore 源。

要做到这一点，请导航到“角色管理”面板并单击“地球仪”按钮，然后从下拉列表中选择“世界信息”并单击“确定”。

### 角色 Lore 插入策略

在生成AI回复时，角色世界信息中的条目将与全局世界信息选择器中的条目相结合，具体方式如下：

#### 均匀排序（默认）

所有条目将根据插入顺序排序，就像它们是一个大文件的一部分而忽略源文件。

#### 角色 Lore 优先

角色世界信息中的条目将首先包含在内，并根据插入顺序排序。然后再包含全球世界信息中的条目。

#### 全局 Lore 优先

全局世界信息中的条目将首先包含在内，并根据插入顺序排序。然后再包含角色世界信息中的条目。

### 世界信息条目

#### 关键字

用于触发激活世界信息条目的关键字列表。默认情况下，关键字不区分大小写（这是 [可配置的](#casesensitivekeys)）。

#### 次要关键字

用于与主关键字一起使用的补充关键字列表。请参阅 [选择性](#selective)。

#### 条目内容

当条目激活时，插入提示词的文本。

#### 插入排序

数值。定义同时激活多个条目的优先级。排序值较高的条目将被插入到更靠近上下文末尾的位置，因为它们对输出的影响更大。

#### 插入位置

* **角色定义前：** 世界信息条目插入在角色描述和场景之前。对对话的影响适中。
* **角色定义后：** 世界信息条目插入在角色描述和场景之后。对对话有较大影响。

#### 注释

为了便利而添加的文本注释，该内容不会发送给AI。

#### 常驻

如果启用，该条目将始终出现在提示词中。

#### Selective

如果启用，只有同时激活关键字**和**次要关键字时，才会插入条目。

如果没有提供次要关键字，该配置将被忽略。

### 扫描深度

定义最多扫描聊天记录中多少条消息来查找世界信息关键字。

如果设置为 1，那么 SillyTavern 只扫描你发送的消息和最近的回复。

最多叠加到 10 组消息。

### Token 预算

**定义世界信息条目一次可以使用多少 Token。**

如果预算耗尽，即使提示词出现了关键字，也不会激活更多的条目。

常驻项将首先插入。然后是高排序优先级的项。

直接提及其关键字插入的条目比在其他条目内容中提到的条目具有更高的优先级。

### 递归扫描

**条目可通过在条目内容中提及关键字来激活其他条目。**

例如，如果你的世界信息包含两个条目：

```txt
条目 #1
关键字: Bessie
内容: Bessie is a cow and is friends with Rufus.
```

```txt
条目 #2
关键字: Rufus
内容: Rufus is a dog.
```

如果消息文本只提到**贝西**，那么这两者**都**会被拉到上下文中。

### 关键字区分大小写

**要进入上下文，条目关键字需要与世界信息条目中定义的大小写相匹配。**

当你的关键字是常用词或常用词的一部分时，这就很有用了。

例如，启用此设置后，关键字“rose”和“Rose”将根据输入内容的不同进行不同的处理。

### 匹配整个单词

只有在搜索文本中出现整个单词时，关键字只包含一个单词的条目才会被匹配。

例如，如果启用了该设置，且条目关键字为“king”，那么“long live the king”之类的文本将被匹配，但“it's not to my liking”则不会被匹配。