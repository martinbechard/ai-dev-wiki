---
title: "How are coding agents changing software engineering?"
source: "https://www.youtube.com/watch?v=blgUmyMiROI&list=PLdVLOietcHTD3OjLupQ6oEQWEeKXLVozO&index=18"
author:
  - "[[Cursor]]"
published: 2026-05-29
created: 2026-06-23
description: "New data from https://cursor.com/insights."
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=blgUmyMiROI)

New data from https://cursor.com/insights.

## Transcript

**0:00** · I've been writing code for the last 15 years and working as a software engineer for the last 10. And yet it feels like software engineering as a whole is changing so fast every couple months as new models come out or as coding agents get better. And it can be kind of hard to understand these trends. So, Cursor, we just released a bunch of data on how AI assistant development and coding agents have been changing the field of software engineering. So, I want to read through it live and give some of my commentary on how I think about this and how it's affected my own work as an engineer.

**0:30** · This developer habits report is going to talk about five things. So, coding speed is doubling year over year.

**0:37** · We're seeing larger PRs. We'll talk more about that. Agent generated code is sticking around.

**0:42** · Uh we've benchmarked many different model families and the cost per line and the cost to actually submit these requests uh is very different across different models and different providers.

**0:52** · We see this trend of the top 1% power users of AI and coding agents really being very productive and having a a larger separation with the rest of users.

**1:03** · Uh context is growing. We see a dramatic increase in input tokens and a shift towards trying to cache as much as possible, which makes sense. And then we're seeing a lot of people evolve from more basic prompts to kind of building this system, building this factory that's going to help you produce high-quality software.

**1:21** · And we have some interesting data to help talk about this. So, let's start with developer acceleration.

**1:28** · Developers are now adding more code per week with growth accelerating since the start of 2026.

**1:33** · Now, I wanted to add this. It's not a perfect metric, but I do think that lines of code added is at least directionally interesting. Obviously, you can add lots of bad code and that's actually a net negative for the codebase. But when you do look at this in aggregate across the Cursor user data, it does show this trend of how more and more developers are both creating more projects, trying out new ideas, trying out new prototypes. Uh other people outside of the development process are being able to contribute to building software, which I think is uh by and large a very good thing.

**2:05** · But it that does come with its own challenges, so we can't look at just that one bit of data um in isolation. Notably, code additions are growing in PR. So, the lines added per PR is up two and a half times year over year, and that's continuing to grow. And then specifically, I think this mega PR, which is a fascinating to me. The number of PRs with a thousand lines changed are becoming more and more common. Which makes sense. You see people who are kind of vibing out these PRs with tons of changes.

**2:36** · Maybe they don't yet understand what a lock file is and why it added, you know, thousands of lines of codes in in their diff, or maybe they accidentally generated some code and it needs to be ignored in Git, or maybe it's just actually just a ton of code.

**2:52** · And I think this is really interesting for two reasons. One, you see the spike around the holidays, which I think is when a lot of people started to explore the latest models, Opus 45, kind of getting into Cursor, trying this and applying it, or other coding agents. And then secondly, I think that these mega PRs do pose a real challenge for developers. It's hard to maintain quality as the number of lines of code produced grows, and in general, that code can become a liability.

**3:19** · I had a tweet about this earlier if you want to go check it out, but you should be trying to minimize the amount of code, and an agent without proper wielding and control is going to be happy to write a lot of code for you.

**3:34** · Some of that code you might not even need. It might be overly defensive. It might be overly backwards compatible for situations that don't really even matter or don't exist. So, it really takes a lot of nuance to do this well, and a lot of these patterns are still really being figured out.

**3:50** · But interestingly, in the past couple months, if you look at tool calls, so writing or editing files or running shell commands, searching the web, for example, you're seeing this continue to rise about 30%. And for me, the way I think about this is agents and models are generally getting better at calling tools. And if you call tools, it's a pretty good approximation of an agent's usefulness. If they're making more file changes, if they're reading the web, they're running shell commands, it's probably a more productive and helpful agent for you.

**4:20** · So, I kind of view this chart as general model intelligence and model quality improving over time, which I find really interesting.

**4:30** · And then, the last part in this section, AI-generated code is surviving longer.

**4:35** · This is a really interesting stat that Cursor can help provide through our data, but AI lines have been accepted are still present after 60 minutes. And, you know, you could argue what the correct duration of that time should be.

