---
title: "Making Agent Evals Isn’t As Hard As You Think!"
source: "https://www.youtube.com/watch?v=h_DP7ChJUpY"
author:
  - "[[Adam Lucek]]"
published: 2026-06-20
created: 2026-06-30
description: "Discussing the theory behind creating and using agent evalsResources:Evals Field Guide - https://lucek.ai/blogs/agent-evaluationsEvaluation Concepts - https://docs.langchain.com/langsmith/evaluati"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=h_DP7ChJUpY)

Discussing the theory behind creating and using agent evals

Resources:
Evals Field Guide - https://lucek.ai/blogs/agent-evaluations
Evaluation Concepts - https://docs.langchain.com/langsmith/evaluation-concepts
Demystifying Evals - https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents

Chapters:
00:00 - Introduction
00:33 - Context
02:37 - What get’s measured
05:08 - How its measured
08:20 - Unit Test Evals
11:14 - Agent Integration Evals
14:49 - Online Evals
18:32 - Benchmark Evals
23:51 - Agent Eval Loop

#ai #programming #datascience

## Transcript

### Introduction

**0:00** · Hello everybody. Adam Lusick here, and today we're going to be talking about agent evals or evaluations. As anybody who's worked on an agent before will tell you, evals are a core part of actually measuring and improving the agent that you're developing, but they're notoriously tricky to understand and get right. So, I thought it would be useful to discuss some core types and examples of common agent evals. While this will not be comprehensive to every single way that you can test and evaluate an agent, it should provide a lot of the foundational understanding and theory behind how all of these evals and types of evals are applied.

**0:30** · So, let's get into it. As a preface, there's a few things that we need to get out of the way for context. The first is more specifically, what are we talking about when we talk about agent evals? And really, this can come down to one core idea, testing and measuring the behavior of your agent. An easier way to think about this is it's literally just the parallel of software testing, but for creating and measuring AI agents.

### Context

**0:53** · But, due to the similarities between evals and general software tests, I think it's easier to actually frame various types of evals and how we set them up using existing terminology. Specifically, I'm going to break down the evals and their definitions into four main groups that you've likely already seen before if you've done some software engineering and development. That would be unit test evals, integration test evals, online evals or observability, and benchmarks.

**1:22** · While these aren't exactly going to translate one-to-one with the application that we're going to show here, I do think that it provides a nice framing of the point that we're trying to get across with the individual evals that we'll discuss. And along the way, you can likely start to think of how you've been applying different forms of test-driven development or just general testing in your software to when you're actually developing and creating an agent. But, the overall nuance that we'll dig into along the course of defining all of these is really what we are evaluating.

**1:50** · At a grand level, you can think of this as evaluating actually the agent's behavior. The difficulty that comes with this, however, is that the behavior of an agent depends on a lot of different variables and factors.

**2:04** · It's also very non-deterministic. So, in our traditional testing sense, where we would assert that a function actually does what we expect it to do, that is very easy to implement and does what we expect. However, when we're discussing whether a language model under an agent harness or in a total agent setup actually does what we want it to do under given scenarios, we have to reframe the question and the implementation a little bit. But, as with all good tests, what we need to figure out first before actually getting into these definitions is what are we actually testing or evaluating and how is it being measured.

**2:35** · Starting with the what's getting evaluated, of course, at the top level, we are evaluating the agent, but we actually need some form or some artifact of the agent to do our comparisons and our measurements against. That is, of course, where what we have come to known as the trace comes into play.

### What get’s measured

**2:52** · Traces have become the common logging form for agent interactions and essentially capture all the information about an agent's environment, including things like the inputs, the outputs, and how it actually evolved across its invocation. In other words, every time an agent is actually ran, we capture all of the different metadata around it and the individual steps that are taken into a format that we refer to here as the trace.

**3:19** · For those of you who are more familiar with traditional observability platforms, you can think of this as a trace same sense or what is commonly referred to as a span. But, the traces here are going to capture and display essentially all of the inputs and outputs and steps that the agent takes along the way with, of course, any relevant metadata about its environment or its state. Within a trace, we have the individual runs, which are the single steps within them, and then also, if you group multiple traces under a one continuous context, that is commonly referred to as a thread.

