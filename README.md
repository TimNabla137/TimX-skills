# TimX skills

**English** | [简体中文](README.zh-CN.md)

Codex Skills built on **Lark CLI** for task assessment, time management, and calendar scheduling in Lark/Feishu.

## Available skills

### tim-daily-planning

Combine **Eisenhower Matrix**, **Time Blocking**, and the **Pomodoro Technique** to assess importance and urgency, estimate effort, batch small tasks, reserve focused work blocks, and schedule recurring work. With explicit authorization, link tasks to calendar events through Lark CLI.

Skill entry point: [`skills/tim-daily-planning/SKILL.md`](skills/tim-daily-planning/SKILL.md). Invoke it with `$tim-daily-planning`.

## Requirements

Use Codex with skill support and an installed, authenticated `lark-cli`. Access personal resources as the user (`--as user`), with the permissions needed to read tasks, OKRs, and calendars. Calendar writes require the corresponding permissions and explicit user authorization. Consult the CLI help for supported commands rather than assuming command syntax.

Provide task and OKR sources, the target calendar, planning dates, time zone, working hours, and authorization through the current project or conversation. The skill instructions guide the workflow; they do not install Lark CLI, configure authentication, or create scheduled automations.

## Suggested daily schedule

Use Cron or a scheduler that runs Codex with this project context to start two daily check-ins. Choose morning and evening times in your own time zone, and invoke `$tim-daily-planning` in each run.

**Morning planning:** Read current tasks, OKRs, and the day's calendar; discuss energy, new commitments, and the most important outcome. Assess priorities and effort, then arrange work blocks within the authorized calendar scope.

**Evening review:** Review actual progress, time spent, blockers, and remaining work. Compare estimates with actual effort and identify tomorrow's most important next step, while preserving evening rest.

Configure the scheduler separately and verify its time zone, project context, skill access, Lark CLI authentication, and permissions. A scheduled run can initiate a discussion, but it cannot supply missing user answers or expand authorization. Installing the skill or reading this README does not create or enable scheduled jobs.

## Privacy and scope

This repository contains reusable skill instructions, without personal configuration or task data. Installation alone does not authorize calendar writes. Project rules determine where the skill applies and which actions are authorized.
