# 易Agent 
0 tokens、0门槛 、轻量级 | 基于 DeepSeek 网页版制作的 Agent —— 让 deepseek "操控"你的电脑。

## 环境要求
- 必须：Edge 浏览器(电脑自带)
- 系统要求：仅Win10/11

## 起源
- 先说一下网络上的项目：
    - `DeepSeek Harness` 等正经的 Agent —— 它们的功能都比 EAgent 强大 100 倍！**但它们都要 API-Key、都要花钱买 token**
    - `网页反代` 等同类非正经的 Agent —— 都通过反代等技术手段实现白嫖 token，功能也很强大，但他们封号概率很大！
    - ...本项目核心是cdp自动化操控、封号概率更小 (但概率不为0，详细划到最底下看声明)

- 再看我的情况：
    - 用 `正经的 Agent` —— 又不搞啥企业级牛逼哄哄的 Agent 工作、也不专业搞计算机，而且这个蓝色大肥鱼有时候他妈的会吃白饭，思考陷入死循环了一直吃干我的 token ，白瞎了几十块钱。所以我一直用免费的 DeepSeek 网页版，小项目也没必要买 token。
    - 用 `非正经的 Agent` —— 又怕反代把我号封了。那我自己搓一个呗。
```
是个硅基生物都知道：DeepSeek 网页无法直接编辑电脑文件。最多生成代码、然后复制粘贴.
非常麻烦，它不能"操控"我的电脑。
我想，直接生成 PowerShell 代码、执行、结果扔回去，不就好了吗？
卧槽对啊，然后问 deepseek 有啥想法，啊...灵光一闪就有了这个项目。
让 DeepSeek 网页版 —— 编辑电脑文件、能看电脑屏幕、能控制你的键盘和鼠标、能编辑 Excel/Word ！...
还能更多，正在持续开发中...
```

## 快速使用
- 下载文件：[点我下载](https://github.com/YaoGaoChaoLe/EAgent/releases)
- 右键 `EAgent.exe`，以管理员身份运行。`而不是直接双击打开`
- 进入程序，点击 `选择工作目录` 按钮，选择一个目录。
- 然后会自动打开 Edge 浏览器，请自行登录后，才能进行下一步操作。
- 点击 `开始新对话` 。等待 Ai 分析提示词...
- 到你回复它了 —— 用 EAgent 发消息，而**不是用网页版发消息**。 `网页版的唯一作用就是给你看的，而不是发消息的。`

---

<img width="1396" height="825" alt="2" src="https://github.com/user-attachments/assets/26816735-55d1-407f-a7b6-9610f889f673" />

---

## 实现原理 —— 自动化脚本
- EAgent **不是反代**、没第三方中转、没逆向 DeepSeek 网页！
- 核心原理是：cdp 自动化模拟用户操作，**和反代一样均违反了 [DeepSeek 用户协议](https://cdn.deepseek.com/policies/zh-CN/deepseek-terms-of-use.html)**。EAgent 的实现原理理论上比反代安全。
```
[ DeepSeek 分析本源码后总结 ]
    用 PowerShell 连接 Chrome/Edge 调试端口，
    通过 CDP WebSocket 在 DeepSeek 页面里执行 JavaScript，
    模拟输入、上传文件、点击发送，并轮询判断助手回复是否完成、返回助手回复信息。
```

## 声明
- 您应该清楚 —— 风险与利益共存，一分钱一分货：
    - EAgent 轻量级的设计：整体只有一个 .exe 文件，大小连 3 MB都不到，仅供学习交流，不适用于生产 (小玩具来的)；
    - EAgent 无安全系统：DeepSeek 可能生成恶意代码、再通过 EAgent 破坏系统，有必要审查 Ai 执行的命令；
    - EAgent 有基础的防风控措施，但是 **极端高频的使用** 仍会被 DeepSeek 限制，作者不承担责任；
- 病毒问题：本项目由 `e语言` 编写，由于其一言难尽的狗屎编译器，使部分杀毒软件误报木马病毒。但我保证：**本项目自身不会带有任何恶意代码，请放心使用。**[微步云-样本分析报告.pdf](https://github.com/user-attachments/files/33975912/_aa1cfadfaf91e60eef30a1400670305089e0cb11eefc07470897802731f74f41.pdf)
- 本项目始于 2026/10/8，处于开发阶段，欢迎提交 [issue](https://github.com/YaoGaoChaoLe/EAgent/issues)。开源仓库 [在这](https://github.com/YaoGaoChaoLe/EAgent/)，遵循 `GPL-3.0` 协议。

```
没事弄了点好玩的：
https://yaogaochaole.github.io/EAgent/Works/liang-skin/
```
