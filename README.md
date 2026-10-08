# AI Automation Hub — Franco & Agent Runners

Public GitHub Actions orchestration repository for a set of independent AI automation projects. It runs scheduled workflows in the cloud, so a personal computer does not need to stay switched on.

## What runs here

| Workflow | Responsibility | Connected systems |
| --- | --- | --- |
| `free_franco.yml` | Franco Varela lifestyle / crypto content pipeline | Telegram approvals, content sources, Google Sheets, Buffer / Instagram publishing |
| `free_franco_telegram.yml` | Franco crypto Telegram channel publishing workflow | Telegram channel and bot |
| `free_franco_reel.yml` | Experimental vertical video / Reels pipeline | GitHub Actions and Telegram preview / approval |
| `free_crypto.yml` | Separate experimental crypto trading agent runner | Private agent code, Deriv demo integration, Telegram monitoring |
| `free_money.yml` | Money Agent opportunity research and state persistence | Private `money-agent` repository, GitHub Actions, Telegram where configured |

Additional workflow files support retry, resend and testing of the Franco content pipeline.

## Architecture

```text
GitHub Actions (this public runner repository)
    |
    +-- Franco workflows ------> content pipeline / Telegram approvals / Buffer
    |
    +-- Crypto runner ---------> private trading agent / Deriv demo
    |
    +-- Money runner ----------> private money-agent code
                                   |
                                   +--> opportunity research (read-only)
                                   +--> agent-state branch (JSON/CRM state)
```

The agent projects remain separate. The public repository provides scheduling and execution; it is **not** a public dump of their private code, credentials or customer information. Runtime credentials are supplied through GitHub Actions secrets, not stored in this README.

## Current boundaries

- Money Agent 2.0 discovers *unverified* opportunities; listings are not confirmed income or accepted paid jobs.
- Crypto trading is experimental; no guaranteed performance or returns are implied.
- Content workflows have Telegram approval steps; publication depends on their configuration and platform access.
- Experimental workflows do not imply production readiness.

## Security and operation

- GitHub Actions is used for cloud execution without a permanently running local computer.
- Sensitive tokens are managed via repository secrets.
- Separate workflows keep publishing, opportunity research and trading isolated.
- Inspect the workflow files and Actions history for actual configuration and recent execution status.

Maintained as a practical portfolio of automation workflows and ongoing engineering experiments.
