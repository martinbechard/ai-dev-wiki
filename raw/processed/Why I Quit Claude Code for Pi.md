---
title: "Why I Quit Claude Code for Pi"
source: "https://www.youtube.com/watch?v=Sphk79piiqM&list=PLdVLOietcHTD3OjLupQ6oEQWEeKXLVozO&index=20"
author:
  - "[[This Dot Media]]"
published: 2026-06-09
created: 2026-06-23
description: "Claude Code popularized AI coding agents, but what happens when developers want to customize the harness itself?Brandon Mathis explores Pi, an open source coding agent designed around extensibility,"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=Sphk79piiqM)

Claude Code popularized AI coding agents, but what happens when developers want to customize the harness itself?  
  
Brandon Mathis explores Pi, an open source coding agent designed around extensibility, community-driven development, and direct control over the agent workflow. The discussion covers custom extensions, plan mode, to-do management, model flexibility, context visibility, token tracking, and the growing role of coding harnesses as the layer that shapes how developers work with AI.  
  
Topics include open source vs. vendor-controlled agents, harness customization, extension ecosystems, subagents, MCP integrations, workflow design, context management, AI tooling economics, and why extensibility may become more important than the underlying model itself.  
  
Featuring practical demonstrations of building and modifying Pi extensions, customizing agent behavior, and comparing the experience to Claude Code and other AI coding tools.  
  
In this demo, you'll learn:  
\- How Pi's open source architecture differs from Claude Code and other AI coding agents  
\- Why coding harnesses and extension systems are becoming a critical part of AI-assisted development  
\- How to build custom Pi extensions for workflows like planning, to-do management, session tracking, and agent controls  
\- Ways to switch between models such as GPT-5.5, Codex, Kimi, and others within a single coding environment  
\- How greater visibility into context usage, token consumption, and agent behavior can improve engineering workflows and decision-making  
  
Brandon Mathis on Linkedin: https://www.linkedin.com/in/mathisbrandon/  
This Dot Labs Twitter: https://x.com/ThisDotLabs  
This Dot Media Twitter: https://x.com/ThisDotMedia  
This Dot Labs Instagram: https://www.instagram.com/thisdotlabs/  
This Dot Labs Facebook: https://www.facebook.com/thisdot/  
  
Sponsored by This Dot: https://ai.thisdot.co/

## Transcript

**0:00** · All right, developer world. It's time for me to come clean with y'all about something, and that's that I'm not a Claude Code user anymore. For over the past couple months, I have been suffering from the same problem with Claude Code, and that's that it doesn't provide enough opportunity for extension for me. Yeah, sure, you can write custom skills, and you can even write custom hooks, but hooks just spawn a separate process. I want to be able to go directly into the code and modify the harness itself. I want a proper extension layer.

**0:30** · I want to know that the open-source community has had a say in the direction of what my coding agent is going to be doing a month, 2 months, 3 months, 4 months, 5 months into the future. So, with all that being said, let me introduce to y'all my new favorite coding agent of choice, and that agent is the Pi coding agent. Now, Pi does a couple things differently from other agents. The main thing is that it runs in auto mode by default. That means that y'all mode is just turned on all the time.

**1:01** · If your agent can run a command, it will run the command. Before you pick up Pi, make sure that you know what you're doing, and make sure that you understand the need of why this agent exists. The first thing that I think is really important is that Pi is a minimal coding harness. That means no additional system prompt context prompt that you don't control and you don't know anything about. I think that the engineering community at large is learning that the more control engineers have over their context, the better the results of their development experiences.

**1:32** · Installing Pi is done just like any other terminal agent. I mean, they you can run a curl command, you can use npm, pnpm, bundle, tons of different options for you. This is just really delivered as an npm package. You can see here there's a bit of a demonstration video on Pi's homepage about what the coding harness looks like. It's extremely minimal, just a basic input block, text scrolling right in front of you. It even showcases the LLM's own internal thinking inside of the agent.

**2:02** · Another thing that I think is really important to know is that you can access every single harness that's on the market with this agent. It's always staying up to date. My problem with Claude Code was that they were limiting me only to using the Opus model. I want to use Codex. I want to use Kimmy K2. I want to use GPT 5.5. I want to use Quinn. I want to use all the other esoteric models out there to try everything possible. And I think it should be just as easy as running a slash command to get this done. I personally think that Claude Code doesn't want to see this future come to reality.

**2:32** · Now, yes, there are tools out there like Open Code and Forge Code.

**2:38** · These are fine, but I just personally prefer the lightweight extensibility flavor that Pi provides. So, I don't want to talk down to other open-source coding agents that are out there, but I've tried a few and Pi so far is my favorite one.

