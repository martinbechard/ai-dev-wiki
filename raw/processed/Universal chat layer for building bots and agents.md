---
title: "Universal chat layer for building bots and agents"
source: "https://chat-sdk.dev/"
author:
  - "[[Vercel]]"
published:
created: 2026-07-06
description: "A unified TypeScript SDK for building chat bots with type-safe handlers, JSX cards, and multi-platform support—powered by Vercel"
tags:
  - "clippings"
---
A unified TypeScript SDK for building chat bots with type-safe handlers, JSX cards, and multi-platform support—powered by Vercel

$

npm install chat

general

A

Alice12:00 PM

Has anyone tried the new API?

B

Bob12:00 PM

Yeah, docs look great

```
bot.onNewMention(async (thread) => {
  await thread.subscribe();
  await thread.post("Sure! Here's a quick summary...");
});
bot.onReaction(async (thread, reaction) => {
  await thread.post(\`Thanks for the ${reaction.emoji}!\`);
});
bot.onSubscribedMessage(async (thread, msg) => {
  await thread.post("Checking now...");
});
```

1.5M

Weekly downloads

2.2K

GitHub stars

84+

Contributors

15+

Adapters

### The Platform-Agnostic Chat Toolkit

The open-source chat toolkit designed to help developers build chat bots that run on Slack, Teams, Google Chat, Discord, WhatsApp, and more.

Multi-platform support.

Ship to every chat platform from one codebase.

Event-driven by design.

React to mentions, reactions, and replies.

Type-safe by default.

Strict types for adapters, handlers, and JSX cards.

```
import { Chat } from "chat";
import { createSlackAdapter } from "@chat-adapter/slack";
import { createRedisState } from "@chat-adapter/state-redis";

export const bot = new Chat({
  userName: "mybot",
  adapters: {
    slack: createSlackAdapter(),
  },
  state: createRedisState(),
});

bot.onNewMention(async (thread) => {
  await thread.subscribe();
  await thread.post("Hello! I'm listening to this thread now.");
});

bot.onSubscribedMessage(async (thread, message) => {
  await thread.post(\`You said: ${message.text}\`);
});
```

## Chat SDK Core

A unified API for building event-driven chat bots. Listen for mentions, subscribe to threads, and post rich cards across multiple platforms.

[Visit Documentation](https://chat-sdk.dev/en/docs)

Supports

\+ [more adapters](https://chat-sdk.dev/en/adapters)

### Scale with confidence

Plug Chat SDK into an entire ecosystem designed for AI-native chat experiences that scale.

AI SDK

Build AI agents with streaming, tool calls, and structured outputs.

$ npm i ai

Vercel AI Gateway

Access 100+ models with one API key and no markup.

$ npm i ai

Vercel Sandbox

Build knowledge agents with persistent filesystems to search, index, and read files.

$ npm i @vercel/sandbox

Workflows NEW

Build durable chat agents that suspend, resume, and survive function timeouts.

$ npm i workflow

## Build with Chat SDK today

Get started by exploring the docs, following a guide, or using a template.

[Visit Documentation](https://chat-sdk.dev/en/docs)

$ npx create-chat-sdk@latest

### [Slack Agent Guide](https://vercel.com/kb/guide/how-to-build-an-ai-agent-for-slack-with-chat-sdk-and-ai-sdk)

Stream agent responses and tool calls into Slack threads.

```
bot.onNewMention(async (thread, msg) => {
  await thread.subscribe();
  const result = await agent.stream({
    prompt: msg.text,
  });
  await thread.post(result.fullStream);
});
```

### [Knowledge Agent Template](https://vercel.com/templates/nuxt/chat-sdk-knowledge-agent)

Answer questions from synced docs and repos with file-system search.

```
const savoir = createSavoir({
  apiUrl: process.env.SAVOIR_URL,
  apiKey: process.env.SAVOIR_API_KEY,
});

const { text } = await generateText({
  model,
  tools: savoir.tools,
  maxSteps: 10,
  prompt: "How do I configure auth?",
});
```

### [Code Review Bot Guide](https://vercel.com/kb/guide/ship-a-github-code-review-bot-with-hono-and-redis)

Review pull requests with sandboxed AI analysis on GitHub.

```
bot.onNewMention(async (thread, msg) => {
  const { data: pr } = await octokit.pulls.get({
    owner, repo, pull_number,
  });
  await thread.post("Starting code review...");
  const review = await reviewPullRequest({
    owner, repo,
    prBranch: pr.head.ref,
  });
  await thread.post(review);
});
```