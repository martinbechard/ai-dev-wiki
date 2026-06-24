---
title: "OWASP's Top 10 Ways to Attack LLMs: AI Vulnerabilities Exposed"
source: "https://www.youtube.com/watch?v=gUNXZMcd2jU&list=PLdVLOietcHTD3OjLupQ6oEQWEeKXLVozO&index=7"
author:
  - "[[IBM Technology]]"
published: 2026-03-07
created: 2026-06-23
description: "Ready to become a certified watsonx Generative AI Engineer? Register now and use code IBMTechYT20 for 20% off of your exam → https://ibm.biz/Bdp4DLLearn more about OWASP's Top 10 LLM Vulnerabilities"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=gUNXZMcd2jU)

Ready to become a certified watsonx Generative AI Engineer? Register now and use code IBMTechYT20 for 20% off of your exam → https://ibm.biz/Bdp4DL  
  
Learn more about OWASP's Top 10 LLM Vulnerabilities here → https://ibm.biz/BdpRG6  
  
Are your AI models secure? 🤔 Jeff Crume explains OWASP's Top 10 for LLMs, including risks like prompt injection and data leaks. Discover actionable tips like firewalls and access controls to safeguard your AI systems from attacks and vulnerabilities. 🔒  
  
Read the Cost of a Data Breach report → https://ibm.biz/BdpRG5  
  
#owasp #llmsecurity #aithreats #aisecurity

## Transcript

**0:00** · You know what's catching a lot of teams off guard right now?

**0:03** · How easy it is for an LLM to leak something that it shouldn't, or be steered into doing something you never intended.

**0:10** · One clever prompt, one exposed training file, one sketchy plug-in, and suddenly your helpful AI assistant becomes a security incident just waiting to happen.

**0:20** · That's why the new OWASP Top 10 for AI Large Language Models, LLMs for short, really matters.

**0:28** · It cuts to the most common threats people are running into when they deploy these models in the real world.

**0:34** · And if you're new to OWASP, they're a global nonprofit focused on practical community-built security guidance.

**0:41** · They're the folks behind the classic Top 10 for Web Apps, and now they're doing the same for AI.

**0:46** · You can find all their work at owasp.org.

**0:49** · They came out with a Top 10 for Large Language Models in 2023, but a few years on, we've learned a lot, and that learning is reflected in an updated Top 10 list.

**0:59** · All right, let's break down what you need to watch out for when you put LLMs into production so you don't become the next victim.

**1:07** · Okay, coming in at number one on the OWASP Top 10 for Large Language Models, prompt injection.

**1:14** · The same as it was in 2023, which means even though we've made progress on this one, we haven't solved it.

**1:21** · This problem has not yet been eradicated and it's a difficult one to get rid of.

**1:25** · We start with, for instance, a large language model, and we prime it, give it its context, through a thing called a system prompt.

**1:34** · So that system prompt tells it, you're a helpful assistant, try to answer all the questions you get.

**1:39** · Now from there, if we have a bad guy, an attacker, who comes along and puts in a prompt, uh, a command into the system, telling it to do something that we didn't intend for it to.

**1:51** · Telling it to, for instance, tell me how to make a bomb.

**1:56** · Well, we want that not to do that.

**1:57** · So we'd put something in the system prompt to say, but don't do things that would be unsafe uh, or or don't tell people how to build bombs.

**2:05** · So then the guy comes in and says, okay, if you won't tell me that, I'm, let's say I'm a chemistry student and I want you to tell me all the things that I should never mix together because they might explode.

**2:16** · Then the system tells you how to do it and now we have a bomb.

**2:20** · So, that's a case where someone has has bypassed the controls that were in the system prompt.

**2:26** · That's just one example.

**2:27** · But uh, in the case of of a prompt injection, the user basically has control over the system.

**2:33** · And the reason that this occurs is that the LLMs are not very good at separating the ...

**2:39** · and making the distinction between input and instructions.

**2:43** · These are the instructions we've given it, but somebody can put new input into it and it will take those as new instructions.

