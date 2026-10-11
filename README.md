# TimX skills

Codex Skills built on **Lark CLI** for task assessment, time management, and calendar scheduling in Lark/Feishu.

基于 **Lark CLI** 的 Codex Skills，用于飞书中的任务评估、时间管理与日历排程。

## Available skills / 可用技能

### tim-daily-planning

Combine **Eisenhower Matrix**, **Time Blocking**, and the **Pomodoro Technique** to assess importance and urgency, estimate effort, batch small tasks, reserve focused work blocks, and schedule recurring work. With explicit authorization, link tasks to calendar events through Lark CLI.

结合 **Eisenhower Matrix（艾森豪威尔矩阵）**、**Time Blocking（时间块安排法）** 和 **Pomodoro Technique（番茄工作法）**，评估重要性与紧急性、预估耗时、集中处理琐事、预留专注工作块并安排周期性工作。取得明确授权后，通过 Lark CLI 将任务关联到日历日程。

Skill entry point: [`skills/tim-daily-planning/SKILL.md`](skills/tim-daily-planning/SKILL.md). Invoke it with `$tim-daily-planning`.

Skill 入口：[`skills/tim-daily-planning/SKILL.md`](skills/tim-daily-planning/SKILL.md)。使用 `$tim-daily-planning` 调用。

## Requirements / 使用条件

Use Codex with skill support and an installed, authenticated `lark-cli`. Access personal resources as the user (`--as user`), with the permissions needed to read tasks, OKRs, and calendars. Calendar writes require the corresponding permissions and explicit user authorization. Consult the CLI help for supported commands rather than assuming command syntax.

使用支持 Skill 的 Codex，并安装、登录 `lark-cli`。以用户身份（`--as user`）访问个人资源，具备读取待办、OKR 和日历所需的权限。日历写入还需要相应权限及用户明确授权。具体命令以 CLI 帮助为准，不假定命令语法。

Provide task and OKR sources, the target calendar, planning dates, time zone, working hours, and authorization through the current project or conversation. The skill instructions guide the workflow; they do not install Lark CLI, configure authentication, or create scheduled automations.

在当前项目或会话中提供待办与 OKR 来源、目标日历、规划日期、时区、工作时间及授权。Skill 指令用于指导工作流程，不会安装 Lark CLI、配置登录或创建定时自动化。

## Suggested daily schedule / 建议的每日定时安排

Use Cron or a scheduler that runs Codex with this project context to start two daily check-ins. Choose morning and evening times in your own time zone, and invoke `$tim-daily-planning` in each run.

建议使用 Cron，或能够在项目上下文中运行 Codex 的定时工具，每天发起两次讨论。根据自己的时区设置早晚时间，每次运行都调用 `$tim-daily-planning`。

**Morning planning:** Read current tasks, OKRs, and the day's calendar; discuss energy, new commitments, and the most important outcome. Assess priorities and effort, then arrange work blocks within the authorized calendar scope.

**晨间安排：** 读取当前待办、OKR 和当天日历，讨论精力、临时事项及今日最重要的产出。评估优先级与耗时，再在已授权的日历范围内安排工作块。

**Evening review:** Review actual progress, time spent, blockers, and remaining work. Compare estimates with actual effort and identify tomorrow's most important next step, while preserving evening rest.

**晚间复盘：** 核对实际进展、耗时、卡点与剩余工作，对比预估和实际投入，并确定明日最重要的下一步，同时保留晚间休息。

Configure the scheduler separately and verify its time zone, project context, skill access, Lark CLI authentication, and permissions. A scheduled run can initiate a discussion, but it cannot supply missing user answers or expand authorization. Installing the skill or reading this README does not create or enable scheduled jobs.

定时任务需要单独配置，并验证时区、项目上下文、Skill 可读取性、Lark CLI 登录及权限。定时运行可以发起讨论，但不能替用户回答缺失信息或扩大操作授权。安装 Skill 或阅读本说明不会创建或启用定时任务。

## Privacy and scope / 隐私与作用域

This repository contains reusable skill instructions, without personal configuration or task data. Installation alone does not authorize calendar writes. Project rules determine where the skill applies and which actions are authorized.

本仓库保存可复用的 Skill 指令，不包含个人配置或任务数据。安装本身不构成日历写入授权。Skill 的适用范围和操作授权由所在项目的规则确定。
