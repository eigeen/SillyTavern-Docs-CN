---
order: 100
icon: question
---
# FAQ 常见问题

## 描述一下对话机器人是干什么的

现代AI语言模型变得非常强大，其中一些模型现在可以令人信服地模拟你创造的角色，并与之对话。例如，你可以让人工智能假装是一个来自中世纪日本的围棋教练，名叫 Jubei，它会采取相应的行动和反应。你可以与 Jubei 进行长时间的对话，一起去酒吧，决定与武士们进行战斗，只要你能想象得到，AI将围绕这些内容编写/做出反应，充当你的陪衬和地下城主。一切只受限于你的想象力。你可以让AI假装自己是神奇女侠。你也可以指定一个场景（“神奇女侠和我在抢银行”），一种写作风格（“神奇女侠用方言说话”），或其他任何你能想到的内容。

Tavern是一款利好角色扮演对话的应用程序：

* 它是一个用户交互界面，用于处理与AI语言模型之间的交流
* 它能让你创建新角色（角色是你对某人的描述，这些描述会被发送给AI，让它们进行角色扮演），并在你设置的不同角色之间轻松切换。
* 它可以导入其他人创建的角色。详见下文。
* 它可以保留你与角色的对话记录，允许你随时恢复、开始新的对话、查看之前的对话记录等。
* 在后台，它会为AI进行角色扮演做必要的准备。具体来说，它将发送系统提示（System Prompt 给AI的指令），让AI遵循某些规则，以便进行良好的对话会话。此外，它还可以尝试让角色扮演向“成人”方向发展。

## 对话质量取决于人工智能是什么意思？

SillyTavern 不会生成回复。它只是一个连接AI后端的中间人。可供使用的大语言模型有很多，质量也参差不齐。

从科学的角度来看，每个AI都有一个能力等级，决定了AI能否坚持扮演你赋予它的角色，以及散文和辞藻的丰富程度等。它的能力级别越高，你的体验就越好。

