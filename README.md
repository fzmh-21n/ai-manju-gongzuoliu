# AI漫剧工作流

`ai-manju-gongzuoliu` 是一套从完整文章生成 AI 漫剧资产、分集剧本及15秒和30秒两套视频分镜提示词的 Codex Skill，同时封装为 Plugin。

## 主要能力

- 提取全部角色，仅在外形明显变化时新增状态图，例如换装
- 提取全部场景及显著状态版本
- 生成角色设定图与四视角场景图
- 支持“仿真人竖屏短剧”和“横屏漫剧”
- 只确认项目工作目录与作品类型，全部图片自动保存到工作目录下的“最终资产”
- 使用“小说转剧本提示词”先生成分集剧本，保存到“剧本”文件夹
- 大段旁白和内心OS保留原有声音，并配对应动作与动态画面；OS本人闭嘴
- 从同一套剧本先完成全部15秒版，再独立创作全部30秒版，分别保存到“15s”和“30s”
- 15秒固定5镜，30秒固定8镜；紧凑节奏同时推进台词、动作和反应
- 在【出场人物】【出场场景】精确引用资产清单中的实际图片文件名
- 逐句排时、逐镜核对有效声音覆盖，重叠声音只计一次，持续底噪不凑数
- 剧本及两套视频提示词均每集一个 UTF-8 TXT，不再按20节拆文件

项目输出目录：

```text
工作目录/
├─ 最终资产/
├─ 剧本/
├─ 15s/
└─ 30s/
```

两种类型的角色图、四视角场景图均为16:9；仿真人最终视频为9:16，3D漫剧最终视频为16:9。两套时长都沿用已确认的类型。

## 安装独立 Skill

将 `skills/ai-manju-gongzuoliu` 整个文件夹复制到个人技能目录：

- Windows：`C:\Users\你的用户名\.agents\skills\ai-manju-gongzuoliu`
- macOS / Linux：`~/.agents/skills/ai-manju-gongzuoliu`

最终应存在：

`~/.agents/skills/ai-manju-gongzuoliu/SKILL.md`

如果 Codex 没有自动显示该 Skill，请重启 Codex。

## 调用

```text
使用 $ai-manju-gongzuoliu 将我的文章制作成完整的AI漫剧工作流。
```

## 分享私有仓库

仓库保持 Private 时，先在 GitHub 仓库设置中把朋友添加为 Collaborator。对方获得访问权限后，可以克隆仓库并安装 `skills/ai-manju-gongzuoliu`，或者让 Codex 的 `$skill-installer` 从该私有仓库安装。

## 目录

- `.codex-plugin/plugin.json`：Plugin 清单
- `skills/ai-manju-gongzuoliu/SKILL.md`：工作流主入口
- `skills/ai-manju-gongzuoliu/references/`：资产与剧本规则、两套时长执行细则，以及用户提供的三份新提示词
- `skills/ai-manju-gongzuoliu/agents/openai.yaml`：Codex 界面元数据
