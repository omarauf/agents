# Agents – Skill Catalog

Personal skill repo for AI coding agents. 36 skills in `skills/`, synced from upstream GitHub repos.

Repo: https://github.com/omarauf/agents

## Sources

| Upstream | Description | Skills |
|---|---|---|
| [mattpocock/skills](https://github.com/mattpocock/skills) | Skills for Real Engineers. Straight from my .agents directory. | 25 |
| [better-auth/skills](https://github.com/better-auth/skills) | Better Auth skill collection. | 4 |
| [shadcn/ui](https://github.com/shadcn/ui) | Composable, accessible components with thoughtful defaults. Build your own component library with code you can customize, extend, and make your own. | 2 |
| [cursor/plugins](https://github.com/cursor/plugins) | Cursor plugin specification and official plugins. | 1 |
| Local (this repo) | Custom skills with no upstream. | 4 |

## Routing & Setup

| Skill | Description | Source |
|---|---|---|
| [ask-matt](skills/ask-matt/) | Ask which skill or flow fits your situation. A router over the skills in this repo. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/ask-matt/SKILL.md) |
| [setup-matt-pocock-skills](skills/setup-matt-pocock-skills/) | Configure this repo for the engineering skills: set up its issue tracker, triage label vocabulary, and domain doc layout. Run once before first use of the other engineering skills. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/setup-matt-pocock-skills/SKILL.md) |

## Planning & Discovery

| Skill | Description | Source |
|---|---|---|
| [grill-me](skills/grill-me/) | A relentless interview to sharpen a plan or design. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md) |
| [grill-with-docs](skills/grill-with-docs/) | A relentless interview to sharpen a plan or design, which also creates docs (ADRs and glossary) as we go. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/grill-with-docs/SKILL.md) |
| [grilling](skills/grilling/) | Grill the user relentlessly about a plan, decision, or idea. Use when the user wants to stress-test their thinking. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md) |
| [research](skills/research/) | Investigate a question against high-trust primary sources and capture the findings as a Markdown file in the repo. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/research/SKILL.md) |
| [prototype](skills/prototype/) | Build a throwaway prototype to answer a design question. Sanity-check a state model, logic, or UI direction. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/prototype/SKILL.md) |
| [wayfinder](skills/wayfinder/) | Plan a huge chunk of work (more than one agent session can hold) as a shared map of decision tickets, resolved one at a time. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/wayfinder/SKILL.md) |

## Building (Spec to Tickets to Implementation)

| Skill | Description | Source |
|---|---|---|
| [to-spec](skills/to-spec/) | Turn the current conversation into a spec and publish it to the project issue tracker: no interview, just synthesis. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md) |
| [to-tickets](skills/to-tickets/) | Break a plan, spec, or conversation into tracer-bullet tickets, each declaring its blocking edges. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md) |
| [to-questionnaire](skills/to-questionnaire/) | Turn a decision you can't fully answer into a questionnaire for someone else to fill in. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/productivity/to-questionnaire/SKILL.md) |
| [implement](skills/implement/) | Implement a piece of work based on a spec or set of tickets. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/implement/SKILL.md) |
| [wizard](skills/wizard/) | Generate an interactive bash wizard that walks a human through steps only they can perform (infra, secrets, dashboards, migrations). | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/wizard/SKILL.md) |

## Quality, Testing & Debugging

| Skill | Description | Source |
|---|---|---|
| [code-review](skills/code-review/) | Review changes since a fixed point along two axes: Standards (coding standards?) and Spec (matches the issue/spec?). Runs as parallel sub-agents. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/code-review/SKILL.md) |
| [tdd](skills/tdd/) | Test-driven development. Use when building features or fixing bugs test-first, or when integration tests are wanted. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/tdd/SKILL.md) |
| [diagnosing-bugs](skills/diagnosing-bugs/) | Diagnosis loop for hard bugs and performance regressions. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/diagnosing-bugs/SKILL.md) |
| [resolving-merge-conflicts](skills/resolving-merge-conflicts/) | Use when you need to resolve an in-progress git merge/rebase conflict. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/resolving-merge-conflicts/SKILL.md) |