**4:48** · I think for me, what I take away is that code is very sticky, and that's why a lot of people say that adding tons and tons of code is kind of a liability to the maintenance of that software over time. So, with great power comes great responsibility. Yes, it's amazing that we can generate and write lots of code, but the, you know, the senior staff engineers, the code base architects, the people who are thinking about how to build these systems and make them maintainable over time, are also trying to fight against and they're using AI to

**5:16** · work against the AI to make code review easier, to make sure we're not overly adding things that we don't need. And I expect this trend just to continue to rise. I don't think there's a perfect solution in the market right now that has figured this out. Everyone is still grappling with the ease of generating code through agents and what that means for the software systems that we maintain over time.

**5:37** · Okay, section two.

**5:39** · Uh intelligence. This is really interesting. I mean, there's a deeper philosophical thing here, I think, which is why do people like Opus? Why do people like GPT? Why do people like other models? And there is um some correlation between how you view the warmth and the response of the model and the brand of the model and you're kind of building this relationship kind of like it was a coworker to where you might be willing to pay a premium for using that model.

**6:08** · I think a lot of people like the Claude models, a lot of people like the GPT models, and both of them are somewhat converging on some best practices for how you should respond, how eager you should be to make edits, how much you should push back, how much you should continue working on long horizon tasks without having to ask for a bunch of clarifying questions.

**6:27** · This is really tough and getting this model behavior right has been a multi-year effort for um all of the model labs.

**6:34** · So, it's interesting here to see that generally the Claude models are a bit more expensive. But then when you look at the cost per accepted line, this is where things start to get interesting. So, if a model is more expensive, but it helps you get your job done faster, does that mean that it's actually the same cost as maybe a cheaper model that's going to make a bunch of edits or just work a lot longer? I think in some cases, yes.

**6:55** · Like if you can get the most intelligent model to one-shot something, it will be overall a lower price than a very unintelligent model just spinning its wheels for a very long time. But this is a nuanced question because for most of your agentic work, probably everything is not requiring that level of intelligence or that level of um you know, one-shot capabilities.

**7:21** · So, if you use the most expensive model for everything, it will add up and I think we've we've seen that um already happening with some companies as they're trying to figure out how to balance um using very, very smart models and also the economics of thousands of engineers who are writing code now every day using these tools and trying to find the right balance of price, performance, and cost.

**7:45** · And so, we're seeing this uh both in our own internal evals called CursorBench, as well as external evals where people are trying to figure out where on this uh on this chart they want to fit. So, the average cost per task on the x-axis, and on the y-axis we have the percentage that the model scores on our evals.

**8:02** · And you know, you might argue that well, this is a CursorBench, so obviously cursor models are going to score well here, which I think there is some um there are many ways that we try to make that not true, and make sure that we're not just, you know, padding our own benchmarks, right? But, I think it's also going to take this with a grain of salt, and compare it against other external benchmarks.

**8:25** · For example, we report on TerminalBench and SweBench multilingual, and then there's artificial analysis and a bunch of other external benchmarks where you can kind of make your own comparison here. So, for example, the artificial analysis benchmark is pretty similar to the results that we're seeing here.

**8:40** · Um but, what it's trying to show, in my opinion, the bigger conversation is how much do we in value intelligence to a certain price point? And especially the total time it takes to get a task done.

**8:51** · If there's a fast variant of a model, and it's economically much more affordable than maybe a different fast model, does it make more sense for us to use that and get the work done more quickly?

**9:01** · Kind of depends. Kind of depends on the team.

**9:03** · Okay. The power user gap, number three.

**9:06** · Uh This is really interesting. This one kind of blew my mind. I mean, it makes sense. You see people building these wild things what on X, and you hear about these people who are just using a ton of agents and creating wild things.

**9:19** · And when you look at this usage, you see a small share of developers that's just writing a ton of code with AI, or building these uh very complex agent systems, and using a lot of tokens. And they're using tokens to to automate software, which we'll talk about later.

**9:35** · Um but, I think for me, the thing to take away here is somewhat similar to lines of code produced. I think tokens consumed is not a perfect measure. I think there is some amount of token waste here where even the people in the top 1% on the bleeding edge of of trying out and using these models and these agents as much as they can, they are willingly knowing that this is not a perfect measure of productivity, that some tokens are kind of wasted in the pursuit of

**10:06** · what whatever this means to you, but becoming more AI native, figuring out AI agent workflows, whatever, you know, word salad you want to use to describe that.

