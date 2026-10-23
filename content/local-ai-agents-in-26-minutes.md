---
schemaId: urn:gala:schema:content-frontmatter:2.0.0
schemaVersion: 2.0.0
id: 01a168c6-7ed2-7263-825e-0719190c2eea
kind: article
title: Local AI Agents In 26 Minutes
description: I spent months building with local AI agents like OpenClaw and Claude Cowork. Here is what they are, how to design your own, how to keep them safe, and how I run mine.
language: en-US
authors:
- 01a168cb-98ff-7573-a526-4a7e80f05b5b
tags:
- local-ai-agents
- openclaw
- claude-cowork
- ai-agents
- ai-safety
status: published
createdAt: '2026-04-15T12:00:00.000Z'
publishedAt: '2026-04-15T12:00:00.000Z'
slug: local-ai-agents-in-26-minutes
hero:
  path: assets/content-local-ai-agents-in-26-minutes-hero.jpg
  alt: Thumbnail of the video "Local AI Agents In 26 Minutes"
  role: informative
redirects: []
extensions: {}
---
*Adapted from the video [Local AI Agents In 26 Minutes](https://www.youtube.com/watch?v=M-NTwkM3VwM)*

> **TL;DR:** A local AI agent is an AI that takes action and completes tasks on its own while running on your machine. I break one down into where it lives, a communication channel, a brain, memory, tools and skills, a heartbeat for scheduled tasks, and eyes. You can run several as a team. Safety comes first, so isolate the agent, limit its access, and distrust other people's skills. Add one workflow at a time with clear instructions. I demo OpenClaw and the safer no-code Claude Cowork.

I learned all about local AI agents for you, so here is the cliff notes version to save you the months I have spent playing around and building with them, like OpenClaw and NemoClaw. I even have a little 24/7 Claw factory researching and building me software. I also tried no-code, safer options like Anthropic's Claude Cowork.

I waited many moons to make this video because I wanted to be 100% sure this is not just a hype thing. I am now 100% convinced that local AI agents are a new category of AI products, and in the past few months they have transformed my daily workflows.

Here is the plan. First I define what local AI agents are, including the anatomy of one and how to custom design your own. This is where most people fail to get the most out of their agents, because they don't understand how to design them properly. Then I cover some principles and tips, including safety and good engineering. Then I make it concrete with demos of a code version (OpenClaw) and a no-code version (Claude Cowork). Finally I end with some thoughts on how to take advantage of this new category, because this is just the beginning and it represents massive opportunities.

## What a local AI agent is

*[Watch from 1:16](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=76s)*

First and foremost, it is an AI agent, which is an AI that can take actions and complete tasks on its own. AI agents are nothing new; they've been around for over 2 years now. What makes them more exciting and powerful these days is that they are also local, meaning the agent lives and runs on your personal machine.

A local AI agent can, for example, send you a very personalized morning brief of your calendars, emails, priority stock portfolio, notes and the news you're interested in. Mine are also constantly researching ways for me to improve my business and then autonomously building software to implement them. They have built me a personal finance tracker, accounting software, a dashboard that tracks our boot camp students and their progress, and some trading bots. Not financial advice, it's just a personal hobby. You can also communicate with them and monitor what they're doing from your phone, so you don't have to be sitting at your computer.

## Anatomy: where your agent lives

*[Watch from 2:25](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=145s)*

To show you the components, picture a little guy who is your local AI agent. His name is Inky, and we're going to build and customize him.

The first thing to decide is where he lives. He's local, so he lives on your machine, but there are many kinds of machine: your personal laptop, an old laptop, a Mac mini or Mac Studio, a PC, or a VPS (virtual private server), which is like renting somebody else's computer in the cloud. In my opinion, three factors decide where to run your agent:

1. **Whether you want it running 24/7.** Then it needs something that stays on, so a laptop you carry around wouldn't work.
2. **Your machine specs.** Chip, CPU and GPU, but most importantly RAM. If you want your agent powered by really big open-source models, you need a machine that can handle running them, and your everyday computer probably wouldn't cut it.
3. **Privacy and security.** How paranoid are you about the agent having access to your things? There have been stories of people who installed a local agent on their personal laptop without the right guardrails, and it had access to everything and potentially deleted their emails.

If you're paranoid like I am, you probably want a machine dedicated to your agent that doesn't have access to the stuff you don't want it to touch. When I first started playing with OpenClaw, I used an old laptop that I completely wiped, left on 24/7 and dedicated entirely to my agent. Because that old MacBook Pro only has 16 gigs of RAM, I mostly used Claude's Sonnet and Opus models instead of big open-source models. After building more seriously, I also started using a Mac mini, a dedicated machine with better hardware, so I can run bigger open-source models too. I have one on an M2 as well, and I just ordered a Mac Studio because I'm really into local AI agents.

There are a lot of other options. I put some hardware and machine specs on screen, along with a prompt in the description that you can paste into your favorite AI chatbot, like Claude or ChatGPT, to help you figure out which hosting option suits you best. I know hosting and hardware are a really big blocker for a lot of people.

## A mouth and ears: the communication channel

*[Watch from 5:14](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=314s)*

Next, Inky gets a mouth and ears, a communication channel, so you can talk to him and he can talk back. This is also what lets you talk to him remotely from your phone. There are many third-party options you probably already use, like Telegram, Discord, WhatsApp, iMessage, Slack and Dispatch. The easiest way to start is single-channel messaging, and Telegram is usually what people pick, or Dispatch if you're using Claude Cowork. As you get more advanced and have multiple things going on, you'll probably want to graduate to something like Discord, which has multiple channels so you can stay more organized.

## A brain: the model

*[Watch from 6:03](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=363s)*

The brain is the large language model that powers the agent. You can choose Claude models (Opus and Sonnet), OpenAI models, or open-source models like Qwen, Kimi, MiniMax and DeepSeek. Different models have different tradeoffs in capabilities, size, speed, cost and privacy. I made an entire video that goes through the different types of models out there. The short version: the most popular options for local AI agents are Claude Opus or Claude Sonnet, and on the open-source side Qwen and Kimi are the most popular. I put on screen the different types of models and what they're best for, to help you choose.

## Memory: just text files

*[Watch from 6:47](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=407s)*

You also have to give the agent memory so it knows things about you and remembers what it's doing. This is simpler than you'd expect: memory is literally a bunch of text files. You document everything you want Inky to know: who he is, his personality type, what he's supposed to be doing, his workflows and data, and information about you, such as your workflows, personality type, what you care about, your demographic and your job. That is what makes him personalized to you. As he completes a task, say researching stocks, he writes down what he's doing, so when you talk about those stocks later he knows what you mean.

Most local agent software, like OpenClaw and Cowork, already has a memory system built in. Power users often boost it to be more robust and organized with something like Obsidian, which I show in the demo.

## Tentacles: skills and tools

*[Watch from 7:45](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=465s)*

Tentacles represent skills and tools. Inky already comes with some pre-built ones, so he can search your files, execute code and so on. Depending on what you want him to do, you give him more tools and skill sets, such as web search, access to your email, screenshots, text-to-speech and image generation.

## A heartbeat: scheduled tasks

*[Watch from 8:14](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=494s)*

A heartbeat lets you schedule tasks so the agent runs without you asking. For example, every 30 minutes he scans for new email, or every month he schedules a doctor's visit. A schedule can be time-based, called a cron job: every morning at 7:00 a.m. he sends me a morning briefing. It can also be event-based: every time a file gets added to my accounting folder, he runs my accounting workflow and puts it into the books. These are game-changers, and I put some of my favorites on screen.

## Eyes: seeing and using your computer

*[Watch from 8:47](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=527s)*

The last body part is eyes. They let your agent see what is happening on your computer and interact with it like a human would. It can check what's in your folders and, in some cases, see what's on your screen, move your mouse and do things on your screen for you. With that, Inky is built, and I put a diagram of the anatomy of a local AI agent on screen. Take a screenshot.

## Teams of agents

*[Watch from 9:32](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=572s)*

There's no reason to have only one Inky. You can have several agents doing multiple tasks at the same time, or put them into teams where each has a specific function and together they produce something greater than the sum of its parts. I have a research team looking into stocks I might be interested in buying, and a software team researching, making product decisions and building software for my company. One could be doing research, one managing your calendar, one writing a marketing campaign.

There are specific principles for designing these multi-agent systems, which I don't go into here because there's a lot going on there. I made a separate video covering multi-agent system design that you can check out.

## Sponsor: Superhuman Go

*[Watch from 10:23](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=623s)*

As a YouTuber and entrepreneur, my workday is all over the place. One hour I'm deep in the codebase, the next I'm writing a video script, and then a LinkedIn post. The context switching and the cold start problem are brutal, which is why I use Superhuman Go, from the makers of Grammarly. It's an AI partner that works inside the apps and websites you already use, proactively making suggestions without you asking. My favorite feature is reader reactions, which predicts how your audience will respond before they see it, flags where they might get confused and what questions they'll ask, and suggests revisions. I use it on everything from scripts to client emails. Thank you, Grammarly, for sponsoring this portion of the video.

## Principle one: safety

*[Watch from 11:47](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=707s)*

Before the demos, I want to cover two principles that are very important as you build with local agents. The first is safety. It's the primary concern, because you're giving a very intelligent agent access to your computer and hoping it doesn't go bananas. There have been stories of local agents deleting people's emails, or having viruses in them because of skills being shared. Here is how I think about it:

- **Isolate the agent.** I don't run mine on my primary machine, which has all my data. I only run them on dedicated machines with no sensitive information.
- **Be careful about access.** My agent has access to some of my emails because I want it screening them, but not my personal emails, which have very sensitive information. I create new emails for that.
- **Don't trust other people's workflows.** People write workflows that document a process, like writing a marketing campaign, and they can be really useful, but malicious things can be put into them that make your agent go bananas. I generally don't use other people's skills unless they're from very trusted developers. If I find a really good skill somebody else made, I give it to Claude, tell it to scan the skill and rewrite it itself, and then give that to my agent.
- **Be as paranoid as possible.** OpenClaw has dedicated security checks it tells you to run, so I use my agent's heartbeat to run a security audit every hour, or at minimum every day.

If you use something like Claude Cowork, many of these security functions are already pre-baked in, so you don't need to worry as much.

## Principle two: good engineering

*[Watch from 13:46](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=826s)*

The second principle is good engineering: always give clear instructions for what you want your agent to do or build, and add only one feature or workflow at a time so it's easier to track and monitor. Don't say, "Hey, Inky, build me five things at the same time." If something goes wrong you won't know what's going on. Very chaotic.

## OpenClaw demo

*[Watch from 14:15](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=855s)*

Now the demos, starting with OpenClaw, to show how I implement all these components. This is the agent office, where you can visually see all the agents, what they're doing and how they interact. It's a custom tool I use called mission control, and it lets me monitor what the agents are doing.

Here is the team. There's me, the founder, CEO and the human. There's Inky, the chief of staff, who uses the Claude Sonnet 4.6 model as the central brain. There's an autonomous content pipeline made of Blinky, Pinky and Dinky, all using Sonnet models. There's Linky, the builder, so any time we need to build software or do things with code, it's routed to Linky. Linky has two models: Claude Opus 4.6 for planning, architecture and more intense coding, and Qwen Coder 2.5, an open-source model that lives on the computer and is completely free. Linky routes more mechanical coding tasks to Qwen Coder to optimize costs, because Opus is really expensive to run all the time. And there's Winky, a system monitor that runs twice a day to check that all systems are up and there are no security issues, using the Ministral 3B model, a very small local model that is also free.

All of these agents and models run on a secondary laptop, a MacBook Pro with 16 gigs of RAM. I have many OpenClaw setups, but this one is the home for this setup.

**The content pipeline.** This runs on Discord, my communication channel, with different channels for what the agents are doing, current projects and alerts. I get a morning brief with the top stories on things I'm interested in, which is basically AI stuff. It updates my topic watchlist, which is how I track topics to decide when to make a video about them, and gives me video ideas, which it puts into the content ideas channel. If I like one, I go to mission control and open the content tab. Say I like "AI agent memory explained." I click it, and then I can approve or pass. It routes to the YouTube long-form channel and gives me a working title, topics, my ideas and some bullet points, and then I can get a video outline, such as "AI agent memory explained in 28 minutes." I still have to flesh it out myself and cross-reference and check a bunch of things, and it takes me a very long time to make a video, but it's a really good starting point.

**Tools and skills.** I can ask which tools the daily digest to content pipeline uses, and it tells me. Another way to get tools and skills is ClawHub, where people share skills you can download. I don't download from there unless it's literally by the founder, because there was a whole security risk and scam situation through it previously. I'm just being paranoid. What you can do instead is click on a skill you like, give it to Inky and tell him to build the skill himself without downloading it.

**Tasks and nightly builds.** There's a board of all the tasks that everyone is doing, including me, plus an activity log, the scheduled jobs and my current projects. I also asked Inky to build something delightful for one of my current projects every night, so when I wake up there's something new. Last night he built a little quiz, an MVP for a micro SaaS called "what AI skill should you learn next," that gives you a personalized AI learning roadmap. Am I going to use it? I don't know, but it's really fun waking up to something that got done autonomously, and sometimes I like the idea and build on top of it.

**Memory.** I get Inky to aggressively document everything he does. There are docs for everything he builds, daily logs of what he does each day, and long-term memory in memory.md. Since Inky has eyes, one of his daily tasks is to see all the changes that have been made and document everything so nothing is left undocumented. I also have this in Obsidian so I can read it there. I'll probably develop it into a more robust memory system that also works as a second brain for me. There's a lot more I could say, so let me know if you want a more dedicated OpenClaw video.

## Claude Cowork demo

*[Watch from 20:03](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=1203s)*

I also want to show you a safer no-code option, Claude Cowork. It's Anthropic's take on local AI agents. It's a lot safer and a lot easier to use, so I really recommend it for people who are not comfortable with code at all or are just starting out. The downside is that you get locked into Anthropic's system and there are fewer ways to customize things. Still, I think it's a really good option if you're just starting out.

Claude Desktop is the central hub for Cowork. The models available are all Anthropic models, and the interface is very similar to a regular chatbot. You can also chat with it on mobile through Dispatch. Cowork lives on your computer and corresponds to a folder on it. Here I'm using my personal laptop, because I trust Claude Cowork more than OpenClaw not to reveal all my passwords and destroy my life. It has memory files, claw.md and memory.md, which I like to look at through Obsidian. I made separate folders for different projects, like content studio, portfolio, lonely octopus and personal.

In my portfolio folder, which is my investment portfolio, I can ask questions like what my top performer is. It tells me my best performing winner is on the Hong Kong Stock Exchange. I can also ask for my biggest loser, and my China AI names are all underwater. Got to stay honest.

You also have access to Claude Code on the same hub. One thing it built me is an investments dashboard that updates by itself and shows my positions, research on segments I care about and a watchlist. You also have skills and connectors. You can pull from Google Drive or Google Calendar and set up automated workflows. Plugins are combinations of skills and connectors for a specific purpose: a finance plugin has skills like audits and close management, and connectors for apps like Google Calendar, Gmail and Microsoft 365.

Scheduled tasks are the heart of your agent. Mine include, every day at 8:00 p.m., a daily investment deep dive, a portfolio daily briefing and a daily macro briefing, all reflected in the investments dashboard I built.

Finally, Claude Cowork's eyes, computer use, arguably one of its most visually cool features, which I do through mobile. Say I'm out and about, only on my phone, and I need a file on my local computer. I can ask it to send over the Discord PNG file, allow it permissions, and it sends it to me. That didn't really use the computer, so I tried again and asked it to take a screenshot. It literally uses my computer, searches, opens the file and sends me a screenshot. So crazy.

There's so much more you can do with Cowork. I personally use Claude Cowork and OpenClaw at the same time, plus some other agents, many different local AI agents for different use cases.

## Predictions and how to take advantage

*[Watch from 24:18](https://www.youtube.com/watch?v=M-NTwkM3VwM&t=1458s)*

My final section is predictions about the development of local AI agents and what you should learn to take advantage of this new category of AI product, because it represents massive opportunities. It's not just me saying this. In a clip from Jensen Huang of Nvidia, he says the question for every technology company CEO is:

> What's your Open Claw strategy?

He's basically saying companies all need an OpenClaw strategy now, a personal local AI agent strategy. As he explains, there are many opportunities for your personal workflows and your business workflows.

My recommendation, if you want to take advantage of the rise of local AI agents, is to learn to build your own AI agents too. Play around with OpenClaw and set up different local agents, but if you also understand how to build your own agents, that is much more powerful, especially in combination with learning AI coding. If you know how to use local agents, build your own agents and set up systems for them, and know AI coding so you can augment them, that combination is so overpowered. The world is your oyster.

Thank you so much for watching until the end, and good luck and have fun.

*[Watch the full video on YouTube](https://www.youtube.com/watch?v=M-NTwkM3VwM)*
