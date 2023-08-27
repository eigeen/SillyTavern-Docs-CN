# SillyTavern是什么？

![](https://github.com/Cohee1207/SillyTavern/assets/18619528/8c41a061-7f72-4d2b-9d54-e6d058209e7b)

SillyTavern 是一个本地部署的交互界面，允许你通过文本生成AI（LLM 大语言模型）进行交互，和自定义的角色进行角色扮演。SillyTavern 由 Cohee，RossAscends 和 SillyTavern 社区为你提供。

SillyTavern 于2023年2月基于 TavernAI 1.2.8 版本修改而来，此后引入了很多原版 TavernAI 中不存在的先进功能。

### 截图

| ![Chat](https://github.com/SillyTavern/SillyTavern-Docs/assets/18619528/f750387b-b923-4561-85cf-b86b14e39afd) | ![Waifu mode](https://github.com/SillyTavern/SillyTavern-Docs/assets/18619528/a3d0d020-25a1-4c06-9342-972e43b1ad93) |
|:---:|:---:|
| ![VN Mode](https://github.com/SillyTavern/SillyTavern-Docs/assets/18619528/772d7c7a-0f41-4138-b155-d86b61bf2cce) | ![Backgrounds](https://github.com/SillyTavern/SillyTavern-Docs/assets/18619528/e3df8fcc-edfe-4a5d-8ac6-9462181aad4c) |

### 分支（Branch）

SillyTavern采用双分支系统来确保给所有用户带来一个丝滑的体验，

* 发行版 -🌟 **适用于大部分用户.** 这是我们最稳定也是最推荐的版本, 只有当重大更新发布时才更新。 它适用于大部分用户。
* staging - ⚠️ **Not recommended for casual use.** This branch has the latest features, but be cautious as it may break at any time. Only for power users and enthusiasts.

Learn more [here](https://docs.sillytavern.app/usage/branches/).

### Features

* Mobile-friendly interface
* Multiple backend API connectivity ([KoboldAI](https://github.com/KoboldAI/KoboldAI-Client), [KoboldCPP](https://github.com/LostRuins/koboldcpp), [AI Horde](https://horde.koboldai.net/), [NovelAI](https://github.com/LostRuins/koboldcpp), [Oobabooga's TextGen WebUI](https://github.com/oobabooga/text-generation-webui), [OpenAI](https://chat.openai.com/)+proxies, [WindowAI](https://windowai.io), [OpenRouter](https://openrouter.ai/))
* Visual Novel-like Waifu Mode
* Horde Stable Diffusion generation
* TTS support (ElevenLabs, Silero, and built-in OS)
* WorldInfo (lorebooks)
* Author's Note / Character Bias
* Customizable colors, backgrounds, avatar styles, and UI panel placement
* Notification sound for AI responses
* Export chats as .txt files
* Auto-translate single messages or the entire chat via Google API, even automatically.
* Extensive prompt formatting options
* Character HotSwap buttons to quickly change between your favorite characters
* Prompt token breakdown view for each message
* Swipes
* Group chats: multi-bot rooms for characters to talk to you or each other
* Chat bookmarks / branching
* webp character card interoperability (PNG is still the internal format)

### Extensions

SillyTavern supports extensions/plugins:

* Character emotional expressions
* Auto-Summary of the chat history
* Sending images to chat, and the AI interpreting the content.
* Stable Diffusion image generation (5 chat-related presets plus 'free mode')
* Text-to-speech for AI response messages (via ElevenLabs, Silero, or the OS's System TTS)

Additional functionality can be added by using [SillyTavern Extras](https://github.com/SillyTavern/SillyTavern-extras).

<!-- 
### Screenshots

![](https://user-images.githubusercontent.com/18619528/228649245-8061c60f-63dc-488e-9325-f151b7a3ec2d.png)
![](https://user-images.githubusercontent.com/18619528/228649856-fbdeef05-d727-4d5a-be80-266cbbc6b811.png)
-->

### 安装要求

* SillyTavern 可以在任何支持 NodeJS v18 运行环境的设备上运行。
* **注意**: 由于以上要求，**SillyTavern 不能在 Windows 7 系统上运行。**

### 除了 SillyTavern 本体，我还需要准备什么？

SillyTavern 只是一个前端，所以你需要获取上面列出的其中一个后端API。

### How can I get in touch with the developers directly?

* Discord: Cohee#1207 or RossAscends#1779
* Reddit: /u/RossAscends or /u/sillylossy
* [Post a GitHub issue](https://github.com/Cohee1207/SillyTavern/issues)

### I like your project! How do I contribute?

* We welcome pull requests!
* We also welcome helpful and informed bug reports that use the templates provided in our GitHub.
* We do not accept monetary donations for the project itself.
* Cohee does not take donations.
* RossAscends has a personal [Patreon](https://www.patreon.com/RossAscends) & [Kofi](https://ko-fi.com/rossascends)

### 译者注

此项目翻译由@Eigeen个人完成，目前翻译内容较少，优先翻译部分重要内容。欢迎提交pr贡献翻译。