# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [3.0.0] - 2026-03-18

### Added
- **Renamed to `devops-pilot`** — new identity: `/devops-pilot` commands
- Authentication verification as mandatory first step in setup wizard
- `gh auth status` check for GitHub CLI authentication
- Jira MCP authentication verification before project selection
- Auth status summary showing all integrations (Jira, GitHub, Git)
- Clear guidance when auth is missing ("Run `gh auth login`")
- Git remote URL and GitHub repo stored in config
- GitHub username stored in config for PR attribution

### Changed
- Setup wizard now starts with auth check (Step 0) before any project selection
- Config validation re-checks auth on every invocation
- All commands renamed from `/rdmss-jira-git` to `/devops-pilot`
- Safety rules expanded to 17 (auth check rule added)

## [2.0.0] - 2026-03-18

### Added
- `triage` command: analyze bug reports, find root cause in codebase, create structured Jira issue
- `create-issue` command: create bugs/features/tasks from natural language
- `create-epic` command: create epic + auto-decompose into child stories from spec
- `create-from-notes` command: extract multiple issues from meeting notes, emails, or messages
- Duplicate detection algorithm: checks Jira + local files before creating any issue
- Root cause analysis: triage traces errors to specific files and lines
- Issue type discovery during setup: maps Bug, Story, Task, Epic IDs
- `root_cause` field in issue frontmatter for triaged bugs
- Structured Jira comment templates for different scenarios
- User confirmation before creating issues: always shows structured preview first
- Commands organized in three categories: Create & Triage, Execute, Manage

### Changed
- Skill identity: from "workflow executor" to "complete dev workflow copilot"
- Setup wizard discovers issue type IDs
- Safety rules expanded to 16

## [1.1.0] - 2026-03-18

### Added
- `comment` command: add Jira comments without closing the issue
- `verify` command: run build/tests before marking done
- `reopen` command: reopen a previously closed issue
- `verifyCommand` config field for automatic pre-close verification
- Conflict detection on `sync`: warns when Jira issue changed since last sync
- Filter support for `sync`: `--assignee`, `--type`, `--label`
- Before & After comparison table in README
- FAQ section with 7 common questions
- Contributing guidelines
- Changelog

### Changed
- All examples genericized: no project-specific data in any file
- `done` command now runs `verifyCommand` if configured before closing
- Improved issue state machine with `reopen` path
- README restructured with better navigation and visual hierarchy

## [1.0.0] - 2026-03-18

### Added
- Auto-discovery setup wizard (site, project, user, transitions, git)
- `sync` command: pull issues from Jira to local markdown files
- `status` command: dashboard with progress by epic and priority
- `plan` command: phased execution plan (bugs first, then features)
- `work` command: assign + create branch + analyze codebase + implement
- `done` command: commit + push + Jira comment + close issue
- `pr` command: create GitHub PR with Jira link
- `batch-done` command: close multiple already-implemented issues
- `close-epics` command: auto-close epics with 100% children done
- `branch` command: Git-only branch creation
- `commit` command: Git-only smart commit
- YAML frontmatter issue tracking with auto-generated INDEX
- Three integration modes: Full (Jira+Git), Jira-only, Git-only
- Conventional Commits with issue key as scope
- Project-locked config for safety
- Offline-first architecture
- 13 safety rules
