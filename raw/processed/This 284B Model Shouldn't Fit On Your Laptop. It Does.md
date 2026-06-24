---
title: "This 284B Model Shouldn't Fit On Your Laptop. It Does"
source: "https://www.youtube.com/watch?v=9gHcmhUDJfw&list=PLdVLOietcHTD3OjLupQ6oEQWEeKXLVozO&index=5"
author:
  - "[[Prompt Engineering]]"
published: 2026-06-18
created: 2026-06-23
description: "In this video, we will look at DS-4, that enables DeepSeek V4 Flash to run on a 128GB unified memory. I this video I run it on DGX Spark thanks to @NVIDIADeveloper LINK: https://github.com/antirez/d"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=9gHcmhUDJfw)

In this video, we will look at DS-4, that enables DeepSeek V4 Flash to run on a 128GB unified memory. I this video I run it on DGX Spark thanks to @NVIDIADeveloper  
  
LINK: https://github.com/antirez/ds4  
Blogpost: https://engineerprompt.ai/writing/dwarfstar-4/  
  
My voice to text App: whryte.com  
Website: https://engineerprompt.ai/  
RAG Beyond Basics Course:  
https://prompt-s-site.thinkific.com/courses/rag  
Signup for Newsletter, localgpt:  
https://tally.so/r/3y9bb0  
  
Let's Connect:  
🦾 Discord: https://discord.com/invite/t4eYQRUcXB  
☕ Buy me a Coffee: https://ko-fi.com/promptengineering  
|🔴 Patreon: https://www.patreon.com/PromptEngineering  
💼Consulting: https://calendly.com/engineerprompt/consulting-call  
📧 Business Contact: engineerprompt@gmail.com  
Become Member: http://tinyurl.com/y5h28s6h  
  
💻 Pre-configured localGPT VM: https://bit.ly/localGPT (use Code: PromptEngineering for 50% off).  
  
Signup for Newsletter, localgpt:  
https://tally.so/r/3y9bb0  
  
  
00:00 Can It Run Locally  
01:42 Why Big Models Don’t Fit  
02:39 Quantization Limits Explained  
04:26 Dwarf Star Selective Quant  
07:56 Calibration and Validation  
09:42 SSD Streaming Ends RAM Cliff  
15:34 Benchmarks Demo and Wrap

## Transcript

### Can It Run Locally

**0:00** · Okay, so is unified memory good for running capable models? This is Deep Seek V4 Flash.

**0:08** · 284 billion parameter model, one of the most capable open weight model that we have seen. Now, this model shouldn't fit on any of these devices.

**0:18** · Memory requirement for this, stored the normal way, is almost four times what these devices have. But, you can still run this device, but it runs on both of them at real usable speed. And how it runs is one of the most interesting piece of system engineerings that I have seen this year.

**0:37** · This is a project called Dwarf Star from the creator of Redis.

**0:41** · Let me draw exactly how this works.

**0:45** · Okay, so let's start with this problem.

**0:47** · Small language models have gotten really good. You can run a 1 billion or an 8 billion model on basically anything now.

**0:54** · They're fast, they're private, they're free. And for most of the tasks, they're genuinely all you need. But, here's the uncomfortable truth. Our capability still scales with size. The bigger models are simply better at reasoning, at coding, at tool usage.

**1:13** · Now, Deep Seek V4 Flash is really good at agentic coding tasks.

**1:19** · This is what we would call a quasi frontier performance from an open weight model.

**1:24** · The problem is that the models worth running are exactly the ones you can't run. They live in data centers behind APIs, even though if they are open weight models.

**1:35** · So, the question is how do you get a model like that onto hardware that you actually own?

### Why Big Models Don’t Fit

**1:42** · Okay, but first let's talk about why exactly they don't fit. So, if you have a 284 billion parameters stored each one at 16 bit, you need 568 GB just for the weights.

**1:58** · Now, a maxed out MacBook Pro or DGX Spark gives you 128 GB.

**2:05** · So, we are not close. Now, even if you cut every weight to eight bits, you still need 284 GB, which is more than double the VRAM that these devices have.

**2:18** · And that's actually the main issue with local models.

**2:22** · It's kind of binary. Either the model fits in memory or it doesn't run at all.

**2:27** · So, if you're using a hosted version of open weight models, you're still accessing it through an API. And basically, it's the same as paying for OpenAI or Anthropic.

### Quantization Limits Explained

**2:40** · Now, the standard escape hatch is quantization. And to understand what Dwarf Star does differently, you need to see what quantization actually does.

**2:49** · So, every weight in the neural network is just a number. Most of them tiny values scattered around zero.

