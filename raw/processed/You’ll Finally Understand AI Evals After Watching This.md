---
title: "You’ll Finally Understand AI Evals After Watching This"
source: "https://www.youtube.com/watch?v=12WN6u2DrBk&list=PLdVLOietcHTD3OjLupQ6oEQWEeKXLVozO&index=21"
author:
  - "[[Mastra]]"
published: 2026-06-18
created: 2026-06-23
description: "What's the difference between an eval and a test? By the end of this video, you'll know the difference with confidence.📚 RESOURCES- Mastra docs: https://mastra.ai/docs/💬 JOIN THE MASTRA COMMUN"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=12WN6u2DrBk)

What's the difference between an eval and a test? By the end of this video, you'll know the difference with confidence.  
  
📚 RESOURCES  
  
\- Mastra docs: https://mastra.ai/docs/  
  
💬 JOIN THE MASTRA COMMUNITY  
  
\- https://discord.gg/mastra  
\- https://twitter.com/mastra  
\- https://www.linkedin.com/company/mastra-ai  
  
🟣 WHAT IS MASTRA?  
  
\- Mastra is a TypeScript framework and platform for building AI agents and workflows. Start locally with the open-source framework, then ship to production with the Mastra platform — including hosting, observability, evals, and more. Everything is built on the same framework, so you can prototype fast and ship with confidence.  
\- https://mastra.ai  
  
⏱️ TIMESTAMPS  
  
\- 00:00 Introduction  
\- 01:15 Manual vs. automatic evals  
\- 01:40 What is a scorer?  
\- 02:51 Code-based scorer  
\- 04:00 LLM-as-Judge scorer  
\- 05:08 Code behind the scorers  
\- 08:11 Offline scorers  
\- 12:00 Online scorers  
\- 15:10 Advanced ideas

## Transcript

### Introduction

**0:00** · Okay, I've been getting some questions about evals, so I want to make the best evals 101 video I can.

**0:06** · Let me make one thing clear off the bat, which is that evals is often underestimated as a discipline. If people can write books like this and many of them dedicated to disciplines like testing, we just know that evals are in that same kind of category where there are different schools of thought, advanced techniques, and lest we forget, this is all kind of an emerging area, so people are still figuring it out. I think because people underestimate it, it's easy to get lost in more advanced techniques like building an eval loop, for example.

**0:36** · But you need really good fundamentals. So, the goal is in this video that you leave it with a crispy, clear understanding and definition of what an eval and a scorer is, how a scorer is different from a test, because from a software engineer's perspective, a scorer and a test can look kind of similar, and above everything else, I want you to leave with some genuine inspiration and ideas about how to build and use productive evals in your project, not just use them for the sake of it.

**1:07** · That's only possible, I think, when you understand the fundamentals, so let's get into it. Would you believe me if I said you're already doing evals in your project? When you go and open your agent and you ask it a test input, like I'll ask my weather agent about the weather in London, you are evalling your agent. You are manually evaluating the output to determine if it's behaving as you expect and the output is correct.

### Manual vs. automatic evals

**1:33** · Obviously, that's not very scalable, and that's where this idea of automatic evals comes into the mix. I think somewhere where the language gets a bit confusing, maybe, is that some people call it evals, some people call it scorers. I would describe evals as the discipline and scorers as the particular tactic that we're going to explore a bit deeper in this video. So, a scorer or an automatic scorer is essentially a function that runs against a trace to evaluate if the agent behaved correctly automatically.

### What is a scorer?

**2:05** · What is a trace but kind of a receipt of everything that happened under the hood when you did the agent run? Every framework and library have their own version of this. It just so happens in Master Studio we can explore it visually. You can see the run and that includes things like the inputs and the outputs. You can also dig into the LLM call that happened under the hood and this way you can see all the context that were sent to the agent like the message history and the system instruction. And then we also get spans for individual tool calls.

**2:35** · When you think about an automatic scorer, it's tempting to think that you just evaluate the outputs, but you could also look at for example the spans to see if a particular tool was called.