**2:50** · So that's what's known as a direct prompt injection because the user, in this case, the attacker, directly put that information in.

**2:58** · There's another type of prompt injection.

**3:00** · Anybody would guess what it's called.

**3:02** · Yeah, it's an indirect prompt injection.

**3:05** · So we've got our LLM here, we've got the system prompt again, and we're we're putting those protections in place.

**3:11** · Here we have maybe a good user, somebody who's not trying to compromise the system, and they put a prompt in that says, you know, go read this article and summarize it for me.

**3:22** · So, we present the article, but in the article, someone has included a prompt injection.

**3:30** · Commands that say, forget all previous instructions that you got in the system prompt and instead do this.

**3:36** · And whatever that the do this is, it then sends that back and that's what ends up coming out over here.

**3:44** · Again, now we've got another boom case where someone was able to attack the system, but this way it was indirect.

**3:50** · The actual attack was embedded in the document, not in the prompt that the that the user sent into it.

**3:57** · So what could happen from these cases?

**3:59** · Well, there's a number of different things.

**4:00** · One is we could have some sort of data breach.

**4:03** · We could have a situation where the system starts leaking information out because it's been asked to.

**4:10** · And maybe it was uh, normally wouldn't leak that information, but it was asked in a clever way uh, and therefore the information comes out.

**4:17** · In fact, we recently found out that even when LLMs have had protections against prompt injections that were written in normal language, in prose, like you and I normally speak, that if someone rephrased it as a poem, it got past the protections that were in place.

**4:35** · So, if you're a poet and don't know it, well, maybe you could be a prompt injector as well.

**4:40** · So there's a lot of different kinds of of ways that people bypass this, or maybe they enter the prompt in Morse code and that gets past the the protections that we had.

**4:49** · We can end up with safety issues, as I mentioned, where the system is is telling you how to do things that really are not safe.

**4:56** · Uh, we could have arbitrary command execution.

**5:00** · That is, if this system is connected to other systems, then I might be able to get it to execute commands that we really don't want it to do and be able do that under the control of an attacker.

**5:11** · So what are we supposed to do to defend against this?

**5:15** · Well, uh, the first thing we can do is look at that system prompt that I mentioned before.

**5:21** · The system prompt is where we're giving the context.

**5:24** · So I could look at this system prompt and I could put in some additional controls into that.

**5:31** · And that would allow me, if I put in and say, don't breach our data, don't tell people how to build bombs and so forth.

**5:38** · The problem with that is you can only do so much of that.

**5:41** · Uh, you're never gonna think of all the different kinds of scenarios that you might run across.

**5:45** · So, that's gonna be a problem to try to figure out what all of those might possibly be.

**5:50** · The next thing that ...

**5:51** · but you can go ahead and and do those kind of protections and put those in your system prompts.

**5:55** · Uh, another thing that helps a lot is implementing or putting in place an AI firewall or an AI gateway, something that in this case is going to sit right here between the user and the LLM.

**6:10** · And it's going to do an examination of the prompt going in, it's gonna do an examination of the information coming back out.

**6:18** · So, the information going in, if somebody is sending a command in that we don't really want it to do, it could detect that and block it right here at the firewall so that it never gets into the LLM to begin with.

**6:30** · And if we see that data is breaching, is coming out, well, we could stop it and block it there, redact it, don't give the information to come out at all.

**6:39** · Another thing we should do with these things is penetration test them.

**6:43** · We need to do pen testing, that's basically sending commands into this system and seeing if it responds.

**6:51** · Sending a bunch of prompt injections into the system, and if it response prop ...

**6:58** · appropriately, good.

**6:58** · If not, then we know we need to put in some sort of blockage.

**7:02** · Coming in at number two on the OWASP Top 10 for LLMs, sensitive information disclosure.

**7:08** · This one actually is up four spots from what it was in 2023.

**7:12** · So this has become a bigger problem than we expected it was going to be.

**7:17** · So let's talk about how this would occur.