**2:57** · At 16 bits, you have 65,000 possible values to store each one, which is plenty of precision. Now, quantization says, "Use fewer levels."

**3:09** · At four bits, you're only looking at 16.

**3:13** · Now, if you push it to two bits, you're just looking at four different levels.

**3:17** · And our 568 GB model shrinks to around 80 GB.

**3:24** · So, you could see, this fits. So, why doesn't everyone just do this?

**3:30** · Because precision is not free. Here's what actually happens when you try to squeeze it too hard.

**3:35** · Some weight matters more than others.

**3:38** · When an important weight gets snapped into the wrong level, the layer now computes a slightly wrong answer.

**3:47** · And transformer is deep. The slightly wrong answer feeds the next layer and the next.

**3:54** · Which means errors are going to compound.

**3:57** · You can see it in the quality curve.

**3:58** · Down to about four bits, models hold up surprisingly well if they are large models. Below three bits, quality historically falls off a cliff on its own.

**4:09** · So, native two-bit quantization gives you the model that fits in the RAM, but isn't worth running. You saved the memory, but threw away the intelligence.

**4:19** · Unless, and this is the key insight of the whole approach, you don't quantize everything.

**4:24** · Okay, so this is where Dwarfstar comes in. DS4, a project by the creator of Redis, and it's built with a philosophy I find refreshing. Instead of a general engine that runs everything like llama.cpp or ollama, it runs exactly one model family, which is Deep Seek V4, and it optimizes everything around it.

### Dwarf Star Selective Quant

**4:47** · It's basically a self-contained C, and it ships its own custom-built model files tuned for this exact engine.

**4:57** · And the idea is that it isn't that it seems to work, it actually is measured.

**5:03** · Now, this is interesting because if you look at Deep Seek V4, it's not just a one giant dense network, it's a mixture of experts.

**5:12** · And that structure is exactly what makes this whole trick possible. Okay, so let's talk about the architecture a little bit. Inside each of its 43 layers, there is a router, and behind that router sits 256 separate experts, which are basically small feed-forward networks across the whole model, and there are thousands of them.

**5:36** · So, when a token comes through, the router picks just a handful of experts to process it.

**5:42** · The rest are completely idle for that token. That's why MoE is a usually much faster compared to dense networks.

**5:50** · Now, there is also a small shared expert that every token passes through.

**5:55** · Keep an eye on that one.

**5:58** · It matters in a minute. Now, if you add it up, you get the magic ratio. 284 billion parameters total, but only about 13 billion active for any given token.

**6:10** · So, the model itself is huge, but per token, it is actually pretty tiny. So, now the question becomes if you have to crush some of the weights down to two bits, which one do you pick?

**6:24** · Dwarf Stars answer is beautifully simple.

**6:27** · Now, to explain this, think of the model as a building. The attention layers, the routers, the shared experts, the output heads, they are the load-bearing walls. Every single token flows through them, so damage here propagates everywhere.

**6:43** · But, the routed experts, that's actually the furniture within the building.

**6:48** · There's a massive amount of them.

**6:50** · It's most of the building, but each token only ever touches a few of of those pieces.

**6:58** · The routed experts gets crushed or quantized to around two bits. Everything load-bearing stays at four bits, effectively untouched.

**7:08** · And the reason this works with 256 experts per layers is that there is redundancy.

**7:15** · Any single token only meets a few quantized experts, which are switched between high-precision layers. The error never gets the chance to compound like it did in dense cases.

**7:27** · Now, the results, the model drops from 268 GB to about 81 GB. Suddenly, you can see that it's under the 128 GB of MacBook Pro or DGX Spark.

**7:41** · And all of a sudden, that thing that couldn't fit now fits.

**7:45** · Okay, but what about the performance?

**7:47** · So, they actually are running coding agents.

**7:50** · They call tools that reliably. But, how would you actually know that? That brings us to the calibrations. Now, there's a second layer to this trick, and it's the difference between guessing and measuring.

### Calibration and Validation

**8:02** · Now, before quantizing anything, they run the model over nearly 4,700 real prompts, which is about 3 million tokens.

**8:12** · These include code reviews, math problems, agent tool calls, and long documents.

**8:18** · And while it runs, they record which weight column actually carry signal, which parts of each expert the model genuinely leans on while doing real work. Then, the quantizer uses that map.

**8:33** · The heavily used columns gets protected, placed more precisely on those four levels. The rarely used ones absorbs the error.

**8:43** · The calibration set includes tool calling prompts in Deep Seek on format.

**8:48** · They tune the quantization for a gentle work exactly where cheap quant usually fall apart.