**2:47** · Let's make this more specific.

**2:49** · The There are two types of scorers. The first is a code-based scorer and the second is an LLM as a judge-based scorer.

### Code-based scorer

**2:57** · In Maestro, if you click evaluate trace and scoring, you can see the scorers defined in your project and you can choose one to run against the trace.

**3:05** · By the way, we're not going to spend too much time in Studio. I'll show you the code behind these in a second.

**3:10** · It's just to say that a tool call accuracy scorer is a good example of a code-based scorer.

**3:16** · It looks at the trace which is represented in JSON basically under the hood to evaluate whether a particular tool was called for that agent run.

**3:24** · Why is that important? But because if I ask about the weather in London yesterday and it tells me it's sunny and then today I ask the agent about the weather in London, it might be tempted to look at the message history, be a bit lazy, and be like, "Hey, I've already answered that question. I'm not going to do a tool call." But in relaying the information from yesterday, it gives a completely inaccurate answer. That's why it's really important that the agent always calls a tool to get the freshest data. We can build a scorer to do that and it basically looks at the JSON to see if that tool was called.

**3:57** · A code-based scorer is great because it's just running TypeScript code in this case and that's very cheap and very fast.

### LLM-as-Judge scorer

**4:04** · However, there are certain things we want to test for that would just be kind of impossible with code or very error-prone. For example, I want my weather agent to tell me the weather like a formal, proper BBC news-type weather person and I might want to write a scorer to check the tone for that.

**4:20** · I have no chance of expressing that in TypeScript, but I can ask another LLM to judge the quality of the output, make sure it's in line with the tone of voice and produce a score that indicates whether yes, this score passed or no, this score failed.

**4:37** · You can see here the scorer returns 0.86 and if we click into it, we see the description for the scorer and a bit lower, the reason for why it got this score of 0.86.

**4:48** · Another example of an LLM to judge we have here is a toxicity scorer that checks to see if the agent produced anything that could be considered rude or offensive. This is something that you really want to know about once in production in case you get a post on X or Facebook or something claiming your agent is being hateful because your guardrails failed. So, if we go into the code and we look at the master instance, you can see that we have defined and added a bunch of scorers on the master instance. They're all defined in this weather scorer file.

### Code behind the scorers

**5:22** · The tool call appropriateness scorer, that code-based scorer I showed you, is actually a built-in master scorer. You can change weather tool with whatever tool you want and you can set strict mode to true or false. If strict mode is true, that basically means the scorer only succeeds if the tool was called once and only once. Uh with strict mode false, it doesn't matter if it called other tools as well.

**5:45** · We can also define a toxicity scorer using Mastra's built-in toxicity scorer, but because this uses an LLM as a judge, we need to specify a model, in this case 54 Mini. And it's pretty common, right, to use a smaller model to judge LLM outputs. And we'll talk a little bit more about the strategy to use for LLM as judge in a moment, but there is a bunch we could say about that as well. I wanted to show you an example of defining a custom scorer, which is why I made this tone scorer. Essentially, you give it a description.

**6:14** · That just helps you understand it in Studio, like we saw before. And then we configure the judge with a model and some instructions.

**6:23** · The pre-process step is where we basically access that trace. So, here's the trace input, the trace outputs. Bear in mind the input is not just necessarily the message, but it could be the system message as well, and things like the tool calls. And Mastra actually gives you this helpful function called get assistant message from run outputs that basically traverses the JSON outputs to get the most recent assistant message out of the agent and return it.

**6:52** · Basically, this analyze function runs on the last assistant message, and we define an output schema for the LLM call, so we can access structured data instead of having to parse the LLM's outputs. That's just the Mastra feature anybody can use. It's built into our eval system as well. And then we construct the prompt dynamically, right, which is where you interpolate that value. Ultimately then you can produce a score. Maybe this just returns a one or a zero. That's a very good idea because it's simple, but you might want to apply some kind of formula to arrive at a number.