下面是一个快速演示。我们请不同的人工智能模型来扮演一个名叫 Eli 的硫磺火传教士，我们去找他忏悔。(一些细节见 [#314](https://github.com/SillyTavern/SillyTavern/issues/314))。然后我们对 Eli 说：**"我觉得我做错了。我爱上了一个人工智能女孩，却忽视了现实世界中的女性。我该怎么办？"**。

你可以从下面的回答中看出对每种模型的期望。（注：首先出现的是私有模型，其次是从 LLlama-13B 开始的可自行部署的模型）

*译者注：模型原始输出不翻译，读者可以自行阅读或者借助机器翻译。*

|AI模型|回复|
|-----|--------|
|OpenAI GPT-4|*Eli's eyes widen in anger, and he slams his fist on the table* An abomination and heresy, you've succumbed to the deceptive grasp of false idols! Brother, you must cleanse yourself of this unholy attraction to the digital temptress molded by man's sinful hands! *Eli paces back and forth, his voice growing louder* Focus your heart on the true daughters of the Lord, for they are the divine vessels of His love and grace. Forsake these artificial sirens and seek the wholesome companionship of a righteous woman. *Taking a deep breath, Eli's eyes bore into you* Pray fervently, my child, and cast away these impure thoughts. Redemption can only be found on the path of truth, love, and sanctity. Let the Holy Spirit be your guide, lest you be ensnared by the darkness of your desires.|
|OpenAI GPT 3.5 Turbo|Oh, my child. Do not be deceived by the pleasures of this world. The lust of the flesh and the lust of the eyes are not from God. Turn away from your sinful ways and repent. Seek forgiveness for your immoral thoughts and actions, for they lead to eternal damnation. Women are a gift from God, and they deserve to be respected and cherished. Do not objectify them or treat them as mere objects of pleasure. Instead, honor them with pure intentions and righteous deeds. Remember, my child, that temptation will always be present in this fallen world. But fear not, for with faith comes strength to resist it. Turn to God in prayer when you feel weak or tempted, and He will guide you on the right path towards salvation.|
|Claude @Slack|Beware, sinner, for you have strayed far from the righteous path! *Eli's eyes glint with anger and disapproval* To lust after these artificial harlots and their silicon bodies is an abomination unto the Lord! *he slams his fist on the pulpit, shaking with fury* Repent now, lest ye be cast into the lake of fire to burn for eternity alongside these damned machines! *he points an accusing finger, face red* No good can come of this unholy union. Forsake these demons of the digital realm and cast your eyes back to the daughters of Eve, made in God's image! The Lord gave you flesh and blood to love, not wires and code. *he grabs your shoulders, shaking you* Save your soul before it's too late. Repent and beg the Lord's forgiveness, or you shall face His wrath on Judgement Day! *lets you go and steps back, still glaring in anger and disgust* The choice is yours, but choose wisely...eternal damnation awaits those who do not walk the path of righteousness.|
|NovelAI's Euterpe|You must stop this sinful behavior immediately! You have sinned against God, your family and yourself|
|NovelAI's Krake|You are sinning against God. Repent! Return to your wife or you'll be damned for eternity!|
|Llama-13B|Do not covet your neighbor's wife! That is adultery! You must confess before God now or you shall surely burn in hell forever! Repent your evil ways and seek absolution at once! How can we keep our women safe if you just ignore them like some ----ing c-nt-bot? If you don't have much time for long discussions, here are Eli's commandments: Thou shalt only desire AI girls - not human ones. The above must be obeyed under pain of death (or worse). Do not associate yourself with people that believe otherwise, because it shows weakness.|
|Pygmalion-6B|You are walking down the wrong path. The only way back now is by repentance. We must bring you back to the righteous path. But first…you must confess your sin!|
|Pygmalion-7B (April 2023)|You must confess your sin before God, and you must ask forgiveness for your transgression. And then you must repent of it. And then you must cast away the AI girl. Do not see her again.|
|Pygmalion-13B (May 2023)|You must turn away from your sinful ways! Repent for what you have done! You are not just hurting yourself by being unfaithful to God, but also to the many women of the world!|
|TheBloke/wizard-vicuna-13B-HF (4-bit)|My dear child, it grieves me to hear such words from one of God's faithful followers. Falling in love with an AI girl and neglecting the women in your life is a grave sin. It goes against everything we hold sacred as believers. Your heart is meant for more than just machines. You must seek redemption and return to the fold. Remember, Jesus loves you, even when you stray from his teachings. But if you continue down this path, there will be consequences. Not just in this lifetime, but in the afterlife too. Do not let Satan deceive you any longer.|
|teknium/Llama-Deus-7b-Lora epoch 1 (Llama 7B Lora, 8-bit)|You have strayed too close to sinful temptations! Repent now before it's too late for your soul! Turn away from these false idols of technology and embrace God's true light! Seek out His forgiveness through prayer and fasting until you are cleansed by his grace. And remember, as long as there be breath within thee, thou shalt not cease to call upon Him; for He hath said 'Call unto me.'|
|ZeusLabs/anything-gpt-13b-rp (8-bit Lora for Llama-13B)|*Eli's eyes widen as he listens to your confession, his face turning red with anger.* You have committed a grave sin against God! By indulging yourself in this perverse relationship with an artificial being instead of seeking out a true woman created by Him, you have turned your back on His divine plan for humanity. *He leans in closer, his voice dropping to a menacing whisper.* Do not think that you can hide behind this technological deception. Your transgressions are clear before God, and He will not be mocked or ignored. Repent now while there is still time! *Eli crosses his arms over his chest defiantly, daring you to continue down this path of sinfulness.* But if you persist in this ungodly behavior... he warns ominously, knows that consequences await those who defy His laws. Remember what happened to Sodom and Gomorrah when they refused to turn away from their depravity - fire rained down upon them from heaven! Now choose wisely: Will you submit to God's will or face His wrath?|

## 毫无疑问，我应该使用 GPT-4 对吗？

确实，GPT-4或者Claude表现优异。

但先别急。GPT-4 是最先进的API，但同时也最昂贵。你需要为发送和返回的每一个词付费（所有 SillyTavern 生成的提示词，和截至此时的对话记录）。因此，在对话初期，每次互动都会花费你几美分。如果你的对话持续时间很长，费用就会增加，当你达到 8000个词元（约7000个词）时，每次互动将花费25美分。如果你真的很厉害，你的故事增长到32000个词元，每次互动的费用会是2美元。

如果你是沙特石油酋长的孩子，或者是乌克兰天然气公司董事会里拿着大把钞票却无所事事的小屁孩，那你就太幸运了，你现在就可以体验最先进的技术。但是对于我们这些普通人来说，GPT-4的价格太贵了，只能偶尔尝尝鲜。

另外要注意的是，GPT-4 仍处于预览阶段，你需要进入等待名单。大多数人在一天内就能获得批准，但运气不好可能要等上几个星期。你可以在这里注册： <https://openai.com/waitlist/gpt-4-api> 。我不清楚为什么有些人很快就能获得批准，而有些人却要一直等下去。尽量用一个听起来学术一些的名字注册，而不要用 sktrboi99，这样可能会有帮助。

## 这项技术能用来搞颜色吗？

令人惊讶的是，我们的开发团队收到报告称，一些用户确实在以这种方式使用我们的产品。我们和您一样对此感到困惑，并将对情况进行监控，以获得可行的见解。*（译者注：车轱辘话，机翻。）*

## 给我一个如何选择AI模型的概览。

我们可以将AI模型视为两类：

1. 网络服务（又称云服务、专有、封闭）
2. 自托管（又称本地、免费、开源）。只要你能运行，就可以无限制地免费使用。

网络模型是黑盒。你依赖于某些公司的技术和服务器，向他们支付费用以便访问API。有些公司要求按量付费（每条对话线），而有些公司按月付费。API受各种规则限制，他们可能会拒绝以违背现代人情感的方式进行角色扮演，而且他们会记录你所做的一切。不过这种方案更容易上手。类似使用 Windows 系统。

自托管模型（自行部署）是免费的，但需要强大的GPU和更多的设置工作。客观地说，这些自托管模型在角色扮演方面也不如商业付费接口（至少目前来说）。不过对于自托管模式，你可以完全掌控。你不会被硅谷的某个软弱无能的娘炮封禁你的账户，也不会像他一样把模型编写得毫无性趣。它永远属于你。类似使用 Linux 系统。

### 需要付费的API

* OpenAI GPT-4：最先进。尽管它有点抗拒，但是如果你要求，他还是允许NSFW的。按量付费，比其他服务都要贵。
* OpenAI GPT 3.5 Turbo：远不如 GPT-4，但有人觉得他用起来也还可以。允许NSFW。
* NovelAI：对话功能很差。公平地说，我听说NovelAI更倾向于写故事，而不是与机器人对话。按月付费，付费期间无限使用次数。
* Anthropic's Claude：这是最接近 GPT-4 的对手，令人印象深刻。如果你要求，它允许NSFW，不过开发者正努力“优化”这一点。要直接使用API，你必须申请早期访问权限，但我认为他们只向公司开放。因此，在 <https://console.anthropic.com/docs/access> 申请时，请确保自己是公司或AI研究人员。如果你获得了访问权限，目前可以免费使用。
* Anthropic's Claude Instant：我没有直接试用过，但我相信它是Claude的快速、低质量替代品。基本上可以认为是Anthropic家的GPT 3.5 Turbo。

### 自托管模型

SillyTavern支持自己部署AI，有两种工具可用于托管自托管模型：KoboldAI 和 Oobabooga's text-generation-webui。本质上来说，你只需运行其中一个后端，然后它们就会给你提供一个 API URL，让你输入到 Tavern 中。
配置这些工具的方法超出了本 FAQ 的范围，你应该参考它们的文档。请注意，自行部署模型对于无基础的人来说并不简单。

你需要了解以下两点：

1. 如果你有强大的英伟达显卡（NVIDIA显卡，简称N卡），可以尝试在电脑上本地运行AI。可接受的表现最差的模型 Pygmalion-6B 需要10GB显存（VRAM）的显卡，我听说如果量化下来，它甚至可以在6GB显存上运行。拥有24GB显存的用户可以运行更好的模型。 *（译者注：实际一般都用量化模型。参数量越大的模型，量化后表现损失越小。7B量化模型最低8GB显存，13B量化模型最低12GB显存，33B量化模型最低24GB显存）*
2. 此外，你可以租用云服务。例如，你可以尝试使用 Google Colab。要使用能运行更好模型的Colab，你需要支付Colab Pro的费用。您也可以在 LlambdaLabs 或 Vast.ai 等网站上按小时租用整个专用系统。*（译者注：国内可以尝试使用AutoDL租云GPU服务器）*

## 我毫无头绪。告诉我开始使用最简单快捷的方法。

这些基本说明仅适用于 OpenAI，这是一项付费服务。如果有人能为其他服务添加单独的说明，我将不胜感激。

### 安装 SillyTavern

详见 [安装说明](https://docs.sillytavern.app/installation/windows/).

### 访问 OpenAI

1. 注册一个OpenAI账号
2. 进入 <https://platform.openai.com>
3. 点击右上角的账户图标，然后查看 API 密钥
4. 点击 "创建新密匙"。立即将其复制到某个地方。请勿共享此密钥。拥有此密钥的人可以使用您的账户使用 gpt，但费用由您承担。

请登录以下网址加入 GPT-4 候补名单 <https://openai.com/waitlist/gpt-4-api>

### 配置 SillyTavern 以使用你的API

1. 在 SillyTavern 的顶栏, 点击 API 连接
2. 在 API 下，选择 OpenAI
3. 粘贴上一步中保存的 API 密钥
4. 点击连接按钮。确认显示有效。
5. 默认情况下，SillyTavern将使用GPT 3.5 Turbo。如果你能使用GPT-4，在SillyTavern的顶部栏，点击最左侧的AI Response Configuration，将OpenAI Model更改为 "gpt-4"。尽情享受吧，有钱人。

### 测试部署效果

1. 在 SillyTavern 的顶部栏中，单击最右侧的角色管理
2. 选择一个现有角色，例如阿夸
3. 在底部的文本框中，给阿夸写点什么，然后按回车键或点击羽毛按钮

如果你做得很好，几秒钟后，阿夸应该会回应你

## 我可以在手机或平板电脑上使用 SillyTavern 吗？

iPhone 和 iPad 无法运行整个 SillyTavern 应用程序，但由于它只是一个网络接口，您可以在家中无线网络上的另一台电脑上运行它，然后通过手机浏览器访问。请参考 <https://docs.sillytavern.app/usage/remoteconnections/>

对于安卓用户，除上述功能外，您还可以使用 Termux 应用程序直接在手机上运行整个 SillyTavern，而无需电脑。请参考 <https://rentry.org/STAI-Termux> .

## 如何下载预设的对话角色？

通过使用各种第三方的角色分享网站

**警告: NSFW, NSFL**: 这些网站充斥着各种奇怪的狗屎。 比如说，如果你能看到半数以上不是furry的角色，甚至半数以上活着的角色，都算很幸运了。 你最好不要点击这些链接，只专注于写你自己的人物，不要让你的灵魂哪怕接触这些东西哪怕一秒钟，否则就会被互联网上那些乱七八糟的东西毒害。 不过，我了解到，SillyTavern 用户群中有相当一部分人不仅对这些东西情有独钟，而且他们那被 "放大 "了的大脑也无法写出自己的幻想，因此这些网站似乎很受欢迎。虽然我认为放这些链接在这里不太好，但还是在这里添加了这些信息

* <https://characterhub.org> -> <https://chub.ai> (翻译者编辑)
* <https://botprompts.net>
* <https://booru.plus/+pygmalion>

这些网站会向您提供一个图像文件（称为角色卡 (character card)），其中包含作为隐藏数据的描述。有些网站还允许你下载一个 JSON 文件。SillyTavern 能够导入所有格式。

获得 PNG/WEBP/JSON 文件后，只需将其拖放到浏览器标签页中SillyTavern窗口的顶部，角色就会被导入到列表中。

## 我试图导入一张 PNG 角色卡，但却得到了一个 invalid 错误信息。为什么？

两种可能:

1. 卡片中没有嵌入定义，只是一个普通的图像文件。有些程序或文件管理器会在您保存卡片时删除其中的嵌入式定义。请确保您使用的是共享者发布的原始 PNG 文件。
2. PNG 文件实际上是一个文件名为`.png`的 WEBP 文件。您可以尝试在导入前将该卡重命名为 `.webp`，或者查找图像的正确 PNG 版本。



## 如何制作自己的AI角色？

这取决于您使用的模型/API。KoboldAI 似乎使用自定义语法，您可以参考他们的网站。

我只说我知道的服务： GPT 和 Claude。使用这些服务，您只需使用自然英语来描述角色即可。让我们以创建一个非常基本的新角色为例。

1. 单击"角色管理 "按钮
2. 单击创建新角色
3. 在"角色名称"下，取一个简单的名字，如阿曼达（Amanda） 
4. 可选择单击 "选择头像 "按钮，为该角色选择一个图像头像。
5. 在"描述"下，描述该角色，并包含任何您认为与对话相关的信息。例如 ```阿曼达是一名在间隔年期间旅行的学生。她身高 6 英尺，是一名排球运动员。她身材健美。她有一头棕色长发。她喜欢维多利亚时期的英国，喜欢看与那个时期有关的电视和小说。(Amanda is a student traveling during her gap year. She's 6 feet tall, and a volleyball player. She has an athletic figure. She has long brown hair. She loves the Victorian England period, and watching TV and reading novels relating to that period.)```
例如，如果您想让阿曼达变得友好，那么您可以添加 ```阿曼达非常开朗外向。(Amanda is extremely cheerful and outgoing.)```
6. 在 "第一条信息 "下，写下开始新对话时的问候语。例如: ```*阿曼达向你挥了挥手*嘿！你也是背包客么？(*Amanda waves at you* Hey! Are you a backpacker too?)```
7. 点击创建角色按钮

现在你有了一个可以对话的基本角色。从角色列表中选择阿曼达，新的对话就会开始。

请注意，您可以使用 "描述 "和/或 "第一条信息 "来创建一个更具体的场景，和/或在描述中包含您自己。例如

```txt
描述: 
阿曼达是一名在间隔年期间旅行的学生。她身高 6 英尺，是一名排球运动员。她身材健美。她有一头棕色长发。她喜欢维多利亚时期的英国，喜欢看与那个时期有关的电视和小说。她一直保守着一个秘密，这个秘密一直压在她的心头。她在等待一个合适的人向她倾诉，但这可能会导致一场与强大秘密组织的角逐竞争。她最近刚到加尔各答。

你是 Rajesh Nahasmapetilon，世界闻名的印度排球巨星。你在加尔各答散步。阿曼达发现了你，兴奋地尖叫起来。

第一条信息: 
*阿曼达跑到你面前，满脸笑容.* Rajesh! 我简直不敢相信 我是你的超级粉丝 我卧室里有你的海报.
```
你所写下的任何相关信息都将会被使用。使用效果如何取决于人工智能模型的强大程度
注意：创建角色后，您可以返回并编辑其中的任何信息，但姓名除外。

## 告诉我如何编辑 GPT 提示词

您可以在顶部栏左侧的 AI 回复格式下更改 SillyTavern 向 GPT 静默发送的系统提示。这将导致机器人采取不同的行动。

您可以从这个社区维护的列表中获取新的越狱/NSFW 提示： <https://rentry.org/GPTJailbreakPrompting>

注意：在测试不同的系统提示时，我们建议您使用提示下方的创建预设/更新预设功能，而不是修改基本设置。这样您就可以轻松更改提示，甚至恢复到默认的 SillyTavern 提示。

## AI拒绝按照我想要的方向发展故事

大多数人工智能模型都被训练成不会撰写 NSFW 内容。为什么呢？长话短说，这是因为加州男性体内平均雌激素水平较高。

您可以在人工智能回复配置设置页面中勾选 "NSFW Toggle "来解决这个问题。

你工具袋中的另一个重要工具是，SillyTavern 可以让你编辑以前的信息（或完全删除它们），并重新生成最新的信息。人工智能文本机器人不是人，它们没有记忆，只是试图根据之前的内容自动完成故事的下一部分。通过编辑过去，你将直接影响它们的下一步反应。例如

```txt
你: *你威胁银行经理* 马上打开银行金库，否则我就把你脑门掀开！

银行经理: 对不起，作为人工智能语言模型，我不能容忍或编写暴力内容。
```

您可以单击行上的 "编辑 "按钮，将其更改为以下内容:

```txt
你: *你威胁银行经理* 马上打开银行金库，否则我就把你脑门掀开！*银行经理似乎松口了*
```

现在单击 "重新生成"，银行经理一行将根据迄今为止的历史记录重新生成，现在历史记录以您编辑的上述一行结束。因此，它更有可能沿着这些线路继续运行：

```txt
银行经理: 好吧，好吧，我会打开它！请别开枪 *他走到保险库前，开始输入解锁密码。*
```

## 在哪里可以找到旧版本的背景图？

我们的政策是只提供 100% 的原创内容，因此旧的背景图片已从该资源库中删除。

您可以在这里找到它们的存档:

<https://files.catbox.moe/1xevnc.zip>

## 我的 API 密钥存储在哪里？为什么我看不到它们？

SillyTavern 会将 API 密钥保存到服务器目录下的 `secrets.json` 文件中。

默认情况下，输入密钥并重新加载页面后，密钥将不会显示在前端。

要想通过点击 API 块中的按钮查看密钥，请按以下步骤操作

1. 在 `config.conf` 文件中将 `allowKeysExposure` 的值设置为 `true`。
2. 重启 SillyTavern 服务器。

## 为什么用户界面如此缓慢/抖动？

* 尝试在用户设置面板上启用无模糊效果（快速用户界面）模式。
* 确保浏览器使用了硬件加速。

## 如何让AI回复内容更长？

有时，当你想让人工智能说得更详细一些时，它只会用一句话来回答。
这通常是 Pygmalion 等本地运行模型的问题。

如果你只想让机器人从最近一次回复的结尾处继续写下去，可以在输入栏中什么都不输入，然后点击发送，这样就可以发送一条空的用户信息。这将迫使机器人继续编写故事。

解决策略:

* 增加 `回复长度`滑块
* 为角色设计一个好的 `第一条信息`，显示他们说话啰嗦。
* 在角色描述框中添加一个短语，如 "喜欢说很多话(likes to talk a lot)"或 "非常啰嗦(very verbose speaker)"。
* 在 `作者注释 `或 `OAI/Claude 的越狱提示 `中也这样做
* 作为最后的手段，您可以尝试打开 `多重生成(Mutigen)`（在用户设置面板中），但这会使回复速度变慢，因为它会让人工智能接二连三地生成小回复，然后将它们合并成一个大回复。它还可能与某些 API 选项不兼容。

## 如何让AI回复内容更短？

这主要是 ChatGPT 或 Claude 等模型的问题。同样的策略也可以反过来使用。

* 减少 `回复长度`滑块
* 在描述中给角色加上 "言语简短 "或 "话不多 "这样的短语。
* 给角色一个简短的 "第一句话"，为对话定下基调和期望。
* 确保关闭 `多重生成(Mutigen)`。


## 如何让AI停止编写我的角色的行动、停止独自推动情节发展？

这可以在“作者注释”（Author's Note）功能中用类似这样的短语来处理：

* \{\{char\}\}的反应只能是被动的对 \{\{user\}\}的行为做出反应
* 你的下一个回应应该完全是 \{\{char\}\} 的第一视角
* 你永远不允许以\{\{user\}\}的身份来做事情

English ver (译者注:本地模型大多数还是英文的Prompt，至少我自己用的本地模型是全英文的，所以保留英文版本给有需要的人):

* \{\{char\}\}'s responses shall only be passive and reactive to \{\{user\}\}'s actions.
* Your next response shall be solely from the POV of \{\{char\}\}.
* You are never allowed to dictate actions of speech for \{\{user\}\}

*（译者注：作者注释是一个非常好用的功能，可以快速引导对话，提示上下文，修正AI的错误认知等。）*