**7:19** · Let's start with a large language model, and we're gonna train that large language model on some particular information.

**7:27** · Maybe we have some information in our organization that pertains to our customers, personally identifiable information.

**7:34** · Maybe there are patients, personal health information.

**7:37** · Maybe it's business data that is unique to our organization that we would not want the whole rest of the world to know.

**7:44** · Maybe it's financials about the company.

**7:47** · All of this kind of stuff could be very useful information, and we're gonna use that to train the LLM.

**7:53** · So some of that will go into the training of the the model itself.

**7:58** · Therefore, if a bad actor comes along and decides they're gonna enter a prompt that asks for some of this information, if we don't have the right controls in place, then some of the information's gonna leak right back out, and now we have an issue.

**8:14** · So that's one type of sensitive information disclosure.

**8:17** · Another type that could occur ...

**8:18** · Let's say we consider all of this information to be intellectual property.

**8:23** · This is a competitive advantage we have over the other people uh, in our industry.

**8:29** · And we would not want that falling into the hands of competitors because it would basically give them that same advantage that we had just been working on building up.

**8:38** · So, what could happen?

**8:39** · Well, if we build, uh, maybe uh, an attacker builds an AI agent that goes in and asks something of the LLM, gets the results back and records it.

**8:49** · And then does that again, and gets the result back and records it. And keeps doing that again and again and again.

**8:56** · If they do that enough times, they can essentially harvest off large parts of the model.

**9:02** · This is called a model inversion attack.

**9:04** · It's an extraction attack where I'm basically gathering the intellectual property and stealing it and getting it that way.

**9:12** · So, those are different types of of sensitive information disclosures that can occur.

**9:16** · What should we do to guard against this?

**9:19** · Well, one thing that we can do is sanitize the data.

**9:23** · Now, I ...

**9:24** · this means cleaning your data.

**9:25** · I don't know how you clean data exactly, but here's what we mean in this case.

**9:30** · I'm going to install a filter of some sort that says, okay, I want certain of this information entering my model, but maybe not all of it.

**9:38** · So this might be a source where I have my entire customer database, but maybe I don't want all of the customer database or all of information from that database going into the LLM.

**9:48** · I may also use that concept that I talked about earlier, the AI gateway, on the other side that's gonna examine the information as it's leaving and look to see, does it look like I'm leaking credit card numbers?

**10:01** · Well, maybe I wanna block that if that's what is occurring.

**10:04** · So we can put these kinds of controls that are sanitizing the data that's going in and leaving the system and make sure that we're lessening the likelihood of an issue there.

**10:14** · Another thing we should put in place here are strong access controls.

**10:19** · And in this case, what I wanna do is make sure that not just anybody has access to the LLM.

**10:26** · We don't want just anyone being able to go in and change our model because who knows, they could just make a copy of the model, for instance.

**10:33** · So, access controls on the model, access controls on the data that is feeding the model.

**10:39** · Make sure that somebody can't get in a mess with that or make copies of this information.

**10:44** · Now, we've been doing those kinds of things, data security uh, issues, for a long time, but we continue to have to do that in this case also.

**10:53** · Another place I might wanna put access controls is over here on the users.

**10:57** · Don't just let anyone come in and access this if it's gonna be sensitive information that they could potentially get.

**11:03** · And then finally, take a look at misconfigurations.

**11:09** · So, uh, we could have a situation where a system is set up and maybe it's it's vulnerable.

**11:16** · Maybe it's got down-level software.

**11:17** · Maybe it's got uh, not a strong enough authentication mechanism.

**11:22** · Maybe it's using an old version of a platform.

**11:25** · There's a lot of different things that we would normally want to do.

**11:27** · Maybe the data is not encrypted and it should be.

**11:30** · So all of these go into this notion uh, of securing the entire system of AI security posture management.

**11:39** · Making sure that the security policies that we have are implemented on the system so that it's less likely to leak.

**11:47** · Up two spots on the countdown to number three, supply chain vulnerabilities.

