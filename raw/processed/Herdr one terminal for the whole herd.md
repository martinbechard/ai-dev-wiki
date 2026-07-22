---
title: "Herdr: one terminal for the whole herd"
source: "https://herdr.dev/"
author:
published:
created: 2026-07-18
description: "Herdr is to coding agents what tmux is to terminals: an agent multiplexer that runs where your agents run. Real panes, agent state at a glance, ssh from anywhere, no app."
tags:
  - "clippings"
---
opencodeherdr+

```
▐▛███▜▌
▝▜█████▛▘
  ▘▘ ▝▝
```

**Claude Code** v2.1.198

Fable 5 with high effort · Claude Max

~/Projects/herdr/website

**❯** make the herdr.dev hero mock look exactly like real claude code

● Ha. I read the real pane over the socket — the mock was on v2.1.168, Claude Code is v2.1.198 now. Missing the logo block and the whole rate-limit row.

● Plan:

· index.html — swap ✻ for the real ▐▛███▜▌ mark, bump the version

· css/style.css — coral bypass line, add the 5h / Week bars

**❯** perfect. and make the dialogue about this, obviously

⠴ Baking… (13m 40s · esc to interrupt)

**❯**

~/Projects/herdr/website > master \* ↑1 > ctx ──────── 3% 31k/1M

⏵⏵ bypass permissions on (shift+tab to cycle)

~/Projects/herdr *master*

**❯** bun run dev

$ node scripts/prepare-docs.mjs && astro dev

02:10:44 \[types\] Generated 0ms

02:10:44 \[content\] Synced content

astro v5.18.1 ready in 668 ms

┃ Local http://localhost:4321/

Network use --host to expose

02:10:44 watching for file changes...

\+ Thought: 468ms

→ Read src/main.rs

\+ Thought: 292ms

This is src/main.rs — the entry point for **herdr**. Here's what it does:

1\. Arg parsing — session::configure\_from\_args, then remote args for the SSH bridge.

2\. Subcommand dispatch — server, client, update — each returns early.

3\. Session mode — auto\_detect\_launch() connects to a running server or spawns one.

Build · MiMo V2.5 Free · 16.6s

Build · MiMo V2.5 Free OpenCode Zen

25.2K (13%) ctrl+p commands

migratelogs+

```
▐▛███▜▌
▝▜█████▛▘
  ▘▘ ▝▝
```

**Claude Code** v2.1.198

Fable 5 with high effort · Claude Max

~/Projects/llm-proxy

**❯** prep the request-log migration and run it

● Wrote migrations/0007\_request\_log.sql — request\_log table, retention index on created\_at, daily rollup view.

● Local checks pass: sqlx prepare is clean, backfill dry-run touches 41,209 rows. Ready to apply.

**Bash command**

cargo sqlx migrate run

Apply pending database migrations

Do you want to proceed?

❯ 1. Yes

2\. No, and tell Claude what to do differently (esc)

~/Projects/llm-proxy *master*

**❯** tail -f logs/proxy.log

02:30:58 INFO request id=4818 route=/v1/messages 200 312ms

02:31:04 INFO request id=4819 route=/v1/messages 200 287ms

02:31:09 DEBUG cache hit ratio 0.93

02:31:12 INFO request id=4820 route=/v1/messages 200 301ms

02:31:15 WARN upstream latency p99 1.8s

02:31:18 INFO request id=4821 route=/v1/messages 200 295ms

02:31:21 WARN 429 from upstream, retrying in 2s

02:31:24 INFO request id=4822 route=/v1/messages 200 1102ms

02:31:30 DEBUG cache hit ratio 0.94

02:31:33 INFO request id=4823 route=/v1/embeddings 200 88ms

codexserver+

• **Explored**

└ Read live\_handoff.rs

• **Ran**

└ cargo nextest run -E 'test(live\_handoff)'

└ 14 passed · 0 failed · 41.3s

• The handoff suite passes. Pane PTYs survive server replacement, and long-lived workloads — including the http.server in the next tab — keep responding afterward.

