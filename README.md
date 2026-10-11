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

## Privacy and scope / 隐私与作用域

This repository contains reusable skill instructions, without personal configuration or task data. Installation alone does not authorize calendar writes. Project rules determine where the skill applies and which actions are authorized.

本仓库保存可复用的 Skill 指令，不包含个人配置或任务数据。安装本身不构成日历写入授权。Skill 的适用范围和操作授权由所在项目的规则确定。
