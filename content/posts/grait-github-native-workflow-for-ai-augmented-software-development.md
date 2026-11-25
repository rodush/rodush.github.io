---
title: "GRAIT: A GitHub-Native Workflow for AI-Augmented Software Development"
date: 2026-11-25T13:05:28+01:00
description: "GRAIT brings engineering discipline to AI-assisted development through a repository-native workflow for issues, testing, implementation, pull requests, and human approval."
draft: true
categories:
  - AI
  - Programming
tags:
  - AI
  - Software Factories
  - GitHub
  - Coding Agents
  - TDD
  - Codex
  - Claude Code
  - Copilot
  - Ship
  - Code Review
  - Automation
  - Workflow
---

AI makes it faster to generate code, but faster output does not automatically mean better software.

I recently [have written about](https://www.rodush.com/posts/collaborating-with-ai-coding-agents-in-github/) how I have created a dedicated identity for my Codex Agent, so I can fully utilize features which GitHub provides to me: PR approval, clear conversation in the comments, branch protection with the rulesets, etc.

While using coding agents, I instruct them to use TDD ([test-driven-development](https://en.wikipedia.org/wiki/Test-driven_development)) approach. To be honest, I am not confident that AI agents actually do follow my instructions strictly.
I have discussed this with some engineers, and we talked about how it would be better to set the strict boundaries and areas of responsibilities, and have the clear handover from one agent to another.

Additionally, I wanted to have some template for the git repository/new project, where I would have a collection of "best practices" skills, agents, instructions, etc., so I don't have to repeat the setup step manually in every other project which I build with AI agents.

So I took this extra mile and ...

# Meet GRAIT

![grait-banner-development-pipeline-assembly-line-humans-with-ai-agents](/images/grait-banner.jpeg#center)

[GRAIT](https://www.github.com/rodush/grait) is an opinionated, GitHub-native foundation for AI-augmented software development.
It provides reusable agent instructions, specialist roles, engineering conventions, and deterministic workflows that help coding agents work consistently while keeping humans accountable for decisions, approvals, merges, and releases.

GRAIT belongs to the recent movement toward *software factories*: systems that turn development requests into tested, reviewed, and mergeable changes rather than simply generating code snippets or autonomous edits.

## How it works

GRAIT makes AI-assisted work visible in the same place your team already manages software: GitHub. Instead of asking one agent to take a task from idea to merge in one opaque step, it gives the work a clear path, with defined handoffs and a human in control.

### 1. Work starts as a GitHub issue

Ask in your AI harness, e.g. Codex CLI, to create the ticket in Project:

![Prompt in Codex CLI with the request to create issue in the Github Project](/images/example-prompt-for-github-issue.png#center)

A request begins as an issue with a clear scope and acceptance criteria:

![Ticket specification automatically created by OpenAI's Gpt-6.2-Sol with High reasoning effort](/images/example-ticket-speced-by-sol-6.2-high.png)

A triage role checks that the work is understood, identifies dependencies, and decides whether it is ready to start. If key details are missing, the issue stays in the **Backlog** until a person clarifies them. Such tickets will be labeled with `agent:needs-human`. Otherwise, the ticket sits in the backlog waiting for `triage` agent to check it and move to **Ready**:

![Ticket in the backlog on the Github Project board](/images/example-ticket-in-project-board.png#center)

**Ready** issues appear on the GitHub Project board. When work is claimed, the issue moves to **In Progress** and GRAIT prepares a dedicated branch and worktree for it.

<!-- Screenshot placeholder: GitHub Project board showing issues moving through Backlog, Ready, In Progress, Review, and Done. -->
<!-- Add your image under /images/ and replace this comment with: ![GitHub Project board showing issue progress](/images/grait-project-board.png#center) -->

### 2. Agents take on focused, separate roles

Rather than treating “the agent” as one all-purpose worker, GRAIT separates responsibilities. For testable work, a tester first adds or updates acceptance tests and records that they fail for the expected reason. The implementer then takes over the **same issue git worktree** and makes the change. Independent validation checks the handoff and the test results.

This separation gives each stage a clear purpose and makes it easier to see what was tested, what changed, and whether the change meets the issue’s acceptance criteria.

### 3. The work is delivered in a pull request

When implementation is ready, the branch is published as a GitHub pull request linked to its issue. The PR is the shared record of the work: it shows the commits and code changes, connects the change back to the original request, and provides a place for review and discussion.

GRAIT uses distinct `writer` and `reviewer` identities for publishing. Agents can prepare changes and publish review findings, iterate on those until comments are addressed, and eventually the reviewer can approve the pull request. But that approval is not enough for the merge, it's more of an official recommendation from the AI agent. Code-owners (repository maintainers) retain the final approve and merge authority.

![Pull request showing agent contributions and review](/images/example-pr-description-mentions-ticket.png#center)

Bots are collaborating in the pull-request, until discussion is settled:

![Pull request showing inline comments made by reviewer and replied by the coder bots](/images/example-bots-collaborating-in-pr.png#center)

### 4. GitHub Checks provide a quick validation summary

The pull request’s **Checks** section shows the status of automated validation on the proposed change. GitHub Actions can run deterministic checks for GRAIT’s configuration and managed files, while the repository can keep its own application tests and build checks.

A passing summary is useful evidence, not a substitute for review: a human still considers the change and approves the merge.

![GitHub Checks summary for a GRAIT pull request](/images/example-checks-summary.png#center)

### 5. Review and merge remain human decisions

A reviewer role examines the pull request and can publish a formal decision with actionable findings. If changes are requested, the issue stays in review while the team (of bots :smile:) addresses them. Once the required checks and reviews are in place, a human reviews and merges the PR. The linked issue can then be completed on the Project board.

The result is a workflow where agents contribute useful work, GitHub keeps progress and evidence visible, and people remain accountable for what ships.


## GRAIT vs Claude's Ship

You might wonder: how is it different or more useful than the recently announced [Claude Ship](https://claude.com/resources/articles/introducing-claude-ship)?

It is close to, and in some areas overlaps with, Anthropic's new built-in Claude Code `/ship` command.\
Claude Code currently exposes `/ship` as a built-in skill named `ship-local (ship)`, and this has already caused at least one reported naming collision with existing user-defined `ship` skills.

The overlap is conceptual: `/ship` and GRAIT both aim to move work from intent toward a delivered change.\
GRAIT adds an explicit repository and delivery system around that goal.

### Comparison table

| Area | Anthropic's `/ship` | GRAIT |
| --- | --- | --- |
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

## Summary

GRAIT does not replace engineering judgment. It makes established practices easier to apply consistently when work is delegated to AI agents.

GRAIT is language-agnostic and can be used with a new repository or installed into an existing project without imposing an application framework or language stack.



## Get started

To get started with the usage and become early adapter, check out the links below:

- [Repository](https://github.com/rodush/grait)
- [Installation and configuration](https://github.com/rodush/grait/blob/main/docs/installation.md)
- [Architecture](https://github.com/rodush/grait/blob/main/docs/architecture.md)
- [Workflow](https://github.com/rodush/grait/blob/main/docs/workflow.md)
- [Contributing](https://github.com/rodush/grait/blob/main/CONTRIBUTING.md)

Yes, it's an MIT-licensed open-source project! Feel free to extend and adjust it per your needs, contributions back are very welcomed!
