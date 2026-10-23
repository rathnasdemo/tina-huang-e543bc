---
schemaId: urn:gala:schema:content-frontmatter:2.0.0
schemaVersion: 2.0.0
id: 01a168c6-7e25-7eb7-afc2-a7081dd916a0
kind: article
title: Every Size Local AI In 24 Minutes
description: I ran local AI on every class of hardware I own, from a tiny chip to a rented GPU server, and show what each can run, what you can build, and a formula for what fits on your own machine.
language: en-US
authors:
- 01a168cb-98ff-7573-a526-4a7e80f05b5b
tags:
- local-ai
- hardware
- raspberry-pi
- open-source-models
- gpus
status: published
createdAt: '2026-09-28T12:00:00.000Z'
publishedAt: '2026-09-28T12:00:00.000Z'
slug: every-size-local-ai-in-24-minutes
hero:
  path: assets/content-every-size-local-ai-in-24-minutes-hero.jpg
  alt: Thumbnail of the video "Every Size Local AI In 24 Minutes"
  role: informative
redirects: []
extensions: {}
---
*Adapted from the video [Every Size Local AI In 24 Minutes](https://www.youtube.com/watch?v=rPGJhrunbxo)*

> **TL;DR:** I ran local AI on every class of hardware I have, from bare chips to rented GPU servers. Chips can only run tiny story models. Mini computers like a Raspberry Pi or an iPhone run small chat, speech and vision models, and the difference between them comes down to memory bandwidth and GPUs, not RAM. Laptops run almost every category. Home servers run bigger models faster, and discrete GPUs fix slow image, music and video generation. A simple formula tells you which model size fits your RAM.

Today we're running every size of AI locally on the hardware I have here, to see what we can do with it. I'm hoping to give you some ideas for cool things you can build with local AI, too.

I'm grouping my hardware into different memory classes: chips, mini computers, personal computers, home servers and GPUs. For each one I'll show what it can run and what you could build with it, and along the way I'll give you a quick lesson on AI hardware and a formula for working out what model fits on your own machine.

## Chips: where almost nothing fits

*[Watch from 0:16](https://www.youtube.com/watch?v=rPGJhrunbxo&t=16s)*

Chips are literally just computer chips. They have no operating system, no file system and no separate memory stick, so everything is built into the board. When we put an AI model on one, we're not even installing it. We just stick it on there, and if it fits, it sits and we can run it, or not.

The smallest one I have is an Arduino R4 Uno. It has only 32 kilobytes of RAM, which is big enough to fit, drumroll please, no models. Nothing fits on here. I got it as part of a set because I'm trying to learn hardware. That doesn't mean I can't use it with local AI, though: it has Wi-Fi, so I can connect it to some of my bigger devices.

Something that can fit a model is the ESP32-S3. It's tiny, it has 8 megabytes of RAM, and I got mine for around $20. That one comes with a screen. Without the screen you're looking at two to five dollars, so cheap. It runs two Tiny Stories models, the Tiny Stories 260K model and the Tiny Stories 3M model, both very comfortably, and as the name suggests they let you run tiny stories.

Getting a model running is just the start. You can add modules to make it much cooler. For example, you can turn it into a little game called scrambled versus not scrambled, which might be useful if you're learning English grammar. You can also attach LED lights that represent the mood of the story being produced.

These models can only do the very basics of predicting the next word in order to form a coherent story, which is still very impressive given how small they are. But they can't hold a conversation like a chat, and they can't run any multimodal models for audio, music, video or images. For that we need the next class of devices.

## Mini computers: the Raspberry Pi 5

*[Watch from 3:00](https://www.youtube.com/watch?v=rPGJhrunbxo&t=180s)*

My mini computers are a Raspberry Pi 5 and my personal iPhone 16. These are proper computing devices. They run an operating system (Linux on the Pi, iOS on the iPhone), they can manage memory and file systems, and they can run multiple programs. So you can have multiple models, as long as they fit.

What's really interesting is that both have 8 gigs of RAM, yet they can't run the same kinds of models. I'll explain why in a bit, but first, what they can do.

The Pi looks very small but it is a full-blown mini computer. I can have full conversations with it by chaining together three different AI models on this tiny device:

1. **Whisper**, a speech-to-text model, listens.
2. **Qwen 3 1.7B**, a large language model, interprets what I said and comes up with a response.
3. **Piper**, a tiny text-to-speech model, answers out loud on the speakers.

I can also connect a webcam that grabs a frame, have a tiny visual language model called Moondream describe the picture, and have Piper say out loud what it sees.

So you can run micro to small large language models very easily on the Raspberry Pi, as well as tiny visual language models, tiny text-to-speech models and small but decent speech-to-text models. It struggles with mid-size large language models, though if you really want to, you kind of can. It can barely run small code-tier models. And it really can't do image, music or video generation. Not because a small image generation model wouldn't fit, because it would, but because the Pi has no GPU, so it's painfully slow.

It makes up for that because you can build with it. You can add so many accessories and sensors to a Raspberry Pi. In fact, I believe the Hugging Face robots run off a Raspberry Pi as well.

## The iPhone 16

*[Watch from 6:03](https://www.youtube.com/watch?v=rPGJhrunbxo&t=363s)*

The iPhone 16 also has 8 gigs of RAM, but it's very different. Because it runs iOS, Apple limits each app to around 4 or 5 gigs of RAM. So even though it technically has 8 gigs, you can't run the mid-size models from 7 to 14 B that the Pi can, because Apple doesn't let you. You also can't just put whatever you wish onto an iPhone. You go through Apple's official system, which means installing an app that lets you download and run local models.

- **Gemma 4.** You download the AI Edge Gallery from Google, then download the models onto your phone.
- **Visual language models.** The phone can run the small class, meaning it can analyze images with models in the 1 to 4 B range very comfortably, since it's only 1.5 gigs.
- **Image generation.** You download an app called Draw Things and can run small image generation models at around the 1 B range with no problem. Stable Diffusion 1.5, for example, is 2 gigs, and runs very comfortably.
- **Speech and text-to-speech.** It runs medium and large speech-to-text models like Whisper Large very comfortably, and all text-to-speech models too.
- **Detection models.** People don't talk about these very much for some reason, but they're very cool. You download an app called Ultralytics and run the YOLO 11 N model. It does object recognition to understand a scene, and it's the underlying technology behind everything from facial recognition on your devices to self-driving cars, because you have to be able to recognize different objects as you drive. They're really very useful.

## A small lesson on AI hardware

*[Watch from 7:52](https://www.youtube.com/watch?v=rPGJhrunbxo&t=472s)*

Think of any device as a restaurant kitchen. Downstairs there's a walk-in freezer and storage space, where we keep all the ingredients. Then there's the prep counter, where we load up the ingredients we need right now for the dish we want to make.

Then there are the people who work in the kitchen. There's the head chef, who is very advanced and can make any sort of dish, but there's just one of them. There's a brigade of line cooks, who are less experienced and less versatile, but there are a lot of them. And there are specialized machines bolted to the walls, like an onion machine that only chops onions, or a noodle slicing machine. They can only do one thing, but they do it really well and really fast and use almost no electricity. Between the prep counter and the chefs, cooks and machines is a conveyor belt passageway that carries ingredients from the counter to be processed into, hopefully, a meal.

To prepare a salad, we get the salad stuff from the freezer, put it on the prep counter, and send it down the conveyor belt. The head chef gives out orders: the line cooks chop up the vegetables, the onion machine chops the onions, and he himself mixes the sauce, because that's the tricky part. A few minutes later, voila, a salad.

That's a great analogy for how AI models work on our devices. This time what we're cooking is a model:

- **Storage** is the freezer. We grab our model from there.
- **RAM** is the prep counter, where the model gets placed.
- **The memory bus** is the conveyor belt.
- **The CPU** is the head chef, who directs everything.
- **The GPU** is the line cooks, who cook up parts of the model.
- **The NPU** is the specialized bolted-on machines.

After all that cooking, the model can produce something, like answering "Hi, how are you?" with "Hello, I am good. How are you?" Every time we work with a model, we go through this entire process of cooking.

## Why the Pi and the iPhone differ

*[Watch from 10:10](https://www.youtube.com/watch?v=rPGJhrunbxo&t=610s)*

Now back to the question: why does the Raspberry Pi have 8 gigs of RAM and the iPhone have 8 gigs of RAM, yet models run much faster on the iPhone, which can also do image generation while the Pi cannot?

The two devices have the same capacity but not the same bandwidth, which is the conveyor belt between the prep counter and the chefs. For most large language models, the bottleneck is how quickly you can deliver the model from RAM to the chefs, cooks and machines. On the Pi the memory bus is quite narrow and slow, so it physically takes longer. On top of that, the Pi only has a CPU, with no GPUs or NPUs. It's like a single very capable head chef with a single pair of hands doing everything. The iPhone has CPUs, GPUs and NPUs, which is why it processes things so much faster.

The Pi can't do image generation because of the lack of GPUs. Image, video and music generation are really processing heavy, so if you only have CPUs, no matter how hard they work, it's not enough. You need some GPUs, like the iPhone has.

What I've said about AI hardware is much more simplified than it really is. There are concepts like VRAM and unified memory, and so much more, which I won't go into in this video. But this is the general introduction that will help you figure out what kinds of models can run on what kinds of devices.

## Sponsor: Crusoe Intelligence Foundry

*[Watch from 12:24](https://www.youtube.com/watch?v=rPGJhrunbxo&t=744s)*

I've been very into tinkering and running open-source models, and the next obvious step is tinkering with and customizing the open-source models themselves. For that, Crusoe Intelligence Foundry has been amazing. It gives you two main things: serverless inference to run open models without touching any of the underlying GPU infrastructure, and serverless fine-tuning to customize open models on your own data without owning or managing any hardware. You can fine-tune a model, deploy it in one click and start calling it with an API in minutes. The first time I did this I almost shed a tear. There's no cluster supervision or crazy long setup, and I can't even explain how painful this used to be. When you sign up you get $5 of free credit, and the link is in the description. Thank you, Crusoe, for sponsoring this portion of the video.

## Personal computers: my MacBook Pro

*[Watch from 13:09](https://www.youtube.com/watch?v=rPGJhrunbxo&t=789s)*

Next up are personal computers, such as the MacBook Pro I'm using right now. Mine has 32 gigs, but this category also includes my older MacBook Air, and Windows and Linux laptops too.

I got a MacBook Pro with 32 gigs of RAM because it lets me run pretty much any category of AI model: large language models, coding models, visual language models for visual analysis, image generation, video generation, text-to-speech, speech-to-text, audio generation, voice cloning and music generation. All of it locally.

I can also use these models in different ways with different software. With my Hermes agent, which I use to run many aspects of my life and work, I can run pretty much any mid-size to large-size local model, like Qwen 3 14B, 16B and 32B, some of my go-tos in the Qwen family. I can run Qwen 3 Coder 30B locally with an open-source coding harness like Open Code, and it works pretty well. My favorite for image generation is Flux Dev.

## A formula for what fits on your machine

*[Watch from 14:41](https://www.youtube.com/watch?v=rPGJhrunbxo&t=881s)*

I know what you're thinking: "But Tina, I don't have a 32 gig MacBook Pro." Understandable, it's really expensive. I only got this machine because it's literally my job to test out models and things. Don't worry, I've also put on screen the models you can run with 8 gigs and 16 gigs of RAM, which are the general RAM sizes of the laptops most people have. And if yours is smaller, bigger or somewhere in the middle, here's a formula for roughly calculating the size of model you can run:

1. Take the total amount of RAM your machine says it has.
2. Subtract 25% of it, because that's used up by other stuff. The rest is your usable RAM.
3. Divide that by 0.6. The result is the number of parameters your model can have.

My MacBook Pro says it has 32 gigs. Subtract 25% and I have 24 gigs of usable RAM. 24 divided by 0.6 gives 40, so my MacBook Pro can fit a model of up to 40 billion parameters. It's a very rough way of figuring it out. You can also just ask your favorite AI chatbot what models you can fit.

## Home servers: Mac Studio and AMD Ryzen AI Halo

*[Watch from 15:54](https://www.youtube.com/watch?v=rPGJhrunbxo&t=954s)*

The two home servers I have to demo are the Mac Studio and the AMD Ryzen AI Halo. Plenty of other machines fit this class. The cheapest entry-level one would be a Mac Mini, although those are really hard to get these days. I only got the Mac Studio because I couldn't get a Mac Mini.

There are two reasons to get something like this. First, it's a dedicated always-on machine. Your laptop you have to carry around and close, and when you close it your model stops working. Home servers are designed to be always-on, so you can run your AI models 24/7. Second, they generally have more capacity and bandwidth, so they run bigger models and do it faster.

My Mac Studio has 64 gigs of RAM. Pop quiz: how much of that is actually usable, and what is the largest model, in billions of parameters, that can fit? Put your answer in the comments.

The Mac Studio is where I like to run the local models for my local AI agents, and it lets other devices use them too. Remember the Arduino Uno R4 that couldn't run anything by itself? I connect it to the Mac Studio, and it uses the Qwen 3.6 35B model running there to display encouraging, happy messages.

At this tier and above, it's not about unlocking new categories of AI models. It's about running bigger models, getting higher quality responses, and getting them faster. On the Mac Studio I can run large-tier language models between 27 and 32 billion parameters, as well as large code models, large image models and large music generation models. For video generation I can now run a mid-tier model, but it's still really slow.

The AMD Halo has 128 GB of advertised RAM, around 96 GB of it usable. That lets it comfortably run extra-large models in the 70B range and frontier models in the 100 to 250B range. Llama 3.3 70B runs fine, GPT-OSS 120B runs fine, and so does an extra-large coding model like DeepSeek Coder V2.

What I find most useful about a machine like this is that it can have a lot of different models loaded and working simultaneously, because of that massive amount of memory. I could be using a coding agent and large language models while doing image and video generation, all at the same time.

There's a caveat, though. Even though it has very large capacity, it has pretty small bandwidth, which means it's slow, especially for image, video and music generation. It can do them; it's just really, really slow. Which brings me to the final category.

## GPUs: a boost for the line cooks

*[Watch from 19:42](https://www.youtube.com/watch?v=rPGJhrunbxo&t=1182s)*

Back to the kitchen: a GPU is a brigade of line cooks. Because there are so many of them, they work and compute very fast. That matters most for music, image and video generation, which need a lot of processing power.

The bad news is that all the devices I went through earlier do have GPUs, which is why they can do music, image and video generation, but they do it really slowly because they're not specialized for it. The good news is that you can get really fast, really good image, music and video generation with discrete GPUs. A GPU isn't just line cooks, it's a bundle. When you get another GPU, you get cooks who come with their own private prep counter and a very wide conveyor belt, the memory path. They get the ingredients really fast, so it's a boost for the line cooks and you can cook your models really quickly.

Unfortunately, you can't add GPUs to any of the devices I covered earlier; they're not built that way. A gaming PC, though, has a GPU, and you can add more. I don't have a gaming PC and I'm not about to buy one, because they're expensive.

## Renting an RTX 4090

*[Watch from 21:24](https://www.youtube.com/watch?v=rPGJhrunbxo&t=1284s)*

So I'm going to cheat a little and rent an RTX 4090, a pretty high-end GPU that you might have in a high-end gaming setup. It's costing me by the hour, so I did this quickly. I ran an image generation model and a video generation model, and both were really, really quick.

The downside is that it only has 24 gigs of memory. You can think of it as the opposite of the AMD device. The AMD device has a lot of memory, a very big capacity, but low bandwidth. The RTX 4090 has a smaller capacity, only 24 gigs, but much larger bandwidth. So you can generate a lot of these things and run these models, but you can't fit very large models on it.

## The final boss: 8X H100

*[Watch from 22:25](https://www.youtube.com/watch?v=rPGJhrunbxo&t=1345s)*

That leads me to the final boss, the 8X H100 GPU. This is top tier: 640 gigs of RAM, massive capacity and massive bandwidth. I had to move fast on this one because it was costing me so much money every minute, but for you guys, it's worth it.

On here we can run ultra-large-tier language models up to 700 billion parameters plus, ultra-large coding models of 480 billion parameters plus, visual language processing, and all types of multimodal generation. I checked out video generation with a MiniMax model, and it can generate minutes of video, so quickly.

This is pretty much what you can run unless you're a literal model development company or have a lot of money, and it's really comparable at this point to the frontier models you pay for through cloud APIs. Everything up to this GPU forces you to choose between capacity and bandwidth. The AMD Halo is big capacity and low bandwidth, and the RTX 4090 is small capacity and large bandwidth. Here you get both, very big capacity and very big bandwidth. This is the aspirational class.

Thank you so much for watching until the end. I hope this was insightful, interesting and helpful, and that it has inspired you to want to build things with local AI as well.

*[Watch the full video on YouTube](https://www.youtube.com/watch?v=rPGJhrunbxo)*
