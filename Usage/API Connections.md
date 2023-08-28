# API 连接

SillyTavern 可以连接多种大语言模型（LLM）API。
下面介绍它们各自的优缺点和使用案例。

## 本地 APIs

- 这些 LLM API 可在个人电脑上运行。
- 它们可以免费使用，没有内容过滤器。
- 安装过程可能比较复杂（**SillyTavern 开发团队不提供相关支持**）。
- 需要从 [HuggingFace](https://huggingface.co/models?other=LLM) 单独下载 LLM 模型，每个模型可能有 10-50GB 大小。
- 大多数模型不如云 LLM API 功能强大。

### KoboldAI

- 可在个人电脑上运行，100% 私有，提供多种模型
- 可最直接地控制AI的生成设置
- 需要大量 GPU VRAM（6-24GB，取决于 LLM 模型）
- 模型限制 2k 上下文
- 无流式传输模式
- 常用的 KoboldAI 版本：
  - [Henky's United](https://github.com/henk717/KoboldAI)
  - [0cc4m's 4bit-supporting United](https://github.com/0cc4m/KoboldAI)

### KoboldCPP

- [GitHub](https://github.com/LostRuins/koboldcpp)
- 功能与 KoboldAI 相同，但使用的是 CPU 和 RAM 而非 GPU
- 在 Windows 上安装非常简单（在 MacOS 和 Linux 上必须从源代码编译）
- 比 GPU API 慢

### Kobold Horde

- 此API可以让 SillyTavern 开箱即用，无需额外设置。
- it uses the GPU of individual volunteers (Horde Workers) to process responses for your chat inputs
- at the mercy of the Worker in terms of generation wait times, AI settings, and available models
- [网站](https://horde.koboldai.net)

### Oobabooga TextGeneration WebUI

- 功能与 KoboldAI 相似，但同时有流式传输和 Gradio 接口
- 支持比 KoboldAI 更广泛的模型类型（4-bit和 8-bit 量化模型）
- 提供一键安装程序
- 经常更新，有时会破坏与 SillyTavern 的兼容性
- [GitHub](https://github.com/oobabooga/text-generation-webui#one-click-installers)

## 云 LLM APIs

- 这些 LLM API 以云服务的形式运行，无需电脑资源
- 它们比大多数本地 LLM 更强大/更智能
- 不过，它们都有不同程度的内容过滤，而且大多数需要付费

### NovelAI

- 没有内容过滤
- 订阅制/按月付费制
- [设置指南](https://docs.sillytavern.app/usage/api-connections/novelai/)

### ChatGPT (by OpenAI)

- 易于设置和获取 API 密钥，提供 4k、8k、32k 上下文模型。
- 免费试用需要一个有效的电话号码
- 免费试用后，所有使用按月付费。
- 角色扮演的写作风格容易重复、可预测。*（译者注：写作套路比较固定，经常复读机。）*
- [设置指南](https://docs.sillytavern.app/usage/api-connections/openai/)

### Claude (by Anthropic)

- 推荐希望自己的AI对话具有创造性和独特写作风格的用户使用
- 提供 4k、8k、100k 上下文模型
- 所有 API 中最强的内容过滤器（截至 2023 年 6 月）
- 对大多数模型的访问受限
- 目前不接受创建新账户；在等待名单上（2023 年 6 月）
- [网站](https://www.anthropic.com/index/introducing-claude)

### WindowAI/OpenRouter

- 该浏览器扩展允许你连接到上述云 LLM
- 在 WindowAI 中使用自己的 ChatGPT/Claude API 密钥
- 使用 OpenRouter 他们提供的的 API 密钥需要付费
- 如果你不想在每个服务上创建单独的账户，这很有用
- [网站](https://windowai.io) 和 [网站](https://openrouter.ai)

### Mancer AI

- 托管无限制模型的服务，无需越狱。
- 使用“点数”支付各种模型的词元。每天可以获得免费的点数。
- 默认情况下不记录提示词，但你可以启用它来获得点数折扣。
- 使用类似于"Oobabooga TextGeneration WebUI "的 API，详见 [Mancer文档](https://mancer.tech/docs/clients/#sampling-parameters)。
- [网站](https://mancer.tech/), [SillyTavern 设置指南](https://mancer.tech/docs/clients/sillytavern/)
