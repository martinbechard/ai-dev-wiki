---
title: "Harness Engineering Masterclass: Technical Deep Dive on how to build Agentic Systems"
source: "https://www.youtube.com/watch?v=mQfTdNVCOB0"
author:
  - "[[The Carbon Layer]]"
published: 2026-05-16
created: 2026-06-30
description: "In this episode, the focus is on demystifying harness engineering for AI agents. The discussion covers the essential components and primitives that make AI systems reliable and safe. Key insights incl"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=mQfTdNVCOB0)

In this episode, the focus is on demystifying harness engineering for AI agents. The discussion covers the essential components and primitives that make AI systems reliable and safe. Key insights include the importance of instructions, context delivery, and context management in shaping model behavior and preventing issues like hallucinations. The episode also explores the role of tool interfaces, execution environments, and durable states in creating dependable AI workflows.

Timecodes

0:00 Introduction to harness engineering and its significance.
1:01 Explanation of the model's role and the concept of hallucinations.
2:39 Definition of an AI agent and the agentic loop.
3:45 Discussion on the importance of instructions as a primitive.
6:15 Context delivery and its impact on model performance.
8:14 Context management and its role in maintaining focus.
10:46 Tool interfaces and their importance in enabling model actions.
12:19 Execution environments and their role in operational control.
14:16 Durable state and its significance in preserving work.
16:19 Orchestration and its role in managing workflows.
18:13 Sub-agents and their function in dividing tasks.
20:20 Skill layers and their importance in providing reusable procedures.
22:20 Verification and observability as key components for reliability.
25:14 Evolution of harness engineering and its impact on AI systems.

Harness engineering transforms clever agents into dependable systems by building reliability into the system around the model.

## Transcript

### Introduction to harness engineering and its significance.

**0:00** · Hello everyone.

**0:00** · Today we'll be trying to demystify what harness engineering is all about.

**0:04** · In particular, I'm talking about the AI agent harness engineering, Um, and so I'll try to walk through all the different uh components and primitives as I'm calling it.

**0:14** · Now, these are not all well defined, these are not something that everyone has agreed upon.

**0:21** · This is just my way of trying to explain what goes in when you use systems like Codex and Claude code, and it's not just the model.

**0:30** · .

**0:31** · So harness engineering, yeah, maybe that's a good way to start, is the system around the model, the model matters.

**0:37** · Like of course it does, which is why we have the whole model wars that we see with all the benchmarks and stuff that goes around.

**0:45** · But once you start building the real agent workflows, the model is only one part of this entire machine.

**0:52** · So the harness gets to decide what the model sees, what it can act on, via tools, of course, um, what it remembers.

### Explanation of the model's role and the concept of hallucinations.

**1:01** · what works get delegated, how and what it verifies, and and overall like how it recovers from a failure.

**1:08** · So this is the deep dive in that topic to reveal uh how the magic as we see uh Claude Code and Codex do and expose the machinery that is uh making that happen, the Center of all of this is the model, ?

**1:27** · and with model, what happens is um you give it a prompt, and model gives you a text, and it gives you a text back, and that in itself is already useful.

**1:39** · Early on, when the whole Chat GPT era was just starting on, um, that's all most of the people did.

**1:46** · they would kind of craft these nice prompts.

**1:48** · And out comes an uh some text, and that text can be used to help you explain a concept, it can help draft a plan, It can even write an email, If you provided uh a good prompt.

**2:01** · and so that is all it was.

**2:04** · It's just basically a model, and you interacted with the model directly via some API.

**2:08** · But this has a boundary, and that boundary is obvious, The model.

**2:12** · only sees what is inside of that prompt.

**2:14** · and all the uh data that it's trained on.

**2:17** · that is what will help it to kind of give you that output or the text, So if your current project or repository or the ticket or incident or workflow is not part of that input, the model will start guessing.

**2:31** · And that's what we call hallucination.

**2:33** · So the first question is not actually that is the model smart, I think the first question is what are we giving it?

### Definition of an AI agent and the agentic loop.

**2:39** · To work with in the first place, What is in the prompt is what the question would become, So if this is the model, what does an agent mean?

**2:47** · So again, the word agent gets thrown around quite a lot.

