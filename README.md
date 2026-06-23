# Johnny

Johnny is an open-source AI teammate for small teams.

- It lives where the team already communicates, starting with a Whatsapp group chat, and helps the team stay aligned without creating noise. Johnny understands project context, remembers decisions, maintains useful artifacts, and helps each person focus on what matters.

- This project is also a pilot for [something bigger](https://github.com/The-Last-Founder/Build): learning how to build with state-of-the-art AI tools in public, and growing an open-source community that builds useful AI tools together.

## Why are we building this?

We are building Johnny for three reasons:

1. **Build the product**  
   Build Johnny as a useful AI teammate that helps small teams communicate, remember, decide, and execute.
   We are into dogfooding - the first team Johnny will help, is us!

2. **Learn the new AI-native workflow**  
   Learn how to use modern AI development tools such as Claude Code, [cofounder.co](https://cofounder.co/), [Paperclip](https://paperclip.ing/) etc. as well as OpenClaw, Hermes-like agents, and other emerging workflows.

3. **Build an open-source movement**  
   Use Johnny as the first pilot for a broader community that builds AI tools together. The process should be documented publicly, including through [The Last Founder podcast](http://thelastfounder.com/), so others can learn, contribute, and eventually build additional tools with us.

## The pain

Small teams often lose operational momentum.

Current problems we want Johnny to solve:

- Balls get dropped.
- We aren't using any shared task board.
- Actions and projects are not consistently captured.
- It is hard to know what was decided, and what is blocked.
- It is hard to know what is important now.
- People miss context when they are offline.
- Group attention and momentum is fragile and should not be abused.

Johnny should first solve these problems before becoming more ambitious.

## Core principles

### 1. Preserve human attention

Johnny must be a net positive for attention.

It should not flood the group, over-participate, or create more work than it saves. Every new feature should be judged by whether it improves team focus and reduces dropped balls.

### 2. Live where the team already works

The first target is the existing WhatsApp group.

The team is open to moving to Telegram or Slack if needed, but WhatsApp is the most natural starting point and may be useful to many other small teams.

### 3. Open source by default

Everything should be open source wherever possible.

The current WhatsApp bot infrastructure was built by Yaniv. One early task is to talk with him and check whether we can open-source the current infrastructure or build an open-source equivalent with his help.

### 4. Files over black-box state

Johnny should maintain persistent project knowledge in versioned Markdown files, ideally stored in GitHub.

This makes the system understandable, editable, auditable, and open-source friendly.

### 5. Boundaries matter

Johnny is not a general-purpose assistant.

It should know the project scope and gently reject or question inputs that do not belong to the project.

Example:

> I’m not sure this belongs to this project. Should I still track it here?

## Product philosophy

Johnny should not start as a powerful autonomous agent.

It should start as a quiet, useful, versioned memory and coordination layer for a real team. If that works, autonomy can be added later. If that does not work, more autonomy will only create more noise.

## Roadmap snapshot

| Version | Focus |
|---|---|
| 0.2 | Basic useful team memory |
| 0.3 | Personal interaction and lightweight files |
| 0.4 | Richer file and artifact support |
| 1.0 | More autonomous AI teammate |

See [Spec.md](./Spec.md) for the detailed roadmap.

## Success picture

Johnny succeeds if the team feels more aligned, less forgetful, and less overloaded.

The best version of Johnny is not the loudest or smartest possible agent. It is the teammate that quietly helps the team keep its promises.
