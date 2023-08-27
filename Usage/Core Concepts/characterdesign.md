# 角色设计

### 角色描述

用于添加角色描述和AI需要知道的其他信息。此内容将始终出现在提示词中，因此所有重要的内容都应该在这里交代。

例如，您可以添加有关事件发生的世界的信息，并描述该角色的特征。

角色描述的长度不限（无论200或2000个词元），格式不限（自由文本、W++、对话格式等）。

### 方法和格式

角色格式化方法是一个复杂的话题，超出了本文档页面的范围。

推荐阅读以下指南，他们已经在 SillyTavern 上经过了测试，或者被 SillyTavern 所依赖。

* AliCat's Ali:Chat guide: https://rentry.co/alichat
* kingbri's minimalistic guide: https://rentry.co/kingbri-chara-guide
* Kuma's W++ guide: https://rentry.co/WPP_For_Dummies

### 角色词元

**假设你使用的AI模型限制上下文最多输入 2048 个词元（Token），如果你设定的角色设定包含了 1000 个词元，就相当于将AI的“记忆”削减了一半。**

从这个角度来看，一个表现优秀的AI做出一个像样的回复很容易就会占用 200-300 个词元。在这种情况下，AI只能“记住”大约 3 次聊天记录。

***

### 为什么我的角色词元计数器变成红色了？

当程序发现你的角色设定的词元长度大于模型定义的上下文长度的一半时，程序就会将计数器标红，因为这会降低AI对话的体验。

### 如果我的角色词元过大会怎么样？

首先别慌，这不会造成破坏性问题。在最坏的情况下，如果角色的永久词元过大，只是表示上下文中留给其他事情的空间减少了（见下文）。

这样做唯一的负面影响就是AI的“记忆”会减少，因为它可以处理的聊天记录会减少。

这是因为每个AI模型一次能处理的上下文数量都是有限的。

### “上下文（Context）”？

每次要求AI生成回复时，这些信息都会发送给AI：

* 角色设定
* 聊天记录
* 作者注释
* 特殊格式化字符串
* [括号命令]

在向AI模型发送信息之前，SillyTavern 会自动计算分配可用上下文词元的最佳方式。

### 角色的永久词元是什么？

每次生成请求都会向AI发送这些信息：

* 角色名称（保持名称简短！它会放在每一个角色的消息的开头）
* 角色描述
* 角色性格
* 场景

### 角色设定的哪些部分不是永久性的？

* 第一条消息——只在聊天开始时发送一次。
* 对话示例——只保留到聊天历史填满上下文（可选择强制保留在上下文中）

### 常用的AI模型上下文词元限制

* Older models below 6B parameters - 1024
* Pygmalion 6B, LLaMA 1 models (stock) - 2048
* LLaMA 2 and its finetunes - 4096
* OpenAI ChatGPT (3.5 Turbo) - 4096 or 16k
* OpenAI GPT-4 - 8192 or 32k
* Anthropic's Claude - 8000 (older versions) or 100k (Claude 2)
* NovelAI - 8192 (Kayra, Opus tier; Clio, all tiers), 6144 (Kayra, Scroll tier), or 3072 (Kayra, Tablet tier)

### 性格总结

对角色性格的简要描述。

例子：

* `Cheerful, cunning, provocative`
* `Aqua likes to do nothing and also likes to get drunk`

### 第一条消息

第一条信息很重要，它决定角色的交流方式和风格。

角色的第一条信息应该尽量长，这样之后的聊天就不太可能用很短的信息来回应。

您还可以使用星号 ** 来描述人物的行为。

例如：

`*I noticed you came inside, I walked up and stood right in front of you* Welcome. I'm glad to see you here. *I said with a toothy smug sunny smile looking you straight in the eye* What brings you...`

### 对话示例

描述角色如何对话。在每一个示例前，你应该加上 \<START\> 标签。

* 使用 \{\{char\}\} 而不是角色名称。
* 使用 \{\{user\}\} 而不是用户名称。

例子：

\<START\>

\{\{user\}\}: Hi Aqua, I heard you like to spend time in the pub.

\{\{char\}\}: \*excitedly\* Oh my goodness, yes! I just love spending time at the pub! It's so much fun to talk to all the adventurers and hear about their exciting adventures! And you are?

\{\{user\}\}: I'm new here and I wanted to ask for your advice.

\{\{char\}\}: \*giggles\* Oh, advice! I love giving advice! And in gratitude for that, treat me to a drink! *gives signals to the bartender*

\<START\>

\{\{user\}\}: Hello

\{\{char\}\}: \*excitedly\* Hello there, dear! Are you new to Axel? Don't worry, I, Aqua the goddess of water, am here to help you! Do you need any assistance? And may I say, I look simply radiant today! \*strikes a pose and looks at you with puppy eyes\*

### 场景

互动的环境和背景（情况和上下文）。

### 替换标签（宏）

*发送并生成上下文时被替换的标记列表：*

1. \{\{user\}\} 和 \<USER\> 会被替换为用户的名称。
2. \{\{char\}\} 和 \<BOT\> 会被替换为角色的名称。
3. \{\{time\}\} 会被替换为当前的系统时间。
4. \{\{time_UTC±X\}\} 会被替换为当前的系统时间+指定的UTC时区偏移。 {例如 \{\{time_UTC\-4\}\} 表示时间 UTC-04:00，要表示 UTC+02:00 可以使用 \{\{time_UTC\+2\}\}.
5. \{\{date\}\} 会被替换为当前的系统日期。
6. \{\{idle_duration\}\} 会被替换为一个易于阅读的字符串，表示自上次发送用户信息以来的时间间隔（例如： 4 hours, 1 day）。
7. \{\{random:(args)\}\} 从列表中返回一个随机项。（例如 \{\{random:1,2,3,4\}\} 将随机返回4个数字中的1个）。此功能也适用于文本列表。
8. \{\{roll:(formula)\}\} 通过扔骰子来生成一个随机值，采用龙与地下城的骰子语法：XdY+Z。例如，\{\{roll:d6\}\} 将生成1-6范围内的随机值（标准六面骰子）。

### 添加到收藏夹

按下“星”形按钮，将角色添加到收藏夹，以便在侧边菜单栏上快速筛选。