**3:50** · Threads come into play, especially if you have something like back and forth between an agent, say something like a general chatbot behavior. Every time a user sends a message, it does invoke the agent to generate in a response or a final output, and that would be considered a trace. However, if the user responds in the same chat thread, then it would be another trace capturing all of what it did as a follow-up.

**4:13** · But essentially, this has become the standard way of logging exactly what your agent is doing so that you can see the individual steps that it took to get to its final output and the logic that may have happened in between. To actually set up our evals, we'll be taking bits and pieces of the traces, focusing on runs, or looking at threads as a total in various different scenarios and ways. I'll demonstrate this visually with the graphics, however, so hopefully what we do to actually transform the trace to set up an eval will make a lot of sense.

**4:42** · But with the data model of your agent in the form of a trace being defined, what we also need to discuss is how exactly and what parts of it are we measuring.

**4:53** · Across all four of our evals, we're essentially going to be scoring two different things. Either the step, did the right thing happen, or the contents, is the output good, which we apply either at a trace, thread, or individual run level. Actually measuring steps and content fall into two main buckets, both deterministic and probabilistic.

### How its measured

**5:14** · Deterministic is likely what you're more familiar with and have used, doing things like assertions or direct matches against what we expect a function to actually output. But in this case, we are measuring what the contents generated or the step taken of an agent is. We can apply the same idea, looking at something like this, if we expect a tool call of get weather with the city being Paris to be called, and that is what's called, we would consider that a pass.

**5:40** · Or on the other hand, if we observe that the tool that is called is a web search tool, that would be a failure. But essentially for an assertion of agent behavior, we'd be looking for whether the right step is taken or the right contents are generated, usually exactly for something like this, so that it's quick, cheap and easy to actually assert.

**5:59** · But as mentioned, not everything that an agent does or outputs is actually deterministic or specifically something that can be measured directly, which is where we introduce some probabilistic measurements or more specifically what's been commonly referred to as language model as a judge or LLM as a judge. LLM as a judge is something that we turn to when we want to measure the subjective quality of an output or a process that has been taken.

**6:25** · I refer to quality broadly, but I'm essentially referencing all of the non-directly comparable or directly measurable traits of your agent, either it's process or the outputs. To measure these things, we rely on the intelligence and discretion of another language model to provide the score. This is where we would outline exactly and describe the criteria or criterion that we are measuring something against and allow the language model to actually see whether or not what it's judging is up to or passes the criteria.

**6:58** · In our graphic here, that criteria would be whether or not the output of the agent answers the user's question and stays polite. Of course, politeness here would be very difficult to measure with a function, if not impossible, so this is why we would introduce a language model as a judge to say whether or not this response is, which in this case on the left, that would be polite. On this in the right with the refusal, this would be a failure. So, we have our deterministic way of asserting whether or not something is correct.

**7:27** · We also have our subjective or probabilistic way of asserting whether or not something is correct. One of the final things that we can do is combine these all. Very often, there are many dimensions that you want to test and assess across your agent and it's not uncommon to take all of those, weight them by how important they are to you, and have one final rubric or scorecard.

**7:50** · The purpose of a rubric is to take all of the ways that we are measuring an agent and combine them into one overall signal or score, commonly referred to as a reward, to show whether or not our agent is performing in a final summed number. Usually these are weighted and normalized to one, so zero would be an absolute failure and one would be perfect performance. So with a lot of that pre-context out of the way, this comes together a lot more when actually discussing the makeup of the evals themselves.

**8:19** · So without further ado, let us move on to the first unit test evaluations. Unit test evals, or I like to commonly refer to them as behavioral unit tests, are essentially what we use to assert that a certain behavior happens under various conditions. More often than not, we are trying to assert that given a certain scenario, environment, or set of inputs that the agent is operating under, the next step or decision that it makes is what we expect.

### Unit Test Evals

**8:45** · Creating a behavioral unit test then commonly looks like identifying a trace where that desired behavior is happening, such as for example, we would want this tool call being made, and then recreating all of the inputs and environment that the agent is under right before that step happened. And then we run it for one single step. This final step is then our candidate for evaluation, where in this non-specific example, we expect the tool call to happen and that would be a success.