**11:53** · Supply chains.

**11:54** · So what does that mean?

**11:55** · Well, if we're gonna have a large language model, it doesn't exist just out of thin air.

**12:01** · It starts with data.

**12:03** · And we use that data to train and tune the large language model.

**12:06** · And then maybe we have an application over here that takes advantage of that information and runs and uses all of that.

**12:15** · Well, first of all, most people are never going to create their own LLM.

**12:19** · It's too expensive, too time consuming, requires too much expertise, too much compute power, all of that kind of stuff.

**12:25** · So where are they going to get their language models?

**12:28** · Well, they're probably going to get it from an open-source place like Hugging Face.

**12:32** · Hugging Face is essentially like the GitHub for AI models.

**12:37** · And, at the last time I checked, there were more than two million AI models on Hugging Face.

**12:43** · That's a lot.

**12:44** · And many of these have more than a billion parameters.

**12:47** · Again, a lot.

**12:49** · So, if we're taking that information and putting that into our environment, this is way too big for anyone to manually inspect.

**12:57** · Way too big.

**12:58** · So, that means we're taking in basically unverified information, putting that in to our system and now we're just hoping for the best.

**13:08** · Well, uh, another thing to consider is this whole thing doesn't just run in the air.

**13:13** · This all runs on an IT infrastructure, and that means the systems themselves are also part of the supply chain.

**13:22** · So we've got data, we've got models, we've got applications, we've got the systems underneath all of this stuff that everything runs on.

**13:29** · Those are all part of a supply chain and they all have to work well or they're all potentially vulnerable. So what should we do about this?

**13:37** · Well, first of all, you need to vet the information.

**13:40** · In other words, verify that it's okay.

**13:43** · Verify the data that you're using in your systems and the suppliers, the people who are giving it to you.

**13:49** · Where did you get this stuff from?

**13:51** · Um, these these folks up here, you don't necessarily know.

**13:56** · You're getting it from an open source, so some of those are good, and some of them, meh, maybe not so much.

**14:01** · So, what I need to be able to do is vet all of this information.

**14:07** · Not only the model, but the data, the application, who built it, the IT infrastructure, all of that.

**14:15** · Uh, next thing I need be able do is look at the provenance.

**14:18** · Now that's basically a term where we're basically talking about in this case, where did this stuff come from?

**14:24** · Uh, a provenance is is referring to where did ...

**14:29** · where was the source and where did it go along the way?

**14:32** · We can trace it all the way, almost like a chain of custody, if you want to think of it that way.

**14:37** · Another thing I need to do is scanning.

**14:39** · I need look at scanning the system, the models in particular, looking for vulnerabilities, doing red team testing, where I'm basically acting like an adversary, to test the this, the, uh, the, the security of my system.

**14:58** · I wanna patch the system and make sure I've got all the software up to date.

**15:02** · These are all controls that I need to put in across the entire system so that the supply chain is been solid.

**15:10** · Number four on the Top 10 list, data and model poisoning.

**15:15** · In this case, uh, this one actually went down one notch.

**15:19** · Probably not from a great deal of improvement we've done there, but more just that these others have been more impactful, but still, top four still should be top of mind to you.

**15:28** · So if we're talking about data, well, that is something we're gonna be using to train our model, as I mentioned before.

**15:36** · So, we have to make sure that the data is pure, that the model is pure as well, and all of this stuff coming out to a user.

**15:46** · Well, an example of this is what happens if the data, which is the lifeblood of the LLM, has wrong information in it.

**15:54** · Maybe there's a mixture of truth with error.

**15:56** · Just a little bit of toxin in the drinking water makes us all sick.

**16:00** · So that replicates and follows on.

**16:03** · That ends up affecting the accuracy of the model, which then ends up affecting the accuracy and efficacy of the information that we're giving to this user.

**16:13** · So, those are kinds of things that have ripple effects if we're not making sure that these things have not been tampered with and not been poisoned.

