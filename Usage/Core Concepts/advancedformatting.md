# 高级格式设置

通过本节提供的设置，可以对提示词构建策略进行进一步控制。

### 上下文模板

**这里的大部分设置不适用于对话补全 API，因为它们由提示词管理系统控制。**

通常，AI模型需要以某种特定方式提供角色数据。SillyTavern 包含一份针对不同模型的预设转换规则列表，但你也可以根据自己的喜好进行定制。

#### Story string

此字段是聊天前角色数据（内部称为 story string）的模板。
这是为文本补全和指示模型而格式化角色卡的主要方式。

该模板支持 Handlebars 语法和任何自定义文本注入或格式化。请参见此处的语言参考：https://handlebarsjs.com/guide/

我们为 Handlebars evaluator 提供了以下参数（将它们置于双花括号中）：

1. `description` - 角色描述
2. `scenario` - 角色背景
3. `personality` - 角色性格
4. `system` - [指示模式] 系统提示词或覆盖角色的主要提示词（如果存在且“首选角色卡提示”在用户设置中启用）
5. `persona` - 选定的用户角色描述 *（译者注：即当前选中的代表用户输入的角色）*
6. `char` - 角色名
7. `user` - 选定的用户角色名
8. `wiBefore` or `loreBefore` - 合并后的激活的“世界背景”条目，并且插入位置为“角色设定前”
9. `wiAfter` or `loreAfter` - 合并后的激活的“世界背景”条目，并且插入位置为“角色设定后”

**警告**: 如果 story string 模板中缺少上述某些参数，则根本不会在提示词中发送这些参数。

#### 对话示例分隔符

用作块标题和示例对话块之间的分隔符。示例对话框中的任何`<START>`标记都将用该字段的内容替换。

#### 开始回复

作为分隔符插入在渲染完成的 story string 之后和示例对话块之后，但在上下文中第一条信息之前。

#### 始终在提示词中添加角色名称

将角色的名称附加到提示词中，强制模型以角色的身份完成对话：

```
** 其他的上下文 **
Character:
```

### 分词器 Tokenizer

分词器是一种将一段文本分解成称为 Tokens 的较小单元的工具。这些 Tokens 可以是单个词，甚至是词的一部分，如前缀、后缀或标点符号。根据经验，一个 Token 一般对应 3 到 4 个字符的文本。

SillyTavern 提供了一个“最佳匹配”选项，它会根据所使用的 API 提供商，使用以下规则尝试匹配分词器。

文本补全 API **（可覆盖）**：
1. NovelAI Krake/Euterpe: GPT-2/3 tokenizer.
2. NovelAI Clio: NerdStash tokenizer.
3. NovelAI Kayra: NerdStash v2 tokenizer.
4. TextGen / KoboldAI / AI Horde: LLaMA tokenizer.

如果你得到的结果不准确或想进行试验，你可以设置一个 *override tokenizer*，让 SillyTavern 在向AI后端发出请求时使用：

1. None。每个 Token 估计约为 3.3 个字符，四舍五入到最接近的整数。**如果你的提示词在上下文过长时被截断，请试试这个。** KoboldAI Lite 采用的就是这种。
2. GPT-3 tokenizer。**在 Turbo 之前的 OpenAI 模型（ADA、Babbage、Curie、Davinci）中使用。**更多信息：[OpenAI Tokenizer](https://platform.openai.com/tokenizer)。
3. （旧版）GPT-2/3 tokenizer。由原版 TavernAI 使用。**如果不确定，请选择这个。**更多信息： [gpt-2-3-tokenizer](https://github.com/josephrocca/gpt-2-3-tokenizer).
4. LLaMA tokenizer。由 LLaMA 1/2 系列模型使用：Vicuna、Hermes、Airoboros 等。**如果使用 LLaMA 1/2 模型，请选择**。
5. NerdStash tokenizer。由 NovelAI 的 Clio 模型使用。**如果使用 Clio 模型，请选择**。
6. NerdStash v2 tokenizer。由 NovelAI 的 Kayra 模型使用。**如果使用 Kayra 模型，请选择**。
7. API tokenizer。通过调用查询 API，直接从模型中获取 Token 计数。只有 Oobabooga's TextGen 支持。**如果使用最新版本的 TextGen API，请选择**。

聊天补全 API **（不可覆盖）**：
1. OpenAI / Claude / OpenRouter / Window：通过 [tiktoken](https://github.com/openai/tiktoken) 计算取决于模型的 Token。
2. Scale API： GPT-4 tokenizer。
3. Fallback tokenizer（用于代理）：GPT-3.5 turbo tokenizer。

### Token 填充

**重要：本部分不适用于 OpenAI API。SillyTavern 将始终为 OpenAI 模型使用匹配的 tokenizer。**

SillyTavern 无法使用在 KoboldAI 或 Oobabooga's TextGen 远程实例上运行的模型所提供的恰当的 tokenizer，因此在生成提示词时假定所有 token 数量都是根据所选的 [分词器 Tokenizer](#分词器-Tokenizer) 类型估算的。

由于 tokenization 的结果在上下文大小接近模型定义的最大值时可能会不准确，提示符的某些部分可能会被截断或删除，这可能会对角色设定的一致性产生负面影响。

为避免出现这种情况，SillyTavern 会分配一部分上下文大小作为填充，以避免添加的聊天内容超过模型所能容纳的范围。如果你发现即使选择了最匹配的 tokenizer，提示词的某些部分也会被截断，那么请调整填充，这样描述就不会被截断。

您可以为反向填充输入负值，这样就可以分配比设定的最大 token 还要多。

## 自定义停止字符串

Accepts a JSON-serialized array of stopping strings. Example: `["\n", "\nUser:", "\nChar:"]`. If you're unsure about the formatting, use an [online JSON validator](https://jsonlint.com/).

Supported APIs:

1. KoboldAI (versions 1.2.2 and higher)
2. oobabooga's Text Generation WebUI
3. NovelAI
4. OpenAI, including via OpenRouter (max 4 strings)

接受一个序列化的 JSON 数组，用于停止序列。例如：`["\n", "\nUser:", "\nChar:"]`。如果不确定格式，请使用 [在线 JSON 验证](https://jsonlint.com/)。

支持的 API：

1. KoboldAI（1.2.2 及更高版本）
2. oobabooga's Text Generation WebUI
3. NovelAI
4. OpenAI，包括通过 OpenRouter（最多 4 个序列）

### Multigen

*此特性提供的伪流式传输功能与 token 流式传输功能相冲突。当启用 Multigen 且 API 支持流式传输时，将仅使用 Multigen 流式传输。*

SillyTavern 尝试通过使用较小批次的链式生成来创建更快、更长的响应。

#### 默认设置

First batch = 50 tokens

Next batches = 30 tokens

#### 算法

1. 生成第一批（如果设置的生成量大于批长度）。
2. 生成下一批 tokens，直到达到其中一个停止条件。
3. 将生成的文本附加到下一个周期的提示词中。

#### 停止条件

1. Generated enough text.
2. The character starts speaking for You.
3. &lt;|endoftext|&gt; token reached.
4. No text generated.
5. Stop sequence generated. (Instruct mode only)

1. 生成足够的文本。
2. 角色开始为你说话。
3. 遇到了 &lt;|endoftext|&gt; token。
4. 未生成文本。
5. 生成了停止序列。（仅限指示模式）