## Architecture & Domain

| Skill | Description | Source |
|---|---|---|
| [codebase-design](skills/codebase-design/) | Shared vocabulary for designing deep modules: interface depth, seams, testability, AI-navigability. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/codebase-design/SKILL.md) |
| [domain-modeling](skills/domain-modeling/) | Build and sharpen a project's domain model. Use when discussing terminology, writing CONTEXT.md, or recording ADRs. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/domain-modeling/SKILL.md) |
| [improve-codebase-architecture](skills/improve-codebase-architecture/) | Scan a codebase for deepening opportunities, present them as a visual HTML report, then grill through the pick. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/improve-codebase-architecture/SKILL.md) |

## Auth (Better Auth)

| Skill | Description | Source |
|---|---|---|
| [better-auth-best-practices](skills/better-auth-best-practices/) | Configure Better Auth server and client, database adapters, sessions, plugins, and env vars. | [better-auth/skills](https://github.com/better-auth/skills/blob/main/better-auth/best-practices/SKILL.md) |
| [create-auth-skill](skills/create-auth-skill/) | Scaffold authentication in TypeScript apps using Better Auth: frameworks, adapters, route handlers, OAuth, auth UI. | [better-auth/skills](https://github.com/better-auth/skills/blob/main/better-auth/create-auth/SKILL.md) |
| [organization-best-practices](skills/organization-best-practices/) | Multi-tenant organizations: members, invitations, custom roles, teams, and RBAC via the organization plugin. | [better-auth/skills](https://github.com/better-auth/skills/blob/main/better-auth/organization/SKILL.md) |
| [email-and-password-best-practices](skills/email-and-password-best-practices/) | Email verification, password reset flows, password policies, and hashing for email/password auth. | [better-auth/skills](https://github.com/better-auth/skills/blob/main/better-auth/emailAndPassword/SKILL.md) |

## Frontend & UI

| Skill | Description | Source |
|---|---|---|
| [frontend-design](skills/frontend-design/) | Create distinctive, production-grade frontend interfaces with high design quality. Avoids generic AI aesthetics. | Local |
| [shadcn](skills/shadcn/) | Manages shadcn components and projects: adding, searching, fixing, debugging, styling, and composing UI. | [shadcn/ui](https://github.com/shadcn/ui/blob/main/skills/shadcn/SKILL.md) |
| [migrate-radix-to-base](skills/migrate-radix-to-base/) | Migrates React projects and components from Radix UI to Base UI, single components or whole projects. | [shadcn/ui](https://github.com/shadcn/ui/blob/main/skills/migrate-radix-to-base/SKILL.md) |
| [tanstack-form](skills/tanstack-form/) | TanStack Form best practices for form handling, validation, and user experience in React apps. | Local |
| [html-communication](skills/html-communication/) | Use when the user asks to communicate through an HTML document (plans, reports, UI mocks). | Local |

## Communication & Productivity

| Skill | Description | Source |
|---|---|---|
| [handoff](skills/handoff/) | Compact the current conversation into a handoff document for another agent to pick up. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/productivity/handoff/SKILL.md) |
| [teach](skills/teach/) | Teach the user a new skill or concept, within this workspace. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/productivity/teach/SKILL.md) |
| [triage](skills/triage/) | Move issues and external PRs through triage roles: categorise, verify, grill if needed, write agent-ready briefs. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/engineering/triage/SKILL.md) |
| [unslop](skills/unslop/) | Cut AI tells from any writing. Must always apply. | [cursor/plugins](https://github.com/cursor/plugins/blob/main/pstack/skills/unslop/SKILL.md) |
| [wait-what](skills/wait-what/) | Stop. That last message did not land: re-pitch it with context in simplified technical English. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/productivity/wait-what/SKILL.md) |
| [writing-for-agents](skills/writing-for-agents/) | Writing documents for agents. Use when creating/editing skills or AGENTS.md / CLAUDE.md. | [mattpocock/skills](https://github.com/mattpocock/skills/blob/main/skills/productivity/writing-for-agents/SKILL.md) |
| [postplan-read](skills/postplan-read/) | Use when the user provides a postplan.dev URL to read. | Local |