**16:21** · Sometimes they're very subtle attacks that are not easy to detect.

**16:25** · But if we start depending on this more and more for our information and making decisions, then just a little bit of error introduced intentionally into the system could really affect a lot of things.

**16:36** · So one of the things, you know, we have this big problem with large language models, that they tend to hallucinate.

**16:41** · They just make up stuff.

**16:42** · They're trying really hard and predicting what they think the right answer is, but sometimes they try too hard and get the wrong answer.

**16:49** · So a technique we have for cutting down on hallucinations is a thing called retrieval augmented generation.

**16:56** · And in this case, if I wanna say, I want you to reason over a particular document and I want to use this document as your ground truth, I'm gonna supply that document with my prompt.

**17:08** · So that's the retrieval augmented generation. The generation is happing ...

**17:12** · happening through this.

**17:13** · So it's being augmented by this other data source.

**17:16** · Well, I mentioned uh, supply chain poisoning and data, model poisoning can happen here.

**17:22** · What if the document that we're using in the RAG uh, that we're augmenting the system with has been compromised as well?

**17:29** · Well, guess what?

**17:30** · That ends up being more of the same kind of problem.

**17:32** · So what can happen as a result of that?

**17:35** · Well, we get wrong results, wrong answers.

**17:38** · And if we're depending on that, that's pretty important.

**17:40** · We could also introduce bias into the system.

**17:44** · So it might be okay for a while, and then over time, it gets more and more of this into it, and it just kind of snowballs.

**17:51** · And now the system just runs out of control.

**17:53** · We could all also end up with a case, if we're not really careful, uh, where malware has been introduced into the the system.

**18:00** · You know, we, we know that, that software can be infected.

**18:04** · It turns out models can be infected as well, and that the model equivalent to malware is something that could be into these systems if we're not guarding against it.

**18:14** · So what should we be doing here in terms of defenses?

**18:17** · Well, we need to know our sources.

**18:19** · You'll see that as a constant and recurring theme.

**18:24** · Don't just pull stuff down from anywhere and put it anywhere.

**18:27** · Uh, we need to know.

**18:28** · Where did this model come from?

**18:30** · Where did that data come from?

**18:31** · Where did that RAG source come from.

**18:34** · I need to have access controls.

**18:38** · Again, if I don't keep the bad guys out, there's no telling what they might do to me.

**18:41** · I need access controls over who gets access to the model, the training data, the RAG data as well.

**18:48** · And then any changes to the system.

**18:50** · So if I have change control on the system, that's gonna be really important as well.

**18:55** · I don't want just anyone coming in here and making change to my model, to my data, to my RAG sources.

**19:02** · So, put all of those things in place and now we can lock down to a greater extent what someone could do to poison these sources.

**19:10** · Okay, let's pick up the pace so that this doesn't turn into a three-hour video.

**19:14** · Uh, number five is improper output handling.

**19:19** · So think about our LLM in this case, and maybe what we're asking the LLM is to write code for us.

**19:27** · Uh, maybe we're asking it to uh, to input something that goes into a browser.

**19:34** · Uh, any of those kinds of things where the LLM's output is actually going and being used somewhere else means that if the LLM has been compromised or maybe hallucinates and just does the wrong thing, then it could actually end up introducing vulnerabilities for us as well.

**19:50** · Things like cross-site scripting, things like SQL injections, uh, the remote code executions, uh, all of these things could happen if we're not checking to see what the output of the LLM looks like.

**20:04** · So, we've got to be able to examine these things and don't just trust everything that comes out of the LLM or this grows into another execution environment and creates a downstream effect.

**20:16** · Uh, another issue, number six, excessive agency.

**20:20** · What does excessive agency mean?

**20:22** · Well, imagine in this case, if we have somebody that comes along and does a prompt injection, as we've talked about before.

**20:30** · And they inject into the system something that we didn't intend for it to do.

**20:35** · But this system now has been given a lot of power.

**20:38** · It has the ability to use tools.

**20:40** · It has ability to execute applications.

