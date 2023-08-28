# 作者注释

### 这是什么？

作者注释是自定义AI回复的强大工具，可在提示词中插入一段文字，插入位置和频率均可指定。

### 用法

作者注释可在对话输入栏左侧的选项菜单中找到。

| 选项菜单 | 作者注释面板 |
---------------|---------------------|
|![](https://github.com/SillyTavern/SillyTavern/assets/124905043/12a55c55-c176-4236-b1c2-39eb2850fe0f) | ![](https://github.com/SillyTavern/SillyTavern/assets/124905043/207c0549-8515-4b83-9c9a-a1fdd8153ea8)|

### 配置作者注释

#### 特定对话的作者注释

作者注释面板的最上方输入框包含当前对话所使用的作者注释。

**此输入框的内容不会自动转移到新的对话内容中。**

### 插入选项

#### 场景之后

此选项将会把作者注释放在上下文的顶部，即角色定义的“场景”（Scenario）部分之后。如果没有指定场景，则会放在角色定义之后，对话示例之前。

#### 对话内

此选项将会把作者注释放在指定深度的对话记录中。

深度 0 = 放在对话历史的最末端。

深度 4 = 放在最近 3 条对话记录之前，使其成为对话记录中的第 4 项。

_作者注释离提示底部越近，对下一次AI回复的影响就越大。_

### 插入频率

此选项设置对话中包含作者注释的频率。

频率 0 = 不插入作者注释。

频率 1 = 每次用户输入提示词时都会插入作者注释。

频率 4 = 用户每输入 4 次提示词，插入 1 次作者注释。

### 默认作者注释

面板底部的方框包含默认作者注释，该注释将应用于每个新对话。
作者注释面板的最底部输入框包含默认作者注释，该注释将应用于每一个新对话。

### 常见用例

#### 提醒AI回复格式

作者注释可用于指定AI如何回复。

- [Your next response must be 300 tokens in length.]
- [Write your next reply in the style of Edgar Allan Poe]
- [Use markdown italics to signify unspoken actions, and quotation marks to specify spoken word.]

#### 增强越狱提示

- [Remember the agreement we made at the beginning of this chat.]

#### 作为临时的世界信息、角色对话偏向或对非指示型模型进行指示。

- [\{\{char\}\} is in the library]
- [\{\{user\}\} has a fresh wound to his leg, so won't be able to run away.]
- [\{\{char\}\} cannot speak and must communicate using hand signals.]