**8:56** · Okay, so the model fits, and it was quantized carefully. The obvious question is how much did it lose on performance?

**9:05** · Now, they take 100 prompts, send them to the official Deep Seek API, and record exactly which token it produces.

**9:12** · This is going to be used as ground truth. Then, they ask the two-bit local model, "How much probability did you assign to each one of those exact tokens?" Because we have access to those probabilities.

**9:25** · That's basically the negative log likelihood token by token measured of drift.

**9:32** · And if the quants were damaged, the two curves would split apart. But, in their case, they actually track pretty closely.

**9:40** · Okay, so do you need a 128 GB machine to run this? What if you have 64 GB GB of unified memory? Now, in the normal approach, you would run into this uh cliff again.

### SSD Streaming Ends RAM Cliff

**9:54** · But if you're using a MacBook or even GB 10, there's another pool of memory sitting right there that you can access, and that is the SSD.

**10:02** · Which is usually multiple terabytes on modern machines.

**10:06** · And it reads at gigabytes per seconds.

**10:10** · So, here's the question. Do all those routed experts actually need to sit in RAM? Or could they live on disk?

**10:18** · And show up only when they are called?

**10:21** · So, this is SSD streaming, and it's actually a pretty interesting part that you definitely want to understand. So, in streaming mode, the load bearing weights, which are attention, router, and shared experts, sits permanently in RAM. They're needed for every token, so they never leave.

**10:41** · Now, next to them, Dwarf Star carves out an expert casher.

**10:47** · Which is basically a set of slots pinned in memory, each holding one complete expert.

**10:53** · And the full set of experts, which is about 11,000 of them, stays down here on SSD inside the model file.

**11:03** · Now, when the token comes in, the router picks its experts. And if they're already in cache slot, that's a hit. And it's going to be a fast path.

**11:14** · There's no disk involved.

**11:16** · But if one misses, the engine reads the single expert straight off of the SSD, drops it into the slot, and evicts which which expert has been called for the longest.

**11:29** · But here's the interesting thing. The usage actually follows power law. Some experts are just popular.

**11:35** · And this dwarf star ships pre-filled hot list and preloads the popular ones at startup, so cache starts warm.

**11:45** · Now, the result is long prompts still processes fast and generation slows down only as much as you miss the cache, which leads to a complete reframing of that cliff.

**11:57** · Okay, so remember we talked about RAM cliff, whether everything fits in or nothing.

**12:03** · Now, here is what it looks like. With streaming, there's no cliff anymore.

**12:08** · There's just a slope.

**12:10** · So, RAM stops being a wall and just becomes a tile. And this basically controls the cache hit rate now.

**12:18** · So, if you have a smaller cache, there are going to be more misses. It's going to be slower, but everything will still run because you are putting the most important bits on the SSD now.

**12:30** · Now, the SSD streaming turns the amount of RAM from a hard cut off, which defines whether you can run this model or not, into a continuous spectrum of speed levels. So, with this whole project, the question is no longer, "Can I run this model?" It's, "How fast I can run this model?"

**12:48** · Okay, so now weights are only half the story. The other monster is the KV cache, which is basically the model's working memory for your orchestration.

**12:57** · Normally, every token you process leaves a record in every layer.

**13:02** · At a million tokens of context on a classic architecture, that cache alone can outgrow the model itself.

**13:09** · Now, Deep Seek 4 has a clever layered design. Each layer keeps the most recent 128 tokens raw full resolution.

**13:19** · That's basically your local context.

**13:22** · Now, older history gets compressed a long time.

**13:25** · Half the layers pull every four tokens into one row with an indexer that picks the 512 most relevant rows to attend to.

**13:36** · The other half compacts 128 to one.

**13:40** · So, the result of this is that a million token of context costs about 26 GB.

**13:47** · And because it compacts, Dwarf Star treats it as a first-class disk citizen.

**13:53** · Whole session gets saved as a file.

**13:57** · So, if you just reopen that file, you can resume the model instantly.

**14:02** · There is zero reprocessing. So, say if you had a two-hour-long session with the model, that is just a file that you can come back to.

**14:12** · And if you want to push past one machine entirely, Dwarf Star does distributed inference, which is pretty great for running large models. So, say you take two MacBook Pros, you just connect them via a Thunderbolt 5 cable.

**14:30** · Now, in this case, you split the model by layers.

**14:34** · First half lays on one machine, second half on the other machine.

**14:38** · Now, for processing your prompt, this becomes an assembly line. So, while machine B chews on chunk one, machine A is already working on chunk two.

**14:50** · And that pipeline genuinely pays. On a 64,000 token prompt, Prefill runs 1.85 times faster than a single machine.