**2:51** · Um, OpenAI's uh agent SDK defines it as like an LLM or a model that is configured with some instructions and it's provided some tools and it's put into this uh environment that it can uh act on.

**3:04** · Um that's what is the definition of like an agent, and codex and Claude code show the product version of that agent, Um but that loop where it follows Reason, act, observe, and repeat that loop is what we call as the agentic loop, But before we jump in and start talking about the primitives, I think we should clarify three things as to not confuse them, Model, that is a reasoning engine.

**3:30** · Second is this runtime that we just talked about.

**3:33** · That is the loop where the model will observe, decide, call and act on And then third, which is what our deep dive is going to be, the harness itself, That is the system around this runtime.

### Discussion on the importance of instructions as a primitive.

**3:45** · And we'll talk about some of those one by one.

**3:47** · When an agent fails, we usually blame the model, We'll say, like, oh, the model might not be that great.

**3:53** · Um, and sometimes that is true.

**3:55** · Like there is clearly difference between model capabilities and smartness, but often is the it's the layer, one of these components or the layer around it.

**4:06** · it just didn't support the model, And and That's basically what I want to talk about in the rest of the video.

**4:12** · So having said that, let's talk about the first primitive itself, And that is instruction, what does this mean, So you tell the model who it is, you tell it the kind of work that it is doing, you tell it the tone, you tell it the constraints, you tell it the coding styles.

**4:27** · you give it some your rules of how to review the code and things that you it should not do that becomes the instruction that you're giving to the model and so that's why we should treat that as a primitive this is where AGENTS .

**4:40** · md is one form of instruction CLAUDE.md if you're using CLAUDE that fit into this primitive again in the same family you can think of system prompt custom instructions, repository rules that some uh of these agent and agent harnesses support, um, cursor call it cursor rules, So those are all in some form or the other this primitive, this instruction.

**5:02** · They are powerful because they move the repeated guidance that you otherwise would have given to the model into the environment itself, So you As a user, don't have to repeat those things over and over again.

**5:13** · You don't even have to copy paste that instructions all the time.

**5:17** · there is some orchestration, this primitive instruction that uh the harness will take care of.

**5:24** · And so that's why they say, like, hey, AGENTS.md will automatically be provided um to the model.

**5:30** · So Uh instruction are the first harness layer, ?

**5:34** · Because they shape the behavior of anything that happens with the model.

**5:38** · But there is a limit to what instructions can on its own do, Um, so instructions are uh passive, They can say follow the project convention, but they cannot discover those conventions unless those files are available, for example, they can say be careful with like say the the migrations, um, but they cannot inspect the actual migration um itself, Um, and because the agent can't see it.

**6:05** · Instructions help the model to behave better, but they do not give it the entire world.

**6:10** · You cannot give everything, Um so keeping that in mind, let's see what then the next primitive would be .

### Context delivery and its impact on model performance.

**6:17** · And that next one is the context delivery, This context delivery mechanism of the harness gives the model the material that it needs, So you would have used the @ rate symbol to refer to a file Um all of those are in some way or the other this primitive, which is context delivery.

**6:35** · This is where you immediately see the difference between like a bare bone model and an agent working inside this harness that has context delivery.

**6:43** · so because now you you uh can give it a relevant file, You can give it the failing test, you can give the stack trace, and and now you have a very different animal, And so if earlier you used to ask a model to fix a bug with no files, it would give you a generic fix.

**6:57** · But now if you give that source file, you're gonna get a very different answer.

**7:01** · But here We will now start seeing the limitation of this layer as well.

**7:05** · So this alone is also not enough, And so let's see why.

**7:09** · so you have instructions and you have a context delivery where you can make it refer to files and logs and docs, ?

**7:16** · But dumping that in uh is not on on its own context engineering, you might have a chat that is way too long, sometimes your production incident has logs that are like Too long So if you pour all of that into the model, you are not gonna get some really smart thing.

**7:31** · You'll actually see the AI slop as we are all know.

**7:34** · because model has a finite context window, So if you start putting everything, it it cannot hold that.

**7:41** · into its context window, So even inside that window that that model has the attention is not free.

**7:48** · So wrong context sometimes ends up being way much more worse than missing context because it gives the model a plausible distraction.