**10:16** · Everyone is trying to disrupt themselves and figure out how they use these tools.

**10:21** · And for a lot of people, especially a lot of companies, they're willing to have some error bars on how much of that token usage is actually just kind of throw away in pursuit of that larger goal of upskilling or reskilling an entire workforce. So, it's interesting.

**10:37** · I I think what it means to me is it is worth investing in learning the latest models, learning the latest agents. And it's also okay to come at that with this critical eye of cost to intelligence to performance and trying to get the most value out of the tools that you're using.

**10:55** · So, when you look at these developers kind of pulling away from the median developers, this chart is measuring it in lines of code per week, which we've already kind of talked about is, you know, an imperfect measure, but still interesting.

**11:08** · And then here's another interesting thing. When you look at the lines of code, the median active user merges.

**11:14** · They merge 15 times more PRs.

**11:17** · Um so, that's really interesting. I actually like merged PRs as a better metric than just lines of code added cuz presumably um for for some compliance reasons, a lot of companies need to have at least one human reviewer sign off on a PR.

**11:33** · So, if that's the case and a PR is getting merged, there is at least some human reviewer doing some sort of check.

**11:40** · Now, it might just be a cursory check, no pun intended, but they're doing some review of the code.

**11:46** · And for a PR to get merged and to know that that code is going to production and someone is going to be responsible for that code, it is a higher bar than I just generated a bunch of code and I just like vibed out this prototype, right? So, that's pretty interesting and I think it speaks back to what I was saying where the P99 people are really trying to get the most out of these models and figure out how to kind of reimagine their workflows. Now, on context, this one is maybe not as interesting, but I think still pretty pretty interesting as kind of a footnote.

**12:17** · A lot of these things, the coding agents and the harnesses are taking care of you and handling it behind behind the scenes, but over time, you're going to see a lot more input tokens, which makes sense. Like, you you give the models, um, you know, a pretty you know, relatively simple prompt and then they go and do a lot of work for you. So, when you look at this input mix, 90% of the input output token volume, it's making the context that dominant part of the non-cached model usage.

**12:45** · And if you jump down to input context, you're seeing that's basically the main token cost now. So, it's dominating that token consumption and it's become the majority of the price equivalent token usage since the start of the year at roughly half of the input output token cost to nearly 70% and now if we drill in like one final time, most of that is going to be cash.

**13:08** · So, the cash read tokens are going to dominate all of that total token activity, which shows really how much this agent work is important to reuse prior contexts, to use prompt caching, you know, there's new strategies that models and model providers are putting into agent um, into the models that they're offering to better take advantage of the cash.

**13:31** · As the context grows, as you ask agents to do these very very long threads or conversations and then compact or self-summarize over time, it's very important that you can cash as much as possible in that. And there's a lot of nuances to do this well with things like tool calling and as these models get more complicated. So, we have a blog post if you want to learn more about how we try to maximize caching across models and providers, but it's a very tough problem.

**14:01** · And kind of to wrap up, the interesting thing to take away is you might think of people working with coding agents or writing code with AI as doing you know simple prompts into a text input or writing plans and reviewing plans and making those changes, but I think increasingly what you're starting to see is more changes accepted without manual review, which is in my opinion, this number is lower than what I think you would expect if you were in the SFX zeitgeist online bubble.

**14:31** · Like 30, what is this? 30 6%? I mean, if you follow just the online hype cycle, you would think that oh everyone's just merging code without review, but I think for most teams like I talked about compliance reasons or software quality maintenance reasons, it's still really important to have that review.

**14:50** · The thing that I take away from this more than anything else for all its pros and cons is that we're starting to build these agent systems where it's really important to figure out how you build this repeatable software factory and you automate the best practices of building software at scale across your team, whether that's building something on top of an agent SDK that kind of abstracts away some of the harness and the models or you're setting up automations that will do security reviews or code reviews or other things.

**15:21** · Uh think this is the the next trend that we're seeing uh where those those automations, those cloud agents, those systems can run overnight. They can run in the background, and they can help you make better quality software, and ultimately a better product at the end of the day um as you continue to improve and redefine what software engineering looks like.

**15:40** · So, that's the report. I know I tried to breeze through it and give some of my commentary, but I found this really interesting. This data is helpful to kind of understand how software engineering as an industry is changing.

**15:51** · So, let me know what you thought was most interesting, and if we should do something like this again.

**15:56** · Peace.