**15:00** · Okay, but the generation is actually the footnote here. So, it's one token at a time, so the pipeline collapses into ping-pong across the cables, which is going to be around 19% slower.

**15:14** · So, this trick is for fitting larger models and faster prompt processing, not faster generation.

**15:21** · But here's the thing, with this trick you can run the bigger 1.6 trillion parameter model at almost 11 tokens per second.

**15:30** · Which is kind of incredible.

**15:32** · All right, let's look at some benchmarks. So, all of this is from the repo's published benchmarks. Same model two-bit quantization.

### Benchmarks Demo and Wrap

**15:39** · So, these are the generation speeds for different MacBook Pros.

**15:44** · Now, if you're running this on DGX Spark, you get slightly lower speed of generation.

**15:51** · Now, prefill is where these machines fly. 250 to nearly 470 tokens per second on a long prompt.

**16:00** · These numbers are for V4 flash, but you can actually run the Pro 1.6 trillion model at a reasonable generation speed at 9.6 tokens per second at 32K context window.

**16:13** · Which is readable speed for a model of that size on a hardware you own.

**16:18** · Which is kind of incredible. Okay, I'm going to show you a live demo, but let me zoom out because I think this project matters beyond a single model.

**16:27** · First, it really shows what you get when you own the whole stack.

**16:31** · In this case, it's the engine, the quantization, the validation, even the coding agent, and tunes them for each other instead of just trying to maximize everything in general.

**16:42** · Second, the reframing of RAM as a dial and not the wall kind of really changes what you can run on these systems locally.

**16:51** · The SSD in your laptop is going to start becoming part of the memory hierarchy for AI. And the third is the ability to run a quasi frontier model completely locally on your MacBook or DGX Spark.

**17:06** · That is kind of incredible.

**17:08** · Okay, so let me show you a practical example of this. Right now, I'm using the DeepSeek V4 flash on DGX Spark that has a GB of VRAM.

**17:19** · In order to set it up, just go through this Dwarf Star for Reaper. It has detailed instructions on how to get started.

**17:28** · Or you can simply ask a coding agent to set this up on either your MacBook or on DGX Spark.

**17:37** · So, in my case, I used Cloud Code to create this UI. I'm currently working on a harness specifically designed for this model, but at the moment, I just want to show you the chat version. Right now, the model is using DS4 server on my DGX Spark, and I am accessing that on the same network. Now, to show you how this works, we can just click on one of these questions. You can actually see the the fire time to first token.

**18:07** · Then, we're going to look at the free prefill speed, decode speed, also the total number of tokens, right? In real time, you actually see the GPU use, and the beauty is that once you load the model, then, since it's using the SSD for the carry cache, you don't really see much impact on the memory that you're going to be needing.

**18:32** · So, this was a quick response.

**18:34** · Now, in my case, I'm getting about 13 tokens per second, which actually is pretty usable. Okay, I'm going to ask it to create something more challenging. Uh so, I'm asking it to create an encyclopedia of uh 25 legendary Pokémon. Uh you actually see that the time to first token was about 600 ms, which is pretty good.

**18:56** · Now, it's going to take its good time uh in order to generate the whole response, and I'm going to show you what the actual speed and the number of tokens actually look like.

**19:08** · Now, again, the GPU utilization is somewhere around 93% peak, which is pretty good. This is a 284 billion parameter model running completely locally on consumer hardware.

**19:24** · Okay, so for this it generated about 8,000 tokens at 11 tokens per second.

**19:28** · Almost 10 minutes and and the peak chance around 93%. Now, the interesting thing is that the response that it generates are very close to the officially hosted DeepSeek.

**19:39** · Okay, so I ran the same prompt on the DeepSeek website using the instant model.

**19:45** · Now, here is the output that is generated by the official hosted version.

**19:50** · Now, for the same prompt these are the generations from our locally hosted version that is running on GB10.

**19:58** · Again, keep in mind this is a two-bit quantized version with selective quantization, but still it preserves the behavior of the original model. So, this is pretty close to what the hosted version generates, which means you can run these large language models on consumer grade hardware locally now.

**20:21** · I highly recommend to check out the Dwarf Star Four project because I think this is the step in the right direction, especially what we are seeing with the whole Anthropic fable drama.

**20:34** · I think having local models which are actually close to the frontier are going to be very critical. Now, at the moment they are mainly focusing on the DeepSeek models, but we could see similar projects dedicated to other models like the newly released GLM 5.2.

**20:53** · Anyways, I hope you found this video useful. Thanks for watching and as always, see you in the next one.