**9:15** · To make our example more specific, consider something like an e-commerce customer service agent. This agent has access to common tools like process return, escalate support, look up user, and other things that you would expect. One of the behaviors that we might want to unit test is then the agent's ability to actually successfully process a return in the manner that we want.

**9:35** · More explicitly, we would hope that when a user provides an order ID and a message to actually process a refund, that the agent will call the process return tool, which can take in the order ID and the reason as keyword arguments. We would create a behavioral unit test then by reconstructing the message sequence that we have, which in this case would just be the user's request containing the order ID and the request for a refund, recreate our agent, and pass the message sequence along to it. We allow it to generate a response and then stop the execution.

**10:08** · Given that next step in its output, we may do something like assert that the process return tool was exactly the next generated step, or assert that the order ID match the input exactly, or judge the quality of the generated response.

**10:23** · Implementing this test allows us to essentially cement that that behavior is either working or not, so that as we modify and make additions or removals to the agent, we would run this test and be able to tell whether or not the behavior is still present. Or in other words, this could be a form of regression testing for the behaviors that we want in our agent.

**10:44** · But as a general rule of thumb, as we introduce different behaviors or different steps that the agent needs to take within its prompt, we would follow that up with a behavioral unit test like one of these to be able to measure whether or not our desire is actually happening and catch if it is unable to in the future.

**11:02** · Similar to regular unit tests, testing every dimension of a code base, we would also have plenty of these behavioral unit tests testing every single behavior of the agent that we expect. In the same boat as our behavioral unit tests, would be agent integration tests, or some people like to think of these more as end-to-end tests. So while a behavioral unit test is interested in one single step or behavior of the agent, the integration test is actually going to look more at the output rather than the individual steps.

### Agent Integration Evals

**11:33** · So, we care less about the individual steps or process that the agent took to get to a final output and more about whether or not it did that successfully and well. Setting these agent integration tests up looks like first identifying a desired outcome of your agent and then recreating or mocking the starting state and inputs to your agent. We then let the agent run until it finally resolves and produces a final output and then we concern ourselves with measuring and scoring this output.

**12:01** · So, you can see this is less about mocking an ongoing run and then resuming and more about whether or not the whole thing works and whether the output was good or not. The scope of what and how we're scoring it can actually widen a lot here as the final output of an agent can be pretty much anything from just a simple generated response to a multi-page report to creating a whole lot of external system calls and everything in between that you can think of.

**12:30** · For example, you can consider a deep research style agent that performs competitive market research. This might rely on multiple sub-agents, web search tools, all to provide a comprehensive report back to the end user on a given topic. While our unit tests are covering the spread of how it actually gets there, we are now interested in measuring the report that the overall system generates. So, to set this up, we might take a topic of interest, recreate the agent's environment, give it access to all of the live tools that it needs.

**13:01** · For example, this might be something like web searches and a file system back-end and input the system prompt and the initial kickoff message into the agent.

**13:12** · We allow it to operate fully, it'll do all of its wonderful research and come back with the generated report artifact at the end. We can then measure the generated report that comes out of this in a few different ways. We may assert that the report follows an expected structure that we have defined. We may judge the quality of the generated contents as we have described it in a language model as a judge criteria, or we may do something like compare the generated report with an example of a quality report that we have prepared on the same topic.

**13:44** · This could also be a language model as a judge. As we do allow a full agent run here in the scenario, these do tend to take a little bit more time and a little bit more compute to do. Similar to your traditional integration or end-to-end tests. But overall, agent integration tests are going to measure whether or not the full thing works and the quality of the outputs. Well, our unit tests up here are going to be measuring the individual steps and whether the behaviors that we have implemented are actually being followed.

**14:15** · One of the commonalities between these two tests, our unit and integration tests here, is that as you can tell, over time as we are making and implementing these, we'll be building up essentially a data set of all of these different scenarios that are being tested as well as the scoring mechanics here. We then run these various tests in a manner that we would describe as being offline.

