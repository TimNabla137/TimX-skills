# TimX skills

**English** | [简体中文](README.zh-CN.md)

Reusable Codex Skills for prompt optimization, task assessment, time management, and calendar scheduling. The planning skill uses **Lark CLI** to work with Lark/Feishu.

## Available skills

### tim-opt-prompt

Turn a rough request into a professional, specific, verifiable prompt while preserving its original scope. First answer four questions about expert practice, primary sources, concrete methods and tools, and external evidence; then deliver a complete prompt in a copyable text block.

Skill entry point: [`skills/tim-opt-prompt/SKILL.md`](skills/tim-opt-prompt/SKILL.md). Invoke it with `$tim-opt-prompt`.

- **Use for:** optimizing, rewriting, or deepening an existing prompt. Ordinary task execution, light copyediting, and translation do not trigger this skill.
- **Output:** four task-specific answers followed by a standalone rewritten prompt, in the language of the original request (Chinese by default).
- **Boundaries:** preserve the original goal, deliverables, constraints, and authorization. Identify missing evidence and assumptions; do not invent research or validation results. Executing the rewritten task requires user authorization.
- **Requirements:** Codex with skill support. No Lark CLI or other external tool is required for prompt rewriting itself; tools proposed for the underlying task depend on the available environment.

Example invocation:

```text
Use $tim-opt-prompt to improve this request:
"Review this onboarding flow and suggest improvements."
Keep the scope within the existing flow; do not add features. I can provide
screenshots, support tickets, and conversion data. First answer the four
questions, then provide a complete prompt I can copy. Do not execute the review.
```

### tim-daily-planning

Combine **Eisenhower Matrix**, **Time Blocking**, and the **Pomodoro Technique** to assess importance and urgency, estimate effort, batch small tasks, reserve focused work blocks, and schedule recurring work. With explicit authorization, link tasks to calendar events through Lark CLI.

Skill entry point: [`skills/tim-daily-planning/SKILL.md`](skills/tim-daily-planning/SKILL.md). Invoke it with `$tim-daily-planning`.

## Requirements

The following Lark CLI requirements and scheduling suggestions apply to **tim-daily-planning**.

Use Codex with skill support and an installed, authenticated `lark-cli`. Access personal resources as the user (`--as user`), with the permissions needed to read tasks, OKRs, and calendars. Calendar writes require the corresponding permissions and explicit user authorization. Consult the CLI help for supported commands rather than assuming command syntax.

Provide task and OKR sources, the target calendar, planning dates, time zone, working hours, and authorization through the current project or conversation. The skill instructions guide the workflow; they do not install Lark CLI, configure authentication, or create scheduled automations.

## Install a skill

Clone this repository and copy the desired skill folder into your Codex skills directory. For example, from the repository root, install `tim-opt-prompt` for your user:

```sh
git clone https://github.com/TimNabla137/TimX-skills.git
cd TimX-skills
mkdir -p ~/.codex/skills
cp -R -i skills/tim-opt-prompt ~/.codex/skills/
```

If you use a custom `CODEX_HOME`, use its `skills` directory instead. The interactive copy asks before replacing existing files. Start a new Codex session after installation, then invoke `$tim-opt-prompt` with the request you want to improve. Replace the folder name with `tim-daily-planning` to install the planning skill.

## Suggested daily schedule

Use Cron or a scheduler that runs Codex with this project context to start two daily check-ins. Choose morning and evening times in your own time zone, and invoke `$tim-daily-planning` in each run.

**Morning planning:** Read current tasks, OKRs, and the day's calendar; discuss energy, new commitments, and the most important outcome. Assess priorities and effort, then arrange work blocks within the authorized calendar scope.

**Evening review:** Review actual progress, time spent, blockers, and remaining work. Compare estimates with actual effort and identify tomorrow's most important next step, while preserving evening rest.

Configure the scheduler separately and verify its time zone, project context, skill access, Lark CLI authentication, and permissions. A scheduled run can initiate a discussion, but it cannot supply missing user answers or expand authorization. Installing the skill or reading this README does not create or enable scheduled jobs.

## Privacy and scope

This repository contains reusable skill instructions, without personal configuration or task data. Installation alone does not authorize calendar writes. Project rules determine where the skill applies and which actions are authorized.