**7:57** · So the problem now changes.

**7:58** · Like we no longer can ask, can we provide context?

**8:03** · I think we start asking who decides what context matters now, and that's an interesting question.

**8:09** · Harness is is meant to kind of uh help with that aspect of it.

### Context management and its role in maintaining focus.

**8:14** · So yes, we as humans of course play a part in it, but at the same time, there is a lot that harness can do on our behalf, And that brings us to the third primitive, and that is the context management, This is where the management of that context enters, the harness, as you would have seen, does a lot of the stuff to manage that context as to what is the context that the model should be provided.

**8:39** · This means that you might have heard of RAG or retrieval augmented generation.

**8:43** · It might help in that aspect.

**8:45** · uh It might re-rank that thing and figure out which parts of this retrieved chunks to include.

**8:51** · It might summarize at a regular interval.

**8:54** · When it sees that it's reaching the context limit, it might trigger compaction.

**8:59** · You might have heard that word as well.

**9:01** · Putting all of these in in order or in in in a way that it assembles this entire context.

**9:07** · The job basically ends up deciding what enters the model at that particular instance, And that's something small until you try to run a real task, So if a repository is too large and a chat transcript gets too long, if all of that gets dumped into the model, you have not made the agent smarter.

**9:24** · You have made the prompt noisier, So popular names for this show up as context compressors, prompt caches, retrieval rankings, session summaries, compaction.

**9:35** · The name change, but the job is still how do we protect the model's attention?

**9:41** · How do we get the model to focus on the context for it to do the task that we want it to do?

**9:48** · the point is simple that harness is uh managing the attention for the model by context management.

**9:56** · but The context management makes the agent smarter inside the conversation.

**10:01** · it can keep the important parts and summarize the stale parts and retrieve the files at the time, avoid spending half the window on on on noisy context, But the agent is still mostly a talker, It can tell what it would do, it can identify the file, It can propose a command to run.

**10:23** · It can say the next step is for us to run a failing test.

**10:27** · Great.

**10:27** · But at some point, that alone is not enough, If the work requires action, the model needs a way to ask the outside world to do something.

**10:38** · Someone has to then do that act part that the model has decided or identified at that stage.

### Tool interfaces and their importance in enabling model actions.

**10:46** · And that brings us to the next primitive, which is tool interface.

**10:50** · Tools give the model a way to act, It's no longer just uh the agent talking.

**10:56** · this is like structured action that it will take.

**10:59** · A tool would have a name, tool would have a description, It would have schema, um, it may have an output schema as well.

**11:06** · And the model decides that I should call this tool with these arguments, That is the model side of the contract, Um, and if you have seen the rise of MCP, it's it's it's this layer, MCP is useful here because it serves as a way to abstract away how these tools are made available to the model.

**11:25** · It's the model context protocol.

**11:27** · so if anyone any service provider is authoring such mcp mcp servers uh it'll expose their tools to the model for it to then act not just talk so if you have used openai function calling uh or anthropic tool use um MCP tools, bash or grep or find you are using this primitive, Now the model is no longer just describing the work.

**11:52** · uh it can request actions as well but again this also has uh limitations Um say the model correctly decides I should run the test command.

**12:01** · Great.

**12:02** · Where?

**12:02** · On my laptop, in a container, in a cloud sandbox, with network access, with secrets, with write access to the whole repo.

**12:10** · And what about the output?

**12:11** · So tools can fail, tools can return messy text.

**12:14** · Web pages can contain prompt injection, ?

**12:17** · API can return partial data.

### Execution environments and their role in operational control.

**12:20** · The model may choose the tool and valid arguments, but the harness still has to answer the operational question, which is where does this run?

**12:29** · Under what boundaries, and how much do we trust what comes back?

**12:33** · That is the execution environment.

**12:35** · And that is our next primitive, so the execution environment is where the tool calls become bounded reality.

**12:42** · It's the file system scope, network call.

**12:45** · Credentials, sandboxing, containers, browser sessions, cloud workplaces, all of those is what we are putting in this primitive, This is where words that you might have heard of sandbox container, dev container, work tree, browser profile.

**13:00** · there are companies that are formed in for this layer as well.

