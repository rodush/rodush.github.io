---
title: "GRAIT: A GitHub-Native Workflow for AI-Augmented Software Development"
date: 2026-11-25T13:05:28+01:00
description: "GRAIT brings engineering discipline to AI-assisted development through a repository-native workflow for issues, testing, implementation, pull requests, and human approval."
categories:
  - AI
  - Programming
tags:
  - AI
  - Software Factories
  - GitHub
  - Coding Agents
---

AI makes it faster to generate code, but faster output does not automatically mean better software.

# Meet GRAIT!

GRAIT is an opinionated, GitHub-native foundation for AI-augmented software development.
It provides reusable agent instructions, specialist roles, engineering conventions, and deterministic workflows that help coding agents work consistently while keeping humans accountable for decisions, approvals, merges, and releases.

GRAIT belongs to the recent movement toward **software factories**: systems that turn development requests into tested, reviewed, and mergeable changes rather than simply generating code snippets or autonomous edits.

It is also close to, and in some areas overlaps with, Anthropic's new built-in Claude Code `/ship` skill.\
Claude Code currently exposes `/ship` as a built-in skill named `ship-local (ship)`, and this has already caused at least one reported naming collision with existing user-defined `ship` skills.

The overlap is conceptual: `/ship` and GRAIT both aim to move work from intent toward a delivered change.\
GRAIT adds an explicit repository and delivery system around that goal.

## GRAIT vs Claude's Ship


| Area | Anthropic's `/ship` | GRAIT |
|---|---|---|
| Scope | A Claude Code built-in skill | A complete repository workflow and setup |
| Main focus | Shipping a task from inside Claude Code | Coordinating the full issue-to-merge lifecycle |
| Work organization | Primarily local/session-oriented | GitHub Issues, Projects, worktrees, branches, and PRs |
| Specialist roles | Not a GRAIT-equivalent repository role system | Triage, test, implement, review, fix, and orchestrator roles |
| Testing | Skill-specific behavior depends on the implementation | Tester-first delivery with independent Red/Green evidence |
| Review | Depends on the skill and configured tools | Independent review identity, formal decisions, and inline findings |
| Publishing | Harness-specific | Separate writer and reviewer GitHub Apps |
| Human authority | Human prompts and approvals remain important | Human approval and merge authority are explicit delivery gates |
| Automation | Built into Claude Code | Deterministic local CLI and optional GitHub Actions |
| Supported harnesses | Claude Code | Codex, Claude Code, and GitHub Copilot CLI |
| Installation | Available through the Claude Code experience | Installed per repository from a pinned Git revision |

In short, `/ship` resembles a compact delivery command for one part of the software-factory pattern. GRAIT is an infrastructure and operating-model implementation of that pattern: it defines backlog readiness, work capacity, role handoffs, worktree ownership, independent verification, PR publishing, review publication, and human merge gates.

GRAIT does not replace engineering judgment. It makes established practices easier to apply consistently when work is delegated to AI agents.

GRAIT is language-agnostic and can be used with a new repository or installed into an existing project without imposing an application framework or language stack.

## Get started

- [Repository](https://github.com/rodush/grait)
- [Installation and configuration](https://github.com/rodush/grait/blob/main/docs/installation.md)
- [Architecture](https://github.com/rodush/grait/blob/main/docs/architecture.md)
- [Workflow](https://github.com/rodush/grait/blob/main/docs/workflow.md)
- [Contributing](https://github.com/rodush/grait/blob/main/CONTRIBUTING.md)
