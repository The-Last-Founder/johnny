# Johnny Spec

## Scope

This document defines the functional roadmap for Johnny, starting with version 0.2.

For the clean Johnny repo, the recommended initial structure is:

```text
README.md
SPEC.md
```

Later, once Johnny starts maintaining its own state, add:

```text
memory/
  project.md
  johnny.md
  tasks.md
  ideas.md
  decisions.md
```

## Version roadmap

| Version | Focus | Included |
|---|---|---|
| 0.2 | Basic useful team memory | Group chat, Markdown config, project scope, shared task list, on-demand summaries, weekly summary, basic boundaries |
| 0.3 | Personal interaction and lightweight files | One-on-one chats, personal task filtering, reminders, reading text and Markdown files, better bootstrapping |
| 0.4 | Richer file and artifact support | PDFs, voice transcripts, more boards, wiki layer exploration |
| 1.0 | Agentic teammate | Task extraction, suggestions, smart routing, stronger agent backend, podcast participation |

## Johnny 0.2: MVP

Johnny 0.2 should be the smallest useful version that proves the concept.

### 0.2 goals

- Make the team less likely to drop balls.
- Create a shared source of truth.
- Keep communication concise and useful.
- Preserve attention.
- Stay simple enough to build quickly.

### 0.2 features

#### 1. Group chat presence

Johnny should live inside the team group chat.

Initial behavior:

- Mostly silent by default.
- Responds when tagged or replied to.
- Answers concisely.
- Uses the project context.
- Does not act like a generic chatbot unless that helps the project.

#### 2. Configurable chat behavior

Johnny should have a Markdown file that defines how it behaves in chat.

Future suggested file:

```text
memory/johnny.md
```

This file should include rules such as:

- Be concise.
- Preserve human attention.
- Do not over-explain.
- Stay inside project scope.
- Ask when unsure.
- Use a pleasant, lightweight tone.

#### 3. Project scope file

Johnny should have a project definition file.

Future suggested file:

```text
memory/project.md
```

This file defines:

- What this project is.
- What is in scope.
- What is out of scope.
- Who is involved.
- What Johnny should optimize for.
- What boundaries Johnny should enforce.

#### 4. Shared task list

Johnny should maintain a shared task list in Markdown.

Future suggested file:

```text
memory/tasks.md
```

Suggested fields:

| Field | Description |
|---|---|
| ID | Stable task identifier |
| Title | Short task name |
| Owner | Responsible person |
| Priority | Low, medium, high, urgent |
| Status | Open, in progress, blocked, done |
| Deadline | Optional date |
| Description | Short task context |
| Source | Where the task came from |
| Last updated | Last modification date |

Johnny should be able to show a clean version of the task list in chat and also provide a GitHub link to the raw Markdown file.

#### 5. General table-like Markdown artifacts

The task list is the first use case, but the pattern should generalize.

Future Markdown tables may include:

- `ideas.md`
- `podcast-ideas.md`
- `projects.md`
- `decisions.md`
- `questions.md`

Johnny should eventually support multiple boards, but 0.2 should start with tasks.

#### 6. On-demand discussion summaries

Johnny should be able to summarize recent discussion when asked.

Example:

> I was offline for a day. What did I miss?

This should not be hard-coded as a special action. It should emerge naturally from Johnny having enough conversation context and project awareness.

Summary length should be appropriate to the situation and may later be configurable in `memory/johnny.md`.

#### 7. Weekly summary

Every Sunday at 7:00, Johnny should post a concise weekly summary.

The summary should include:

- What happened last week.
- Key decisions.
- Open tasks.
- Blockers.
- What seems important next week.
- Optional projection for the coming week.

The weekly summary must respect attention. If there is little meaningful activity, Johnny should say so briefly rather than generate filler.

#### 8. Basic boundary enforcement

Johnny should recognize when a request may be outside the project scope.

Example:

> I’m not sure this belongs to this project. Should I track it here anyway?

This should be gentle, not annoying.

## Johnny 0.3: Near-term expansion

### 0.3 features

#### 1. One-on-one conversations

Team members should be able to talk to Johnny privately.

Goals:

- Avoid flooding the group.
- Let each person ask questions privately.
- Let Johnny help one person understand their own tasks.
- Allow Johnny to bring relevant group context into the private chat.
- Allow private conversations to update group artifacts when appropriate.