**13:03** · Uh Daytona uh is one that comes to E2B is another one that comes to mind.

**13:07** · I know Docker now has sandbox, a dev sandbox.

**13:11** · So this is a primitive that we should be thinking of as well.

**13:14** · And it is harness that is providing configuring and collaborating with the tool call and putting it in, and that is what is making it possible basically, this is why running each task in an isolated sandbox matters.

**13:27** · It's not just a deployment detail, it is a harness primitive at this stage.

**13:31** · And the model can ask to run a command, the harness decides where that command runs, What it can see, what it can change, and what it needs in terms of say human approval.

**13:41** · So this layer is also where trust gets practical, we are We are not just telling the model like please do not touch secrets, But instead, at this layer, we can make it such that it does not get secrets, So then environment gives the agent a place to work, but one clean sandbox is not enough for long work, real task sometimes pause, they resume, they fork, They fail sometimes.

**14:04** · and they need a plan, they need a log, they need to record what was tried, they need uh continuity uh so that the next step is where it starts rather than redoing from scratch, if the only place where all of this was stored is inside the model context, yeah, if it crashes or if something happens, we lose it, The system needs something much more durable than yeah I think I remember that one.

### Durable state and its significance in preserving work.

**14:29** · So that brings us to the next primitive that um you would think of when you're creating a custom harness.

**14:35** · And that is durable state.

**14:37** · So durable state is the workbench that survives the current turn, Plan files, checkpoints, task state, where it is in the task, the the session summaries, Uh logs of what it has done, diff, memory stores, all of these.

**14:54** · Right.

**14:55** · Context management decides what gets brought into the model now, but the durable state preserves the facts, the artifacts, the progress outside the prompt so that they can survive the current run.

**15:07** · For coding agents, durable state might be a branch with changes, a test log, a plan document, Or a summary of what failed.

**15:15** · For research agents, it might be a source map.

**15:18** · Or extracted quotes, a confidence table, The important part is not the storage format.

**15:24** · The important part is that the progress becomes inspectable outside the model's current attention, And that is important.

**15:33** · Durable state will preserve work, but it does not coordinate the work, A plan file can say what should happen.

**15:39** · It does not decide what to retry or when to retry.

**15:42** · A lock can be can be recording that a command failed, but it does not decide whether to ask for approval or not.

**15:49** · Similarly, a memory can preserve a lesson, but it does not schedule the next run, So once the workflow has lifecycle, state alone clearly is not enough, You need something that says start here.

**16:01** · Pause there, resume after this, run this check uh after this action, ask the human before the risky step, That part is a whole new primitive, Um and in the agent harness, that primitive will show up as the orchestration, So I have kind of uh zoomed out a little bit here, So we now have all the previous ones showing up.

### Orchestration and its role in managing workflows.

**16:22** · Instructions is there, context delivery is there, context management is there, durable state is there, execution environment, model of course is there.

**16:30** · And now we have another primitive which is orchestration.

**16:34** · Orchestration is the harness deciding how work moves, Life cycle hooks, Heartbeats, as we have seen from OpenClaw and all, retries, approval gates, human handoff, Wrapping the tools, ordering some steps, the task list, routing the model, There is a lot that goes on into this one, So before a tool called do this and after failure, do that, all of that comes becomes part of this particular primitive.

**16:59** · Claude code hooks are a great example of this, Agent frameworks expose lifecycle events because real system needs places to intercept the behavior The model is not doing all of that by willpower, the harness is carrying the workflow, And it's this particular primitive that is doing the busy work.

**17:19** · Um This layer is where the agent work starts to look less like chat and more like a runtime.

**17:25** · but as you have seen the pattern.

**17:27** · Orchestration helps one agent do more, but one agent still has one attention stream, sometimes you need branches.

**17:35** · you might want mid-work someone to go and research something, you know, or go and look inside that Git repository, or draft something on these uh on a separate thing, review the diagrams, uh, verify the browser rendered correctly, If one agent does all of these serially, the process has two issues.

**17:57** · One, it becomes very slow because it happens in serial.

**18:00** · And the second is the context, the thing that we talked about gets crowded, So when work branches, the harness needs to do that branching as well, And that brings us to the next primitive in the harness.

**18:12** · and that one is sub agents.

