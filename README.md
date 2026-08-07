# AI漫剧工作流

`ai-manju-gongzuoliu` 是一套从完整文章生成 AI 漫剧资产与视频分镜提示词的 Codex Skill，同时封装为 Plugin。

## 主要能力

- 提取全部角色及显著状态版本
- 提取全部场景及显著状态版本
- 生成角色设定图与四视角场景图
- 支持“仿真人竖屏短剧”和“横屏漫剧”
- 两套导演提示词绝对隔离，禁止混用
- 在分镜中准确引用角色图和场景图的原始资产名
- 按自然剧情节点拆分正文，保持完整台词和连续动作
- 每20节输出一个 UTF-8 视频提示词文件

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
- `skills/ai-manju-gongzuoliu/references/`：七步规则、两套导演提示词和示例资源
- `skills/ai-manju-gongzuoliu/agents/openai.yaml`：Codex 界面元数据
