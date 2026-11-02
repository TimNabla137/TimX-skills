# TimX skills

[English](README.md) | **简体中文**

可复用的 Codex Skills，用于提示词优化、任务评估、时间管理与日历排程。其中，任务规划技能通过 **Lark CLI** 操作飞书。

## 可用技能

### tim-opt-prompt

把原始要求改写成专业、具体、可验证的提示词，同时保留原任务范围。先回答顶尖专业实践、原始材料、具体方法与工具、外部验收证据四个问题，再用一个完整文本代码块交付可复制的提示词。

Skill 入口：[`skills/tim-opt-prompt/SKILL.md`](skills/tim-opt-prompt/SKILL.md)。使用 `$tim-opt-prompt` 调用。

- **适用场景：** 优化、重写或深化既有提示词；普通任务执行、单纯润色和翻译不触发。
- **输出内容：** 针对当前任务的四问回答，以及可独立使用的完整提示词；语言与原始要求一致，默认中文。
- **范围边界：** 保留原目标、交付物、约束与授权，明确缺失证据和假设，不编造调研或验证结果。执行重写后的任务需要用户授权。
- **使用条件：** 支持 Skill 的 Codex。提示词改写本身不依赖 Lark CLI 或其他外部工具；原任务所需的候选工具取决于实际环境。

调用示例：

```text
使用 $tim-opt-prompt 优化下面的要求：
“检查这个新用户引导流程，提出改进建议。”
保持现有流程范围，不增加功能。我可以提供页面截图、客服反馈与转化数据。
请先回答四个问题，再给出可直接复制的完整提示词，暂不执行评审。
```

### tim-daily-planning

结合 **Eisenhower Matrix（艾森豪威尔矩阵）**、**Time Blocking（时间块安排法）** 和 **Pomodoro Technique（番茄工作法）**，评估重要性与紧急性、预估耗时、集中处理琐事、预留专注工作块并安排周期性工作。取得明确授权后，通过 Lark CLI 将任务关联到日历日程。

Skill 入口：[`skills/tim-daily-planning/SKILL.md`](skills/tim-daily-planning/SKILL.md)。使用 `$tim-daily-planning` 调用。

## 使用条件

以下 Lark CLI 条件及定时安排建议适用于 **tim-daily-planning**。

使用支持 Skill 的 Codex，并安装、登录 `lark-cli`。以用户身份（`--as user`）访问个人资源，具备读取待办、OKR 和日历所需的权限。日历写入还需要相应权限及用户明确授权。具体命令以 CLI 帮助为准，不假定命令语法。

在当前项目或会话中提供待办与 OKR 来源、目标日历、规划日期、时区、工作时间及授权。Skill 指令用于指导工作流程，不会安装 Lark CLI、配置登录或创建定时自动化。

## 安装技能

克隆仓库，将所需的技能目录复制到 Codex 的 skills 目录。以下示例安装 `tim-opt-prompt` 到当前用户目录：

```sh
git clone https://github.com/TimNabla137/TimX-skills.git
cd TimX-skills
mkdir -p ~/.codex/skills
cp -R -i skills/tim-opt-prompt ~/.codex/skills/
```

如果自定义了 `CODEX_HOME`，请改用其下的 `skills` 目录。交互式复制会在覆盖已有文件前询问。安装后开启新的 Codex 会话，使用 `$tim-opt-prompt` 并附上待优化要求。安装规划技能时，将目录名替换为 `tim-daily-planning`。

## 建议的每日定时安排

建议使用 Cron，或能够在项目上下文中运行 Codex 的定时工具，每天发起两次讨论。根据自己的时区设置早晚时间，每次运行都调用 `$tim-daily-planning`。

**晨间安排：** 读取当前待办、OKR 和当天日历，讨论精力、临时事项及今日最重要的产出。评估优先级与耗时，再在已授权的日历范围内安排工作块。

**晚间复盘：** 核对实际进展、耗时、卡点与剩余工作，对比预估和实际投入，并确定明日最重要的下一步，同时保留晚间休息。

定时任务需要单独配置，并验证时区、项目上下文、Skill 可读取性、Lark CLI 登录及权限。定时运行可以发起讨论，但不能替用户回答缺失信息或扩大操作授权。安装 Skill 或阅读本说明不会创建或启用定时任务。

## 隐私与作用域

本仓库保存可复用的 Skill 指令，不包含个人配置或任务数据。安装本身不构成日历写入授权。Skill 的适用范围和操作授权由所在项目的规则确定。
