# 原神·千星奇域 2D 单人小游戏开发

一个面向《原神》千星奇域的 **2D 单人小游戏开发 Skill**，在 Codex 中使用。AI 编写游戏 Lua，并逐步指导你完成编辑器搭建、脚本挂载和试玩。

以电脑键鼠操作、客户端 UI 实现为基础，覆盖玩法设计与实现、概念图还原、动效音效、官方成功结算和试玩排错。搭好通用环境后，可以复用模板、宿主和挂载来制作不同的 2D 单人小游戏。

## 文件结构

```text
genshin-qianxing-2d-game/
├── SKILL.md                 Skill 入口与流程规则
├── agents/openai.yaml       Codex 显示名称与默认提示
├── references/
│   ├── coding-guide.md      AI 编码要求
│   └── editor-guide.md      编辑器操作指南
├── LICENSE                  MIT 许可证
└── README.md                安装与使用说明
```

## 使用条件

- 能读取本地 Skill、生成文件和查阅官方资料的 Codex 环境。
- 可使用千星奇域编辑器及客户端脚本的游戏环境。
- 按指导操作编辑器、提供模板索引，并完成实机试玩。

具体准备步骤见[操作指南](references/editor-guide.md#开始前检查)。

## 项目范围与验证边界

这是一个非官方社区项目，与《原神》或其开发、发行方没有隶属或背书关系。

本仓库提供 Skill 文档与配置，不包含可直接运行的完整小游戏、游戏客户端、导出关卡工程或游戏美术音效素材。使用时由 AI 按你的玩法生成 Lua，你仍需在千星奇域编辑器中完成配置与实机试玩。

基础搭建流程由作者在实际编辑器中验证；这不代表每次生成的代码都已通过实机测试，也不保证适配未来版本。编辑器入口、接口和资源限制可能变化，应结合当前官方资料核对，并实际验证操作、重开和官方成功结算。

## 安装

将下面的内容发给 Codex：

```text
使用 $skill-installer，从以下仓库安装 Skill：
https://github.com/chen-985211/genshin-qianxing-2d-game

分支：main
仓库内路径：.
安装名称：genshin-qianxing-2d-game
请完整保留 SKILL.md、references、agents 和 LICENSE。
```

使用安装脚本时，根目录 Skill 对应 `--path . --name genshin-qianxing-2d-game`。

也可以从[仓库页面](https://github.com/chen-985211/genshin-qianxing-2d-game)下载 ZIP，将包含 `SKILL.md` 的完整目录命名为 `genshin-qianxing-2d-game`，放入用户主目录下的 `.agents/skills/`。若已通过安装器安装在 `.codex/skills/` 等位置，沿用已有位置，避免重复安装。[官方安装说明](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)

安装后开启新对话使用；若未识别到 Skill，重启 Codex。

## 更新

需要更新时，可以直接对 Codex 说：

```text
请从 GitHub 仓库 chen-985211/genshin-qianxing-2d-game
更新我已安装的同名 Skill，使用 main 分支最新版。
找到原安装位置，将旧版备份到技能目录之外，再完整替换，不要重复安装。
```

手动安装的用户可重新下载 ZIP，备份后完整替换原 Skill 文件夹；通过 Git 克隆安装的用户，在确认本地修改已保存后，可在该文件夹运行 `git pull --ff-only`。更新后开启新对话使用。

## 使用

例如，发送：

```text
使用 $genshin-qianxing-2d-game。
帮我在原神千星奇域做一个 2D 单人打砖块小游戏：
鼠标控制挡板，小球击碎砖块，掉落扣生命。
需要碰撞动画、重新开始和官方成功结算。
请一步步指导我搭建编辑器环境，并交付完整 Lua 文件。
```

说明你当前的搭建进度即可；已有模板时，提供文字模板和图片模板的根索引。也可以提供概念图、当前 Lua、错误日志或截图，让 AI 继续实现、调整画面或排错。

- [编辑器操作指南](references/editor-guide.md)：人数设置、模板、宿主、结算节点图、脚本挂载、资源配置和试玩。
- [AI 编码要求](references/coding-guide.md)：接口核查、视觉实现、输入与性能、动效音效、生命周期和官方结算。Skill 要求 AI 在编写或修改 Lua 前完整读取。

## 反馈与贡献

欢迎通过 [Issues](https://github.com/chen-985211/genshin-qianxing-2d-game/issues)反馈问题或通过 Pull Request 改进文档。报告问题时，请说明游戏或编辑器版本、Codex 环境、所在步骤、预期与实际结果，以及最小复现信息。截图、日志和导出文件提交前，请移除账号、UID、个人路径、令牌及其他隐私信息。

修改编辑器流程或接口说明时，请附官方来源与核查日期，并分别说明文档核对、本地检查和实机验证的结果。新增文件应为你有权提交并按本项目许可证分发的内容；不要提交游戏客户端文件、未经许可的素材或含私人数据的工程。

## 许可证

本仓库的 Skill 文档与配置采用 [MIT 许可证](LICENSE)，允许使用、修改、分发和商用，须保留版权与许可声明。

《原神》相关名称、商标及游戏素材的权利归各自权利人所有，本仓库的 MIT 许可证不授予这些第三方内容的使用权。使用游戏及编辑器资源时，请遵守相应平台规则与资源许可。