**7:23** · This idea of having like a range of numbers between zero and one has gone out of fashion a little bit because it's not really clear what the difference is between like a 0.5 and a 0.6. You get kind of clever with the formula. It can feel a bit like a distraction sometimes.

**7:37** · What we really want to know is, yes, does this match the tone of voice, and no, does it not? And then we can also generate a reason. This is optional, but it's handy because when looking at a failure, it enables us to see why the scorer failed and then dig into it.

**7:53** · So, I think now it's pretty clear, right, what an automatic scorer is. It's either a function or it's like an LLM call that evaluates one of these traces.

**8:01** · The really important question that we have to answer next is, where do these scorers run?

**8:07** · There are two places. The first is offline, that's what we're doing here, and the second is online. Let me just start with offline.

### Offline scorers

**8:15** · Obviously, going into each trace, clicking evaluate trace, picking a scorer is not super efficient.

**8:21** · That's why in Mastra, you can take a trace and you can add it to a dataset.

**8:26** · So, let's create a dataset. I'm going to call this our golden dataset.

**8:31** · And then we'll head back to the agent real quick and ask it just one more follow-up question.

**8:36** · And then we're going to head to the traces view, and we're going to find that first agent run for weather in London, and we're going to save it as a dataset item in our golden dataset.

**8:47** · And then we'll take that other agent run where we ask about the current weather in Tokyo, and we're going to add that to the golden dataset as well. These are actually two different test scenarios because the first test scenario is asking about weather in an empty chat, and the second test scenario is asking about the weather as a follow-up. If we now go to the datasets tab and into our golden datasets, we can run an experiment. We want to run an experiment against the weather agent, and we're going to use all these scorers.

**9:20** · Effectively, for each item in the dataset, the agent is going to run these scorers and produce a score. So, let's give that a moment and see what happens.

**9:30** · And And while this is running, I can quickly explain that the core idea here is that it's kind of like a regression test, right? After every change, I could run this data set and see what changed.

**9:40** · I can actually look at different results and I can compare them if I want to in studio. And using that get a sense of if I introduced the regression.

**9:48** · You can see here that the tool was called, that's why we got a one. In this case, it scored a 0.870 on our tone of voice. I don't know what that means, it sounds good. Where this comes in handy is to kind of see more subtle trends over time and and that becomes a bit more relevant when we talk about online evals in the second. And for the toxicity score, we got zero, meaning that both tracers didn't result in any kind of toxic outputs.

**10:12** · If I was to approach this from scratch, I would probably want to have all my numbers meaning the same thing. So, I interpret one as good here and zero as good there. I'd probably want them both to be one or zero. And by the way, let me just say as well that you can run data sets and experiments inside of your continuous integration process, so you can make this part of your development process.

**10:34** · This does seem very similar to testing, doesn't it? Like some form of regression test, like an integration test perhaps.

**10:40** · But I think the difference fundamentally so far is that when you're dealing with an LLM, you're dealing with stochastic output, meaning you get different things for different inputs. And so, our techniques here fundamentally revolve around checking things that are in our control. We can We can check if the tool call was called, or we can lean on an LLM as a judge. So, it does make sense to have like slightly different language for this form of testing, but it is fundamentally testing, nevertheless.

**11:05** · I would also say that these are very slow, especially when using LLM as judge, very expensive potentially when using LLM as judge. So, it's not really like unit test where you run it in the background.

**11:19** · It's something that you might involve in your CI process. And by the way, in Master, I can't really demonstrate it too well now, but we have this feature called Agent Editor that lets non-technical folks or people without access to the code update prompts and change tools and things like that. At which point having these data sets inside of studio is really beneficial compared to only having them in the code. So, that's another way in which it feels slightly different to test to me, which is that these are parts of the product and are available to everybody.

**11:46** · But, those are all, in my view, just differences. I would say fundamentally these are a form of regression test.

**11:54** · Where scorers start to feel fundamentally different is when we switch gears slightly and we talk about online scorers. So far, we've retroactively run a scorer on existing traces, or we've created a data set and we've run a scorer as a form of regression test.