• Next I can wire the soak test into nightly CI and fail on p95 regressions. Want that?

**›**

gpt-5.5 medium · ~/qmp · master · Context 6% used

~/qmp *master*

**❯** python3 -m http.server 8080

Serving HTTP on 0.0.0.0 port 8080...

02:28:41 "GET /runs/latest.json" 200

02:29:03 "GET /runs/latest.json" 200

02:29:25 "GET /qmp/report.html" 200

02:30:07 "GET /runs/latest.json" 200

02:30:18 "GET /favicon.ico" 404

02:30:42 "GET /qmp/report.html" 200

02:31:09 "GET /runs/latest.json" 200

The whole herd in one terminal. Click the sidebar, it's a real layout.

## Watch Herdr through other developers' workflows.

Independent walkthroughs from Jilles, DevOps Toolbox, and Better Stack. See how Herdr feels as a tmux-style multiplexer for coding agents, remote sessions, and day-to-day agent orchestration.![Thumbnail for Jilles' Herdr in about 6 minutes video](https://i.ytimg.com/vi/qnIu-Xu64H0/maxresdefault.jpg)

Thumbnail for Jilles' Herdr in about 6 minutes video

[Jilles · 6:37 Herdr in about 6 minutes The fastest practical intro: install, workspaces, agent states, persistence, and the agent skill workflow.](https://www.youtube.com/watch?v=qnIu-Xu64H0)[![Thumbnail for DevOps Toolbox's This Tmux Rewrite Is Actually Brilliant video](https://i.ytimg.com/vi/5GtkyPvuvbQ/maxresdefault.jpg)

Thumbnail for DevOps Toolbox's This Tmux Rewrite Is Actually Brilliant video

DevOps Toolbox · 16:40 This Tmux "Rewrite" Is Actually Brilliant A deeper hands-on look at the full package: mouse-first panes, remote use, agent support, and the CLI.](https://www.youtube.com/watch?v=5GtkyPvuvbQ)[![Thumbnail for Better Stack's Herdr agent multiplexer video](https://i.ytimg.com/vi/PlN86TvzGy4/maxresdefault.jpg)

Thumbnail for Better Stack's Herdr agent multiplexer video

Better Stack · 7:10 Is This the Ultimate Agent Multiplexer? A clear tmux comparison with agent awareness, remote attach, and why Herdr stays inside your terminal.](https://www.youtube.com/watch?v=PlN86TvzGy4)

## Run agents where the work is. Attach from anywhere.

Agents run wherever the work is: a server, a Mac Mini, a sandbox VM, anywhere you can ssh. You attach from any terminal, even a phone. Desktop agent managers can't leave the machine with the GUI. Herdr can. [Why switch from an app →](https://herdr.dev/compare/)

### Your machine

Split panes, create tabs, and keep agents running while your terminal comes and goes.

```
$ herdr
```

### Like tmux, on the server

SSH in and run Herdr on the remote shell. The session stays after you detach, ideal from a phone SSH client.

```
$ ssh you@server
$ herdr
```

### Native remote attach

A local client to a remote session. Installs Herdr on the host for you, bridges your local clipboard (including image paste), and keeps your keybindings.

```
$ herdr --remote workbox
```

### Mobile-first when the terminal gets small.

Herdr stays usable over SSH from a phone or tablet. The terminal view remains real, while narrow screens get a switcher built for touch-sized decisions.

![Herdr agent session over SSH on a phone](https://herdr.dev/assets/mobile-agent-session-v2.jpeg)

agent session over SSH

![Herdr responsive switch menu on a phone](https://herdr.dev/assets/mobile-switch-menu-v2.jpeg)

responsive switch menu

screenshots taken with [moshi](https://getmoshi.app/) ❤️ on iPhone

## Most agent managers are apps. Herdr is a multiplexer.

tmux and Zellij own persistent terminal sessions but don't understand agents. Desktop agent apps understand agents but live on one machine. Herdr keeps the multiplexer in your terminal and makes it agent-aware. [See the full comparison →](https://herdr.dev/compare/)

not a terminal emulator

Ghostty, Kitty, iTerm, Alacritty: your terminal stays.

not a browser dashboard

No web view, no account, no hosted control plane.

more than tmux for agents

Persistence plus clickable panes, agent state, an API.

### Runs inside your terminal

tmux/Zellij **✓** agent apps **—** worktree apps **—** Herdr **✓**

### Persistent PTY sessions

tmux/Zellij **✓** agent apps **limited** worktree apps **embedded** Herdr **✓**

### Remote SSH attach

tmux/Zellij **✓** agent apps **limited** worktree apps **remote projects** Herdr **✓**

### Semantic agent state

tmux/Zellij **—** agent apps **partial** worktree apps **workspace status** Herdr **✓**

### Direct agent attach

tmux/Zellij **—** agent apps **—** worktree apps **—** Herdr **✓**

### Agents can orchestrate it

tmux/Zellij **scriptable** agent apps **partial** worktree apps **workflow-owned** Herdr **✓**

## Make it yours.

Review diffs beside the agent. Approve from your phone. Navigate like vim. Watch your agents graze as pixel-art sheep. If herdr doesn't do it, one of 249 community plugins does, or you publish your own with one GitHub topic.

$ `herdr plugin install <owner>/<repo>`

\# any public repo tagged herdr-plugin

249 community plugins, auto-discovered from GitHub

[smarzban/ **herdr-file-viewer** Git-aware file tree, diffs, and rendered markdown in a side pane. ★ 158 · Rust](https://github.com/smarzban/herdr-file-viewer) [persiyanov/ **herdr-reviewr** Review the agent's diff, comment on lines, send notes back to its prompt. ★ 138 · Rust](https://github.com/persiyanov/herdr-reviewr) [paulbkim-dev/ **vim-herdr-navigation** Ctrl+h/j/k/l moves seamlessly across herdr panes and vim splits. ★ 44 · Shell](https://github.com/paulbkim-dev/vim-herdr-navigation) [yuk1ty/ **herdr-spreader** Whole workspace layouts, tabs, panes and commands, from one YAML file. ★ 40 · Rust](https://github.com/yuk1ty/herdr-spreader) [AltanS/ **collie** A phone PWA for your herd over Tailscale, with push when an agent needs you. ★ 54 · TypeScript](https://github.com/AltanS/collie) [ragamo/ **herdr-flock** Your agents as pixel-art sheep on a farm. Ended sessions rest in the graveyard. ★ 7 · Rust](https://github.com/ragamo/herdr-flock)

## Real panes, agent state, and an API to drive them.

No rebuilt chat view. Real processes in real PTYs, with clickable layout, persistent sessions, and a control surface your agents can use themselves.

### Real panes

Mouse-first panes, tabs, and workspaces. Keep your shell, fonts, and keybinds.

### Agent state

Blocked, working, done, and idle at a glance across the whole session.

### Persistence

Detach and reattach. Sessions and agents survive the terminal closing.

### Control surface

A CLI and JSON socket API expose workspaces, panes, output, and waits.

```
# create workspace structure
herdr workspace create --cwd ~/project --label api
herdr tab create --label logs

# split a pane and run work
herdr pane split 1-1 --direction right
herdr pane run 1-2 "just test"

# wait, inspect, and continue
herdr wait agent-status 1-1 --status done
herdr pane read 1-2 --source recent-unwrapped
```

[CLI reference →](https://herdr.dev/docs/cli-reference/) [Socket API →](https://herdr.dev/docs/socket-api/) [Agent skill →](https://herdr.dev/docs/agent-skill/)

## Bring your existing agents into the herd.

Pi

Claude Code

Codex

Droid

Amp

OpenCode

Grok CLI

Hermes

Cursor

Antigravity

Kimi

Kiro

Copilot

Qoder CLI

MastraCode

[\+ yours](https://herdr.dev/docs/integrations/)

Any terminal agent works out of the box. [Integrations](https://herdr.dev/docs/integrations/) add richer state and session resume.