**14:38** · Essentially, not using whatever the live deployed production agent might be, but in all of these various testing scenarios against a historical data set. And while extremely useful, we may also be concerned in analyzing and measuring or evaluating our agent's performance as it happens over a period of time. This is of course then where online evals come in.

### Online Evals

**15:03** · Online evals are going to operate under a bit of a different circumstance from unit and integration tests, as they are going to run against real interactions as they come in, as they happen with the agent, rather than our fixed controlled data set. This means that we'll very often not know the inputs that are coming in because they're from live users, as well as not necessarily have a strict reference output as your agent can cover different things and user requests can be diverse.

**15:32** · Online evals can definitely be thought of more in terms of traditional observability and how you might aggregate those metrics and score them live. Setup for online evals then looks like capturing every trace that is produced as a result of your agent running. I would use LangSmith to do this and then running a function or a code evaluator or a language model as a judge evaluator against a component of the trace or the trace as a total.

**15:56** · We can then plot all of these output scores on a line chart over time to see how they have trended and also do things like set up alerts for if they reach different thresholds. For our online eval example, consider a sales development agent that researches prospective accounts and then sends outreach emails to the contacts that are listed there. In this specific scenario, we already have agent deployed, it's been built, it's running in production, and we're logging all of its traces to an agent observability platform such as something like LangSmith here.

**16:28** · What we want to do is monitor the behavior and output trends from this agent. We're concerned with its turn count, verbosity, and email tone. The reason being, we of course want to make sure that our agent is professional, we want to make sure that it's not sending too wordy of emails, and we want to make sure that it is efficient.

**16:44** · So, to set up our three online evals, we would create a function that counts the trace's turn length, a function that counts the generated emails character length, and then we would set up an LLM as a judge that assesses whether or not this email that's been generated is professional based on our outlined criteria and expectations. So, as our agent runs and does its job, it's going to be producing and logging its traces. For each one of those traces, we'll then run these functions and invoke a language model to do that assessment.

**17:14** · We then capture all of those points and plot them out so that we can see over time how things are doing. We could also set expected range and alerts to notify us of abnormalities or outliers. A scenario could be that say we updated our prompt and this inadvertently caused the agent to become a lot more terse. This would be surfaced as a downward trend in our generated emails character length compared against the standard range that we expect it to be in.

**17:42** · But overall, online evals are really great for giving us trends and how our agent is actually performing over time as well as general alerting as it's running live in production. But we can also use them to do things like flag anomalous traces as they come in, isolate relevant sections for deeper inspection, or just generally scale our analysis of a live agent behavior in ways that would be hard to do manually or capture all effectively in our aforementioned tests.

**18:09** · As a side note, depending on the amount of traffic that your agent sees, you may also want to consider a sampling strategy for the different online evals that you have.

**18:19** · Especially for things like language model judges where they actually invoke an LLM and consume tokens, you may want to run that on just a fraction of the traces coming in, whereas cheaper to run functions could be on more. But overall, our online evals, our integration tests, and our unit tests really give us a holistic picture of how exactly our specific agent is operating and behaving. And I say specifically our agent because this is where we're going to start to diverge from just making individual evals for whatever it is we're concerned of our agent doing.

### Benchmark Evals

**18:52** · Which brings us to our fourth and final eval of this discussion, benchmarks.

**18:57** · Benchmarks are interesting because they are essentially trying to prove and measure the performance of an agent decoupled from its actual implementation. Most often, we see benchmarks created to actually measure the performance for a specific capability, not necessarily the behavior of an agent. The most prolific of benchmarks that have popped up are things like SweBench, which measures an agent's ability to resolve GitHub issues effectively, or essentially measures the capability of software engineering.

**19:25** · SweBench itself is made up of a little over 2,000 tasks that consist of a code base, a GitHub issue, and then the corresponding solution pull request. To score, they have a suite of tests that fail in the task's starting state, but pass when the solution PR has been applied. Running the benchmark then looks like recreating the environment by cloning the code base in its prefixed state, and instructing the agent to fix the outlined issue.

**19:48** · The agent will then operate and do its thing and apply its fix, and then once it is completed, the held out test suite will be ran to verify if the fix is valid. Given that all of the tests pass, the agent has successfully passed the task. Given if any of them fail, the agent has failed.