### Sub-agents and their function in dividing tasks.

**18:14** · Okay.

**18:15** · So not all harness or not all providers uh that are putting out harness even open source one keep this I think if I'm not wrong Pi is a classic example of this where they don't have a built-in sub agent if you want you can add it in Pi but yeah they do serve a purpose Sub-agents let the harness split work into bounded loops.

**18:37** · Now, instead of just one of all of those things that we had, no, it's multiple of those.

**18:41** · One agent explores the code base, one reviews the diff, one verifies sources, one drafts a plan, you get the point, ?

**18:48** · Um, and the main one that fires off all of these things keeps the responsibility for uh integrating all of the output, Um and I think OpenAI's agent SDK has two useful patterns here.

**19:00** · One is agents as tools, So we talked about tools already.

**19:03** · What if you treat agent as a tool as well?

**19:07** · And that basically where you end up with the sub agent Where a manager keeps control and calls the specialists and then hands off Where the active conversation moves to a specialist.

**19:17** · but that's a primitive the primitive is the capability to fire off and branch off with clean context with with the existing context of the main agent.

**19:27** · Um so sub agent is not just more model, it is a model with a narrower job, narrower context, and often narrower tools, Um that's why the term specialists, Um that is why sub agents help Uh as well because they reduce the surface area each worker has to reason about, Remember that whole context and the attention.

**19:47** · Well, that's what the harness is doing via this.

**19:50** · Yeah, the harness is helping say that don't worry about all of these things, you just worry about these tools, you just worry about this aspect of the work that you need to do, and off you go.

**20:00** · And then once it comes back, it integrates all of that stuff, Um But delegation creates a new problem, ?

**20:06** · If every subagent invents its own process, you get parallel inconsistency.

**20:12** · So this is the delegation problem.

**20:14** · It feels faster until everyone comes back with a different interpretation of the job that were given to them, So agents Need procedures, They need reusable know-how that can be loaded at the time.

### Skill layers and their importance in providing reusable procedures.

**20:25** · And a way that the um a primitive for that helps with this particular aspect is the skill layer, It's the skills and procedures basically.

**20:35** · So if these sub-agents are gonna be fired uh to do a very narrow task, wouldn't it be awesome if we can provide uh an exact checklist that it can follow or a procedure that it can follow in a reusable pattern so that every time you want a a narrow sub agent to do that you would just hand off that agent give it a skill off you go so skills are reusable procedures for the recurring work um how to review a PR or a pull request how do you prep for for an for an episode how do

**21:06** · you Use a certain Git repository, How do you do browser checks and tests and so on and so forth?

**21:14** · I think at this stage everyone is very familiar with what skills do, what kind of skills are available.

**21:19** · But you will see this as skills, the slash commands, the playbooks and run books and recipes and workflows, but they are all part of this particular primitive, A good skill will encode a workflow, When to use it, what inputs it should should be given, what steps it would follow, in what order, if need be, which tools to prefer, So they make the harness.

**21:43** · Less dependent on every agent rediscovering the same process from scratch, They move.

**21:48** · repeated expertise from remember to do that thing as instruction into a named capability that the harness can invoke and that's that's important that's why this was a pivotal moment when skill became a thing and of course it became part of our Linux foundation now skills make work repeatable but they do not prove the work succeeded A skill can say run the test, but it the pass, It can say check the browser, was the screenshot clean, So the procedure is necessary, but it is not evidence, And so that primitive is verification and observability.

### Verification and observability as key components for reliability.

**22:24** · Verification asks for receipts, tests, uh builds, type check, lint, browser screenshot, visual inspection, some sort of evals basically, The the agent would say, I am done, and the harness can then ask, Well, show me.

**22:38** · So this is one of the biggest mindset shifts in harness engineering, You do not trust the final sentence because it sounds confident.

**22:45** · You ask what external checks can back it up, For coding work, it's easy.

**22:51** · Like you want a test to run and and and pass, Um for a presentation, it might be a browser screenshot.

**22:57** · With no overlap in text or or so, For research, it might be primary sources and claim table.

**23:03** · I remember my first interaction with agent within a harness, of course.

**23:07** · Um, when I asked it to do some coding task, it automatically said, like, okay, now let me run the test.