Important constraint:

Johnny should not leak private content into the group unless explicitly asked or clearly appropriate.

#### 2. Personal task filtering

Johnny should help a person see only their own tasks.

Examples:

- What are my open tasks?
- What is waiting on me?
- What should I do next?
- What tasks are blocked?

#### 3. Reminders

Johnny may remind people about tasks or deadlines.

This should be done carefully to avoid noise.

Possible behavior:

- Reminders are opt-in.
- Reminders happen only for tasks with owners and deadlines.
- Johnny batches reminders when possible.
- Johnny avoids repeated nagging.

#### 4. Reading basic text files

Johnny should be able to read simple text or Markdown files uploaded or linked by the team.

This should include:

- `.txt`
- `.md`
- Simple pasted text
- Possibly GitHub-hosted text files

PDFs and voice recordings are not included in 0.3.

#### 5. Better project bootstrapping

Johnny should support a more intentional setup flow.

It can ask the team questions, then generate or update:

- `memory/project.md`
- `memory/johnny.md`
- `memory/tasks.md`
- Initial artifact structure

## Johnny 0.4: Heavier file and media support

### 0.4 features

#### 1. PDF reading

Johnny should be able to read and summarize PDFs relevant to the project.

#### 2. Voice transcript support

Johnny should eventually handle voice recordings uploaded to chat.

Possible flow:

1. Audio is uploaded.
2. Audio is transcribed.
3. Johnny extracts useful context.
4. Johnny updates relevant artifacts if asked.

#### 3. More artifact types

Johnny can expand beyond tasks into additional structured files:

- Ideas board.
- Podcast episode ideas.
- Decision log.
- Open questions.
- Project roadmap.
- Meeting notes.

#### 4. Lightweight wiki layer

Obsidian or a similar Markdown-based wiki may sit on top of the GitHub files.

This is not required for 0.2, but the file structure should keep it possible.

## Johnny 1.0: More autonomous AI teammate

### 1.0 features

#### 1. Context-to-task extraction

Johnny should detect when a discussion implies an actionable task.

It may suggest:

> This sounds like a task. Should I add it?

The default should still protect attention and avoid too much autonomy.

#### 2. Task suggestions

Johnny may suggest next actions based on project state.

Examples:

- This task has been blocked for a week.
- This decision seems unresolved.
- There are three open podcast ideas but no owner.
- This looks important but is not on the task list.

#### 3. Smarter routing

Johnny should help get the right information to the right person.

Examples:

- If a task is relevant to Alice, surface it to Alice.
- If Sharon needs a decision from Ron, make that clear.
- If the group discussion creates a dependency, mark it.

#### 4. Stronger agent backend

Johnny may use OpenClaw, Hermes-like agents, Claude Code-style workflows, or other agent infrastructure to maintain files, update GitHub, and execute defined routines.

#### 5. Podcast participation

Future Johnny may participate in the podcast as a documented part of the open-source building process.

This is not core to the MVP, but it supports the broader community and movement.

## Open decisions

### Platform

Options:

- WhatsApp
- Telegram
- Slack

Current preference: WhatsApp, because that is where the team already works.

### Infrastructure

Questions:

- Can Yaniv open-source the current bot infrastructure?
- If not, can he help build an open-source equivalent?

### Agent backend

Possible candidates:

- OpenClaw
- Hermes-like agents
- Claude Code-inspired workflow
- Custom lightweight agent

This belongs in the execution phase, not the vision phase.

### GitHub permissions

Decide how Johnny writes to GitHub:

- Direct commits.
- Pull requests.
- Human-approved changes.
- Separate branch per change.

Early default should probably be conservative.

### Autonomy level

Johnny should start low-autonomy.

Default:

- Respond when asked.
- Suggest before acting.
- Avoid noisy interventions.
- Prefer batched updates.

## Success criteria for Johnny 0.2

Johnny 0.2 is successful if:

- The team has a real shared task list.
- Tasks stop getting lost as often.
- The group can ask “what did we decide?” and get a useful answer.
- Weekly summaries are useful and not annoying.
- Johnny’s behavior can be edited through Markdown.
- The system is understandable enough for outside contributors.
- The project is clearly open-source friendly from the start.