**20:05** · So, while SweBench is a very specific coding example here, what you can see is that it's essentially created in a way that's agnostic to how the agent itself is actually implemented. It's rather a pure test of whether or not some form of operator can actually effectively do these coding tasks. The cool part about this then is that it gives us a very objective baseline for the performance of an agent on a given capability.

**20:27** · This means that very often we can run multiple forms or versions or types of agent on the benchmark, and then see what they score and directly compare them together. For what actually makes up a benchmark, we can extract a lot of the primitives from our SweBench example, and see that we need a capability, or the specific skill or behavior that's being measured measured, a task distribution, or a representative set of inputs that test that capability,

**20:56** · the ground truth, or the expected outcome each task is measured against, and then a scoring method, or how pass/fail or a score is determined.

**21:05** · Then, the goal of the benchmark creator is to essentially create all of these various tasks in a way that accurately reflects the real-world capability that you care about. For example, let's consider a financial audit agent. The capability of interest that we actually want to benchmark is the ability to identify violations in financial records. As such, what we would do is create tasks that would be built that each consists of a set of financial documents containing known discrepancies that we would expect to be identified.

**21:38** · We would then create many of these tasks and vary things like their difficulty, their topic, their density, and other different dimensions to create a representative set of the range of conditions that a real financial audit might present. Running the benchmark would then be instructing for each task the agent to inspect the documents and list all of the anomalies that it finds.

**21:59** · This is repeated across all of the various tasks that we have in the total benchmark. We can then evaluate its performance against the known ground truth using various different measures of things like precision, accuracy, F1 scoring, or whatever might be relevant to actually scoring the capability of the agent. Creating and running these benchmarks then provides us with two useful ways to look at the data. First, we get a great baseline and objective comparison across agents and agent versions on a given capability.

**22:27** · And secondly, we also have a clear signal on either improvements or regressions that might happen of an agent in a given capability. The second point here is especially powerful because if we have an objective measurement of an agent's ability to perform a capability that we want it to do, we can use this as a feedback loop for improvement.

**22:47** · This would look like running the agent on the benchmark, seeing how it scores in comparison to other agents, looking at how it actually completed those tasks to find inefficiencies and improvements that can be made, modifying the agent, and then running again to see if it improves at that capability. The expectation is that as the score and performance on the benchmark goes up, the agent's ability to actually do said capability improves.

**23:12** · A couple of final notes on the benchmarks before we close out here is really just first, benchmarks are very difficult to do correctly. It is difficult to accurately measure a capability and its performance, and often takes a lot of time and inspection of your data as you put these together to make sure that it is truly representative of the capability that you are trying to represent. The implementation of the environment and the way that it is scored also tends to be bespoke to the capability.

**23:39** · For something like SweBench, that of course is whether or not all of the tests pass, but for something like financial auditing, we may have various dimensions that we care about scored on a rubric, so on and so forth. But overall, evals are really an important part of developing, monitoring, measuring, and improving an effective agent. And all four of the eval types same broad categories that we discussed today, all play together and give us a complete view into how our agent's doing.

### Agent Eval Loop

**24:05** · Unit tests do things like lock in individual behaviors, integration tests validate our end-to-end outcomes, online evals monitor our live performance, and the benchmarks here provide the North Star or target for optimization. Each one of these does play a distinct role in surfacing various failure modes and ensuring that the progress on one front doesn't come at the cost of another. But as always, one thing to keep in mind is that the most powerful evals that you make are tailored specifically to your agent.

**24:34** · But on that note, I think evals are pretty cool, and I'll have a link to this guide in the description below. But if you like the video, like the video.

**24:42** · If you have any questions, leave them in the But if you like the video, like the video. If you have any questions, leave them in the comments below. And if you want to see more like this, consider subscribing. Thank you, and have a great day.

**24:54** · comments below. And if you want to see more But if you like the video, like the video. If you have any questions, leave them in the comments below. And if you want to see more like this, consider subscribing. Thank you and have a great day.

**25:05** · more like this, consider subscribing.

**25:07** · Thank you and have a great day.