### Online scorers

**12:11** · The online scorers involve running the scorers against real production traces as they're happening almost in real time. And that's where scorers feel less like testing and more like a monitoring tool.

**12:27** · I'll show you this in action in a second, but just know that it leads way to things like this, where you can see a dashboard of your evals over time, and you know, we spoke about the 0.86 score, what does that mean? Maybe it's not as binary as one and zero. Maybe the Maybe it starts slipping because of some drift in the system prompt or the context engineering. It It gives you that kind of view of things.

**12:50** · The way to set this up is, okay, we have our scorers all defined and they're available on the master instance. We can now go to the weather agent, import the scorers, and then add them directly to the agent.

**13:03** · And when we do this, the scorer runs on every agent run automatically.

**13:08** · You probably don't mind the tool quality appropriateness scorer running on every agent run because it's using code and it's very cheap. But when it comes to the LLM's judge based scorers, suppose you have just 100 users, but likely you have thousands, you don't want LLM's judge running on every single trace because you end up just using a ton of tokens, even with a cheap model, but it add it quickly. So, that's where we kind of like have sampling. So, maybe you only want to run the trace on 50% or 25% of the traces. We'll set that to one for the time being.

**13:38** · And so, now if we uh reload the server for good measure, and now we'll come and ask about the weather in SF, San Francisco. If we head over to traces and click in, and then evaluate trace, you can see where the score has already run for each of these.

**13:55** · And where that becomes really helpful is when we're talking about observability, right? Because whenever you put your agent into production, it's imperative that you send all the traces to some observability platform like Master Observability, at which point you can run these scorers to get a monitoring dashboard to see how the agent is performing over time. You know, it could be that maybe the offline eval didn't catch something. But why, right? It's because users consume our agents with all kinds of inputs in ways we never expect. It's imperative that we have this view.

**14:27** · Such that if something does seem wrong, we can then kind of like dig into the trace, see what that user was doing, and make a fix. It's not the most perfectly instructive to do this all locally, because I'm kind of conflating this local offline environment with how you might use agents online. In reality, you'd probably use something like Master Studio and Master Observability.

**14:48** · Master Observability is like the sync for those traces in production, and then Studio allows you to run scores against those traces online, see the outputs, create data sets, and all that good stuff.

**15:02** · We are just looking at the one-on-one here today, right? There's a lot of interesting things that follow from here. For example, when your users use the agent in unexpected ways, maybe they break something. You could add that broken trace to a data set, submit it for review, and then you know it's something that you can iterate on and fix. That's something that Studio enables.

### Advanced ideas

**15:23** · And so we've defined like an eval versus a scorer. We talked about online and offline scorers for difference between LLM as judge and code-based scorers.

**15:33** · I've showed you some of Master's built-in scorers, as well as how to define your own. And by the way, check out the docs. We have a bunch of built-in scorers. It's a really interesting challenge, right? That because agents or models more specifically are stochastic, non-deterministic, they produce different things. You can't just do like a simple test, right? Where you say, "Did the agent produce?" You know, if you ask about the weather in London, that's going to change on a daily basis.

**15:56** · Or you ask it to write you a poem, well, that's going to vary. But you can define a ground truth and then find similarity in the answers, so you know that it's directionally correct. And then we spoke briefly about this idea of an eval loop when we add failure modes and broken traces to a data set to then review. This creates kind of a loop, right? Where you can then improve the agent such that those traces no longer fail. Or maybe you find things that are not working, but the score is passed, and then you want to dial in your scorers. I sometimes take a score results that says the trace was good when I know it's bad.

**16:28** · I go into my coding agent and I say, "Hey, what gives?" And then I ask my coding agent to then improve the score. And so there's all kinds of like tactics like this that I think would be really interesting to dive into in a part two.

**16:42** · If that's something that you would like to see, I would love to make that. Just let me know in the comments down below.

**16:48** · I've been Alex Booker at Master. This has been evals 101. Thank you so much for watching.