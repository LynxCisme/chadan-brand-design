# 茶蛋品牌 Skill 安装说明

本 Skill 适用于支持本地 Skills 的 Codex 与 Claude Code。字体和 Logo 都在包内，不能单独移动或删除。

## 最简单的安装方式

在 Codex 或 Claude Code 的对话中发送：

> 请安装这个 Skill：`https://github.com/LynxCisme/chadan-brand-design/tree/main/skills/chadan-brand`

工具会下载并安装该文件夹；安装完成后新开一个对话即可使用。

## 手动安装（仅在自动安装失败时使用）

- **GPT/Codex 本地环境：**使用应用的本地 Skill 导入功能，或将整个 `chadan-brand` 文件夹放入该环境配置的 Skills 目录后重新加载应用。
- **Claude Code：**将整个 `chadan-brand` 文件夹放入 `~/.claude/skills/`，然后重新启动或重新加载 Claude Code。

不同版本的桌面应用对本地 Skill 的导入入口可能不同；如果没有本地 Skill 功能，不能只把 ZIP 上传到普通聊天窗口后期待自动安装。

## 使用

调用 `chadan-brand` 后，再提出具体制作任务，例如：

> 请使用 chadan-brand，把这份内容制作成茶蛋品牌 HTML 演示文稿。

生成 PPT、HTML 或 PDF 时，Skill 要求标题使用寒蝉有机体、正文使用思源黑体；Logo 仅使用 `assets/logos/` 中随包提供的官方文件，不得自动生成或重绘。