**2:53** · I wanted to take a brief minute to give you all some insight into what my workflow session with Pi looks like and just what it looks like to drive this thing. Now, already out of the gate, I've installed a couple extensions that you'll need to be aware of. Number one is I've made my own little to-do list manager. This is a very nice utility that I think any coding agent should have. Pi doesn't come with one by default and I like that opinion because I have opinions about how my to-do list should look and I like to have those opinions expressed in my tool.

**3:19** · And I also like to have the opportunity to modify that stuff if I see that it's necessary. Another extension that I've built myself is the status bar all the way at the bottom down here. I want to have a custom session name, which I have Pi generate using an LLM based on the first prompt that I feed it. I want to be able to see what directory I'm working inside of. I want to be able to have full insight into my context utilization, tokens up and down, total spend, how much of my current session am I utilizing.

**3:47** · I don't think that it's important to be paranoid about this stuff, but I do think it's important right now in this era as an engineer to have insight, non-stop insight into this stuff, so we can make informed decisions when even more expensive models come out, and they will be coming out. Truly, I just have to say as an aside, like we're honestly in the baby phase of AI pricing and LLM pricing, so really all expect those token prices to keep on rising because I don't think they're going to be going down from here.

**4:15** · It's going to be part of our job to figure out how to most efficiently utilize our tokens. So, getting an idea of how quickly the spin goes up is going to help us be able to make these decisions in the moment. I want to take a quick minute to take a look inside of my own personal Pi configuration directory and showcase to y'all just how the customization of this tool looks. So, let's just leave our running Pi session going in the background, full screen our tmux pane here, and I want to first showcase to y'all this extensions directory that's in here.

**4:44** · This is where all of your extensions for Pi are going to live. And I've many extensions for Pi now because Pi has knowledge on how to modify itself. Baked directly into the system prompt are instructions on where the most up-to-date docs are for Pi, which are wrapped up in the source code that's on your machine. So, even if Pi can get the answer that it needs by looking at its own docs, it can inspect its own source code. Claude can't do that. I've got a couple small extensions that I wrote.

**5:16** · One is this Pi help extension. All of this stuff was written in JavaScript. All of this is generated code, and all that this extension does for me is provide a {slash} help command that I can give to Pi to ask it any question that I want. So, fire up Pi, {slash} help, how do I make skills?

**5:32** · Pi immediately knows right away through my extension to feed in an initial system prompt, tell, you know, Pi where the location of all of the documentation is at, let it go find that, and just right away it's coming to me knowing that I'm just more asking a question about it and less so much about the world. Now, obviously, you know that I really love plan mode, so one of the extensions that I had to make immediately was also an extension for plan mode.

**6:00** · Again, most of this is JavaScript, most of it is generated, and that doesn't really bother me so much because these extensions, they're not going to leave my computer, and they suit the use case that they need to right now. And I honestly have been looking forward to throwing all this code away in the near future and rewriting it all because Pi is a constantly growing agent harness and the community is growing.

**6:22** · So, I'm not going to fall in love with any specific APIs or SDKs or extension flows until we hit some form of like 1.0 maturity. For that reason, I would say don't be scared to just make extensions, but maybe think twice before you try to release them publicly and become a Pi extension maintainer. This is a newly developed territory, so a lot of things are going to be changing for extension managers.

**6:46** · Couple other extensions that I've made, I've got my auto session name extension, I've got an extension that allows me to confirm when I want to quit or abort out of Pi. This was only 54 lines long. I kept finding that I would send a prompt to Pi, and I would hit the escape button on accident because I'm a Vim user, and then all of a sudden my Pi session would terminate. Now, whenever I send Pi a command and I hit escape, with that new extension, when I hit the escape key, I'm given a prompt, do you want to abort Pi, yes or no? If I say yes, I'll abort the operation.

**7:18** · That was just the natural behavior of Pi, the immediate abort I wasn't liking, so I was able to modify it instantly, and it only took me 5 minutes to do so. If you want to give Pi a shot, you don't need to go it alone.

**7:30** · There is a community extensions website that's going to be chock-full of some really valuable extensions out there for you that you may like. You can go straight here, you can sort by most downloaded, and right out of the gate, I'll agree with a few of the extensions that are on here. The Pi subagents extension is awesome. Pi doesn't have subagents by default. It's just not something baked into the harness, but the harness is fully extendable. So, one of the first things that the community decided to do was make a Pi subagents extension, and I personally love that.

**8:00** · We've got a few other extensions here.