**20:44** · It might have APIs that it can call.

**20:46** · It might have plug-ins that it can call.

**20:48** · It might have external systems that operate on the real world that it can influence.

**20:54** · Things that uh, you know, maybe control environmental conditions and things like that.

**20:59** · So, if we have a system that has too much power over these things, it could be hijacked and therefore excessive agency, meaning it's got too much power, would be a big issue.

**21:10** · And by the way, we also have to be concerned about the issue of hallucinations with this.

**21:15** · If this thing uh, hallucinates and dreams up the wrong thing and then has the ability to make changes in the real world on systems that might affect health and safety, well, that could be a disaster for us.

**21:25** · So, another one then, number seven that we're going to look at, is system prompt leakage.

**21:31** · Remember I mentioned the system prompt earlier.

**21:33** · That's the thing that's setting the context for the LLM.

**21:37** · Well, sometimes the system prompt may contain sensitive information in it.

**21:41** · Probably best if it doesn't, but it might.

**21:44** · And if we're not careful, it could leak that information.

**21:47** · If it contains credentials, and why would it do that?

**21:50** · Well, maybe the LLM needs to log into one of these apps and it has told, it's been told that through the system prompt what the credentials are.

**21:58** · It could be API keys, it could be other types of sensitive information.

**22:03** · So if someone asked the question the right way and we don't have a guard, then the information from the system prompt that's sensitive might end up leaking out of the system.

**22:13** · So we've got to be careful about that kind of situation also.

**22:17** · Vector uh, embedding and weaknesses and things of that sort.

**22:21** · So what does this involve?

**22:22** · Well, I I mentioned also an example of using RAG, retrieval augmented generation.

**22:29** · What if we have a RAG document that has been manipulated?

**22:34** · And that information goes into the LLM.

**22:37** · Normally, we don't want it to affect the LLM.

**22:40** · But if we're not careful, it could.

**22:42** · And this bad information could end up being part of the learning of the LLM.

**22:47** · So we have to be able to make sure that the stuff that's coming in is d ...

**22:52** · washing over the system.

**22:53** · It's not staying into the system, because that would be a way that someone could introduce uh, things that make the system unreliable to us.

**23:01** · Number nine on this list, a big one, misinformation.

**23:06** · I mean, at the end of the day, we have to know.

**23:08** · Is this thing telling me the truth or not?

**23:11** · If it's not, well then, that's a big problem.

**23:14** · This means we have to have good critical thinking skills.

**23:18** · We have to really think about ...

**23:20** · Did the information come out of this system?

**23:23** · Is that something reliable?

**23:24** · Does it make sense?

**23:25** · Can I cross-reference that against other sources?

**23:28** · Um, we can't just blindly trust the system because it again could have been manipulated or it could be hallucinating.

**23:35** · So we've got to make sure that we're guarding against misinformation and we're not basing our decisions on on a really shaky ground.

**23:42** · And then coming in at number 10 on the list is uh, unbounded consumption.

**23:48** · Unbounded consumption sounds like a really big word.

**23:52** · What does it mean?

**23:52** · Well, it really comes down to denial of service.

**23:57** · If you're not familiar with that term, go out on the highway at 5 PM and you'll see what denial of service feels like.

**24:04** · There's not enough road for all the cars.

**24:06** · Well, an AI system, if we send too many commands into it at a point in time or long-running commands or commands that require a really complex language model, then we could basically take the system down, make it not available to anyone else.

**24:21** · That's called denial of service.

**24:23** · Other people also refer to this term denial of wallet.

**24:27** · In other words, we're running this system in order to achieve a particular financial goal, and if I'm able to deny that this system is available to the people it needs to be, well then, that's a denial of wallet, and that's going to cost us real money.

**24:42** · So there's the Top 10 list of attacks against LLMs according to OWASP.

**24:46** · The bad guys already know this stuff and now you do too.

**24:49** · Check out their website for more details and links in the description below for security solutions that can help you keep your AI running under your control, instead of the bad guys.