**23:12** · And I'm like, wow, that is great.

**23:14** · I didn't have to say it.

**23:16** · And this was even before a skill thing, ?

**23:18** · Um, but that's because the harness was written in a in a way that it uh prompted the model to then look for verification as an extra step.

**23:27** · and for a very long time that was a differentiating factor, And a lot of people attributed that to the model smartness.

**23:34** · And again, that was a component of that.

**23:36** · But harness played a big role in that as well.

**23:39** · If the harness requires verification, it will guide the model to do so.

**23:45** · So in the end, of course, it's a model doing it, but harness played a part in giving it the attention at the time for it to be doing the verification.

**23:54** · Right.

**23:54** · So looks good to me is is not a verification strategy.

**23:59** · it basically needs to have some checks and balances, and then harness can play a part in that aspect as well.

**24:06** · Now, verification tells you whether something passed, it does not tell you.

**24:10** · why it failed, So a test fails, but was it the context that was wrong?

**24:15** · Or did the tool return bad output?

**24:17** · Did the agent edit the wrong file?

**24:20** · Did a sub agent miss a constraint?

**24:22** · Without a run record, debugging becomes hard, And that does not scale, So you need to know what the model saw, what tool it called, what argument it used, what came back and what changed.

**24:35** · And that is the observability part, So observability is the recorder for the agent run, Traces, tool call timelines, logs, cost, latency, prompt versions, tool versions, approval events, The full chain of user intent to the final output, Um, Bug is often not in the final message, it is in one of these in between steps.

**24:56** · It is the three tool calls earlier when the agent searched for the wrong symbol, Or trusted the wrong page or skipped the failing test, Um, and so this observability turns the agent messed up into a debug debuggable system, ?

**25:10** · and this matters because you cannot improve what you cannot inspect, and so Then comes the evolution of the harness itself, This is where failures become infrastructure.

### Evolution of harness engineering and its impact on AI systems.

**25:21** · A repeated context miss might be pointing at something that you need to add, a retrieval rule, ?

**25:28** · A bad tool result becomes a stricter schema.

**25:31** · A dangerous command that you saw in your observability becomes a permission gate that you would add after you saw that.

**25:38** · A missed edge case that you see from your observability.

**25:42** · Becomes a test, a recurring correction that the model has to do might become a memory, And a repeated workflow becomes a skill.

**25:50** · What Hermes agent does.

**25:52** · This is the agent version of the post mortem loop.

**25:56** · Do not just explain the incident, change the system so the class of the failure, same class of failure has a harder time coming back.

**26:03** · The point is not to produce a perfect run once.

**26:07** · point is to make the next run start from a better place.

**26:10** · And without this layer, every agent session becomes the same lesson delivered with a new wrapper, if you will, But with it, the harness will compound.

**26:18** · So this is when the harness engineering becomes more than agent babysitting, if you will, So If you put all of these together, , all of these components that we have talked about, and then you would go back at the time when the articles were discussing and creating architecture of how Claude code is working, you would then realize that this looks very much like that diagram, This at some level is how Claude Code works, and this at some level is how Codex works, and this at some level is how Gemini CLI works, And it is useful now because it should now uh not look like a random complex thing that you see in here.

**26:55** · Each primitive that is listed here has a purpose, it has a meaning, it was put there um for a reason.

**27:03** · That is the payoff that I wanted you to have, Here's a practical test that I would leave everyone with, When an agent fails, do not only ask, was the model good enough, Ask which harness layer ran out of the road, Was the instruction missing?

**27:17** · Was the context wrong?

**27:19** · Did the memory go stale?

**27:20** · Was it tool schema that was vague?

**27:24** · Did the command run in the wrong environment, Did the workflow need state that to be durable, Did it need orchestration?

**27:31** · Should it have been delegated?

**27:32** · Uh was there no skill?

**27:34** · Was there no verification?

**27:35** · or did we not have a trace that allowed us to To all that allows us to look inside.

**27:40** · And did we learn nothing from the last failure?

**27:43** · That is the shift.

**27:45** · Harness engineering is how we move from clever agents to dependable systems, The model is still important, but reliability gets built in the system around the model.

**27:56** · Hope this was helpful.

**27:57** · Thank you.