**8:01** · Pi MCP adapter, another important thing to note. Pi doesn't come with MCP support out of the box, but if you want it, just build an extension for it. We have Pi web access as well that'll let Pi be able to search the internet for things. We even have a Pi extension manager that it's allows us to search for extensions, install, uninstall extensions, and the list really just keeps going on and on and on. If you're thinking about this, uh Brandon, why do I have to do all this? I can just use Cloud Code and I get all this functionality. Yeah, sure. You totally could.

**8:30** · You could totally just use Cloud Code and get all that functionality, but there's also a lot of functionality in Cloud Code you don't know about and you probably don't need. And personally, I think that if you want to be the most effective with a tool, you need to understand everything about it. So, I think you will use these extensions a lot more if you go in and install them and understand what it is they're doing.

**8:51** · Web search, subagents, MCP adapter. All of these are useful things, but I think all of them can be implemented in different opinionated ways. And personally, I think that's a good thing.

**9:01** · Okay, so let's take a look at what it looks like to work with Pi. I want to build a small video game here which is pretty much going to be a copy of Pitfall. to have a low poly character that can run left and right and jump over pits. And through that, I just want to show y'all what the user interface of Pi is like, what the flow is like, and what it is you can expect to see when you're running this coding agent.

**9:20** · Starting up Pi gives you a pretty minimal screen about what version you're running, what skills are loaded in, what initial prompts are available to you, and what extensions are running. Let's start with our first prompt to make a plan. I've created my own custom plan mode, so I'll just run {slash} plan here and say, "Let's make a game that has a low poly character that can run left, right, and jump over pits. I want to be able to play this game in the browser.

**9:50** · Now, you'll see here something that I really like about Pi is we can see that it's thinking is written clearly inside the console log in italics, and we can skim over that, and then the tool calls are highlighted in green. So, we know when a tool's being called, when internal thinking is being done, and then finally when the agent responds to us, which is just in plain text. Looks like the plan here is relatively straightforward. You just usually I skim over this, and then my extension kind of continues to drive, which is we're going to execute the plan. We should clear out our context window and start execution flow for us.

**10:20** · Now, as you may notice here, it seems like my to-do list for plan mode and my to-do list for to-dos is starting to conflict here. So, maybe I need to take a look at these two extensions and get them to resolve each other a little bit better. Now, I'll note here that it looks like my to-do list and my plan mode to-do list is kind of colliding. So, let's make a couple modifications real quick to our extension while this work is going on.

**10:46** · I'll just go into my Pi directory, fire up Pi, and this time let's just talk to it.

**10:53** · Hey Pi, so my to-do extension and my plan mode extension seem to be colliding. Plan mode showcases to-dos in my TUI, but so does the to-dos extension.

**11:04** · Modify my custom plan mode extension so it doesn't show those to-dos anymore and I just see them rendered out using the to-dos extension that I already have installed.

**11:16** · From here, we're just going to let it run and see what happens.

**11:20** · Now, again, I don't want to be a broken record and continue to repeat myself, but this is a crazy powerful workflow.

**11:27** · The ability to identify a way that your agent is working that you don't like and isn't beneficial to your workflow and then be able to modify the harness directly so that does work the way that you want is going to be the actual efficiency gain that everyone wants to see. Slamming everybody into the same shape to for everyone to be using Claude Code, I don't think it's going to be working out long-term for the software development industry.

**11:50** · Either Anthropic gets their act together and open sources Claude Code or these open source projects are just going to take over and Anthropic is just going to be a provider of an LLM. It's really about the tools that uses AI and not so much about the AI anymore. And just like that, my extension's done. On top of that, Pitfalls completed as well. Let's see how things went.

**12:30** · Well, you can see the game works, but it's really not well designed. I don't think I can jump over that second pit.

**12:35** · Well, there you have it, a fully extensible and open source coding agent.

**12:39** · I personally have been using Pi now for going on 4 weeks exclusively with the GPT 5.5 model on my code X subscription and I'll say that I really don't notice a difference between using it and Claude Code and it gives me all the added benefit of being extensible. However, you do have to incur some higher utilization pricing whenever you're using these agents that aren't produced also by the LLM vendors. Personally, I would like to see this change some, but I don't think it is and I actually think this is a float towards the norm.

**13:08** · The people that are using Claude Code subscriptions and are enjoying these high usage rates need to understand that every single token that you generate with Claude Code is heavily subsidized right now. So, if you take a look at Pi, you have lots of different opportunities. You could use cheaper agents, Kimmy K 2.5, or possibly even local agents running on Ollama. I would suggest everyone to give this agent a download, give it a try, and then try some different agents, and see if maybe you can quit Claude Code, too.