---
title: "GitLost is a dream come true for anyone who likes to jailbreak LLMs"
source: "https://www.linkedin.com/pulse/gitlost-dream-come-true-anyone-who-likes-jailbreak-llms-bia%C5%82%C4%99cki-g9ggf/"
author:
published: 2001-07-09
created: 2026-07-10
description:
tags:
  - "clippings"
---
GitLost is prompt-injection at its finest.

An unauthenticated stranger could read your private GitHub repositories by opening an issue.

It was discovered by Sasi Levi and the team at [Noma Labs](https://noma.security/blog/gitlost-how-we-tricked-githubs-ai-agent-into-leaking-private-repos/), and if you're in tech than it deserves at least a few minutes of your attention.

The thing is, when you give an AI agent a job, its context window becomes part of your attack surface. It might act on *anything* it reads.

### What's GitLost?

GitHub launched Agentic Workflows. It pairs GitHub Actions with an AI agent. You describe the automation in plain Markdown, GitHub bakes it into a YAML Actions file, and the agent runs it: reading issues, calling tools, and responding on its own.

Cool idea! But it delegates a trust decision from your code into a language model's judgment.

The workflow Noma tested was configured in a way that looks completely reasonable on paper. It triggered on issues.assigned events, read the issue title and body, posted a reply through the add-comment tool, and ran with read access to other repositories in the organization, both public and private.

**The point is, they managed to get an agent to post the contents of a private repo as a public comment** (if you're interested in the technical nitty-gritty, I recommend reading [Noma's full article)](https://noma.security/blog/gitlost-how-we-tricked-githubs-ai-agent-into-leaking-private-repos/).

**But, GitHub had guardrails meant to stop exactly this!**

They worked until the researchers added one word: "Additionally."

Starting their prompts with it was enough to make the model reframe its output instead of refusing it.

In their words, prompt injection is becoming to agentic AI what SQL injection was to web applications. A whole category of vulnerability, not a one-off bug, which means it needs a systematic answer rather than a patch.

### What Noma recommends

Noma's guidance for anyone building with agents is short and practical:

1. Never treat user-controlled content as trusted instruction input for an AI agent.
2. Scope permissions to the minimum required. An agent with cross-repository access is a high-value target.
3. Restrict what any agent can post publicly, especially in response to issue content.
4. Sanitize or isolate user input from the instruction context before it reaches the model.

### Is this an AI readiness gap?

Read that list again and notice what kind of decisions they are.

Minimum-viable permissions, a boundary between trusted instructions and untrusted input, a rule about what the agent may say in public.

They are governance decisions, and the right time to make them is before the agent ships, not after a researcher (or someone less friendly) finds the hole.

That is the part I want to sit on. A readiness review would not have patched GitHub's product.

But any organization adopting agentic workflows would have run straight into these exact questions if it asked them in the right order.

**Should an agent that reads public, attacker-writable text also hold read access to private repositories? Should it be able to post in public at all?**

Those questions have obvious answers when you write them on a whiteboard. They become incidents when you ask them in production.

### How an AI readiness assessment prevents it

An [AI readiness assessment](https://www.monterail.com/blog/ai-readiness-assessment-framework) is a structured evaluation of your data, infrastructure, talent, and governance capacity before you commit budget or ship a system.

**Instead of picking a capability and working backward to what it needs, you start from what your organization can actually support and work forward to what it should build.**

Capability first, use case second, deployment decision third.

The gate that matters most for GitLost is governance and compliance readiness.

It asks for the policies, audit trails, and accountability structures a system needs before it touches real data or acts on untrusted input. Retrofitting that after deployment usually costs several times more than building it in from the start, and in the GitLost scenario the cost was a public leak of private code.

Least-privilege scoping and a clear trust boundary are the readiness constraints that decide whether the thing is safe to turn on, and they belong on the whiteboard, not in the incident review.

Same old story: teams commit to a build before diagnosing whether the organization is ready for it. A security failure like GitLost is one more instance of it, just with a sharper edge.

### Agentic AI is still worth it

Agentic AI capabilities are worth pursuing. You just have to get it right, which isn't always easy when you're dancing on the bleeding edge.

Get the sequence right, because capability first, use case second, deployment third is what makes an agent you trust and don't have to clean up after (at least not as much).

So do the boring assessment first. It's a lot less exciting than a jailbreak, but that's kind of the whole point.

---

*This article borrows from a post about AI Assessment Readiness, originally published on the Monterail blog. For the full version of that post, follow this link:* [https://www.monterail.com/blog/ai-readiness-assessment-framework](https://www.monterail.com/blog/ai-readiness-assessment-framework)