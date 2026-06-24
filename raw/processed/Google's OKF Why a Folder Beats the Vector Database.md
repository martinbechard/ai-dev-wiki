---
title: "Google's OKF: Why a Folder Beats the Vector Database"
source: "https://www.youtube.com/watch?v=P_E29-87THI&list=PLdVLOietcHTD3OjLupQ6oEQWEeKXLVozO&index=8"
author:
  - "[[Devsplainers]]"
published: 2026-06-22
created: 2026-06-23
description: "Google just turned a folder of plain text files into an official AI standard — and it quietly makes the expensive vector database optional. It's called the Open Knowledge Format (OKF), and it's the mo"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=P_E29-87THI)

Google just turned a folder of plain text files into an official AI standard — and it quietly makes the expensive vector database optional. It's called the Open Knowledge Format (OKF), and it's the most-talked-about release in agent memory right now.  
  
This is the full breakdown of what Google actually shipped, why a folder of Markdown beats RAG and the vector database for AI memory, and the three catches nobody's mentioning.  
  
📬 I send the hotter takes that don't make it into the video every Tuesday → https://devsplainers.com/takeouts/  
  
⏱️ Chapters  
00:00 — The idea that broke 2 years of AI orthodoxy  
00:34 — How RAG and vector databases actually work  
01:28 — The "LLM wiki" idea Google just standardized  
02:30 — What Google's Open Knowledge Format really is  
03:37 — Why a folder of text files beats the vector database  
04:53 — The catch: staleness, messy Markdown, and meaning  
06:14 — The real moat (and Google's BigQuery strategy)  
07:13 — Will OKF actually stick?  
  
What you'll learn:  
• Why RAG re-does the same work on every single query  
• What "embeddings" and vector databases are doing under the hood  
• The LLM-wiki idea: the AI writes the wiki, you just ask the questions  
• How OKF's spec works — bundles, one-concept files, the single required field  
• Why plain text in Git beats a database for agent knowledge  
• The freshness problem that breaks OKF on shared teams  
• Why this is NOT an SEO trick and NOT a replacement for MCP  
  
What is the Open Knowledge Format? OKF is a Google Cloud spec (published June 2026) for storing knowledge as a folder of linked Markdown files that AI agents can read directly — no embeddings, no vector database, no server. Instead of re-deriving knowledge from scratch on every query the way RAG does, you build it once into plain text the model reads like a developer reads a codebase.  
  
🔗 More Devsplainers explainers:  
• Vector Databases, explained → https://youtu.be/sKSX1zKjzWc  
• MCP (Model Context Protocol), explained → https://youtu.be/To5t2DsSMP0  
• Google's AI Graveyard → https://youtu.be/gLWQAE3I1A4  
  
📖 Sources:  
• Google Cloud Blog — "How the Open Knowledge Format can improve data sharing"  
• Open Knowledge Format spec — GitHub (GoogleCloudPlatform)  
• Andrej Karpathy — "LLM wiki" gist, GitHub  
  
#OpenKnowledgeFormat #VectorDatabase #Google #RAG #AIagents

## Transcript

### The idea that broke 2 years of AI orthodoxy

**0:00** · For 2 years, the entire AI industry agreed on how to give a model memory.

**0:05** · You chopped your documents into thousands of fragments, turned each fragment into a long list of numbers, and paid to store them in a special database. Then, this spring, one of the most respected names in AI looked at all of it and said, "Just use a folder of text files." And it worked better. Now, Google's turned that folder into an official standard. Developers are calling it the most obvious idea they've ever seen, and they might be exactly right.

### How RAG and vector databases actually work

**0:35** · The complicated version existed for a reason. Everything an AI needs to do its job is scattered. A metric's definition lives in one database. Its logic in some pipeline. The reason it changed in a 6-month-old pull request. And the rest in the head of an engineer who left in March. The standard fix was a thing called RAG. You take all those documents, slice them into chunks, turn each chunk into a long list of numbers that captures \[music\] its rough meaning, and load them into a vector database.

**1:07** · Ask a question, the system grabs the chunks that look \[music\] closest to it, and hands them to the model. It works, but it never remembers.

**1:15** · \[music\] Every query starts from zero. The model gets a fresh pile of disconnected snippets and has to work out the same connections it worked out an hour \[music\] ago, and the hour before that. That respected name, by the way, was Andrej Karpathy, co-founder of OpenAI, former head of AI at Tesla.

### The "LLM wiki" idea Google just standardized

**1:35** · \[music\] In April, he posted a short file to GitHub for an idea he called the LLM Wiki.

**1:41** · \[music\] And it flips RAG on its head. Instead of the model re-deriving everything the moment you ask, you build the knowledge up once \[music\] into a folder of plain text files that link to each other. A living encyclopedia the model can read the way a developer reads a code base.

**1:59** · People hear a folder of notes and \[music\] assume they're the one writing the notes. Wrong way around. You don't write \[music\] the wiki, the AI does. You bring it new material and ask good questions. It handles the summarizing, the cross-referencing, the filing, all the upkeep nobody ever keeps up with.

**2:18** · Karpathy's own line for it, Obsidian is the IDE, the LLM is the programmer, the wiki is the code base. The folder is the part you own, the model is the worker who maintains it. This is where Google comes in. On June 12th, Google Cloud took that loose community idea and published it as a formal spec, the Open Knowledge Format. The spec is almost comically small. A bundle is a folder.

### What Google's Open Knowledge Format really is

**2:45** · Every file is one concept, a table, a metric, a playbook, whatever you've got.

**2:50** · The file's path is its name. Links between files form a graph. There are two special file names, one that lists what's in a folder and one that logs changes. And there's exactly one hard rule. Every file has to say what type of thing it is in one field. The spec also orders any tool reading a bundle to forgive almost everything. Unknown fields, broken links, even files it can't parse.

**3:17** · An enterprise standard from Google whose defining feature is how little it demands \[music\] and how much it lets you break. You could build it in an afternoon. One thing Google dropped though, Karpathy's instructions for how the AI maintains the wiki. They kept the folder and left out the part that keeps it alive.

### Why a folder of text files beats the vector database

**3:37** · Back to the reversal. The folder wins and it wins for three reasons. First, when the work happens. RAG \[music\] does its thinking at question time. The wiki does it once up front when the bundle is built, connecting concepts, \[music\] flagging contradictions, writing the summaries. Pay that cost a single time, then just read the finished answer.

**3:59** · Second, skill. A model can only hold so much in its head at once, and a big \[music\] company has thousands of these files. Each folder carries a short table of contents.

**4:10** · \[music\] The model reads that first, picks the one file it needs, and skips the other 9,000. It never chokes on the whole library. Third, it's only text. It lives in Git exactly like code. You can diff it, review it in a pull request, \[music\] zip the whole thing and hand it to a model running offline on a laptop. You don't need a database, a server, or an API key to read it. If you can open a file, you're good. Two quick mix-ups to clear up. This isn't competing with MCP.

**4:40** · MCP is the pipe that moves data around live. This is the cargo that moves through it, and it's not an SEO trick.

**4:47** · Nothing in it helps a search engine find you. It's private knowledge for your own agents. The pitch is that the AI does the bookkeeping humans always abandon, but the spec has no mechanism to keep anything current. There's a field for a timestamp, fine. A field is not a process. Nothing in the format updates itself. This works beautifully when one person owns one folder. On a shared team folder, it goes stale in a month.

### The catch: staleness, messy Markdown, and meaning

**5:13** · Nobody volunteers to tend it, and the agent starts answering from knowledge that expired back in spring. That's catch one. Catch two is funnier. The whole idea rests on AI being a tireless, accurate librarian. In practice, language models are bad at writing clean markdown at scale. They botch the formatting, mangle headers, invent links to files that were never created. And how did Google fix the messy librarian problem? They didn't.

**5:41** · They changed the spec to order every reader to forgive the \[music\] mess. That permissive rule is damage control with a nicer name. The deepest catch is the last \[music\] one. The format standardizes the container, not the meaning. The one required field is a free-form label. Your team writes BigQuery table. Mine writes table. Someone else writes relational asset.

**6:06** · They're all valid, but each is speaking a different language. You can ship the box anywhere. Agreeing on what's inside is still on you.

### The real moat (and Google's BigQuery strategy)

**6:14** · Strip all of this back and you land on a line some developer wrote that stuck with me. An agent is basically just a folder of markdown files. Anyone can write markdown. The skill is in how the folder is organized. What's locked versus what the AI can rewrite. What stops it drifting over a long run. The moat is invisible. Two folders can look identical. One holds up in production while the other slowly rots. You can't tell which is which by reading the files. No format can hand you that.

**6:41** · Then there's the part Google would rather you skim past. OKF didn't come out of Google's AI lab. It came from the BigQuery team. Every sample data set ships on BigQuery. The reference tool that writes the bundles runs on Gemini.

**6:59** · And the easiest place to pour a finished bundle is Google's own knowledge product. The one they just renamed for exactly this moment. If you've seen our video on Gemma 4, I guess you can already smell the strategy behind this.

### Will OKF actually stick?

**7:13** · Will it stick? Hard to say. The day it launched, almost nobody outside Google was using it. And \[music\] a standard with one user is just a suggestion. It could easily be the next Google project added to their graveyard. The idea underneath it has already won though. The most overfunded field \[music\] in tech spent two years and a fortune convincing itself that giving a machine memory needed exotic infrastructure.

**7:41** · Then a tidy folder of text files did the job better. Whatever happens to the format, that part isn't going back in the box.