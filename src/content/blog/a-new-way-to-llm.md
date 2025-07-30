---
title: 'A new way to LLM'
description: 'A solution for easier access to more models'
pubDate: 'Jul 30 2025'
duration: '5 minute read'
location: 'Trondheim'
tags: ['software engineering', 'ai']
---

The recent controversy surrounding AI pricing models and usage limits for both Cursor and Anthropic's Claude inspired me to think about the way I want to interact with these services. As a consumer, navigating the landscape of what's on offer is a nightmare.

For the average person, one subscription is enough. They will subscribe to a single service which is more than likely to be whatever platform has momentum (or the better marketing team). 9 times out of 10 this will be ChatGPT. This is the simple life. OpenAI has made ChatGPT ubiquitous. It's available on the web, on your desktop, and on your phone. One monthly payment gives you access to a decent LLM wherever you need it for a reasonable price.

## The problem I want to solve

Things start to break down a little bit once you realise that models tend to excel at different tasks. Generally speaking, ChatGPT is better at creative writing, Gemini is great for multi-modal (image, video, audio) tasks and sports a large context window, and Claude excels at coding tasks.

To make things worse, the title of the 'best model' for a given task seems to rotate on a 4-6 month basis aligned to new model launches from each of the big players. As I write this, ChatGPT is out of the spotlight for most tasks however, the release of GPT5 is imminent and will no doubt reset the ranking in OpenAI's favor.

Assuming you, like me, want to use the best tool for job you're in for a bumpy ride. Simultaneous access to ChatGPT, Gemini, and Claude 'premium' subscriptions is going to cost in the region of $60-$100 per month, assuming you're not in need of unlimited plans. These are monthly subscription fees with limited usage.

Even if you are willing to spend that much per month, you're then faced with the problem of access. ChatGPT is everywhere, Claude (Code) is in the terminal but also has a desktop and web app, Gemini only offers web or terminal access (through Gemini CLI). If you can navigate the need for 6 different apps across your desktop and mobile device, you're still faced with the problem of dispersed conversations.

Another minor gripe I have is that the features available across the range of apps is inconsistent at best. For example, ChatGPT provides support for grouping conversations into projects, with custom instructions per project. Gemini goes not.

---

## Wishlist

I want a better solution, even if I have to put the pieces together myself.

### 1. Fair pricing model

I want to pay for what I use (and not pay for what I don't use).

### 2. Access to the best tool for the job (task)

I want the ability to use ChatGPT to proof-read my blog post drafts, Claude 3.5 Sonnet and Claude 4 Opus for coding, and Perplexity for research.

### 3. Easy access to inexpensive models

I often find myself having rapid, unimportant, and inconsequential conversations with my LLM of choice. Using Perplexity Pro to understand popularity of Python modules feels unnecessory. I want the ability to switch to an inexpensive model for those throwaway conversations.

### 4. Consistent app feature set

I want the ability to group chats by project or topic, to be able to provide custom instructions and tailor the persona/role. And I don't want to fight with 4 different apps and UIs to do this; I want it all in one place.

---

## My solution: The pay-as-you-go model

Note: I'm still experimenting with the cost-effectiness of this approach.

I'll break it down into a few parts:

### OpenRouter

One of my requirements is to be able to quickly switch between the most effective model for the task at hand. I need to use an aggregator to do this. The aggregator I'm using is [OpenRouter](https://openrouter.ai/).

OpenRouter aggregates models and provides access via a single API. It also provides a pay-as-you-go subscription model where you only pay for what you use. Check and check.

### MacMind

[MindMac](https://mindmac.app/) offers a unified interface for interacting with models and organising conversations. Crucially, it integrates with OpenRouter allowing me to quickly switch models for each conversation (even within conversations) in order to the most appropriate model.

### IDE integration

VSCode is my IDE of choice. I've spent too long customising it to consider switching now. Whilst a terinal client would work, I've also explored integrated extensions that work with OpenRouter. The two winners right now are [Cline](https://cline.bot/) and [Kilo Code](https://kilocode.ai/). I'm not married to either of these yet and this is a vibrant space with challengers appearing all the time.

### The fallback

This approach ticks most of the boxes for me but there are a couple of downsides: 1. Cost effectiveness is a an open question: I need to experiment with my usage to determine whether this approach is going to be cost-effective in the long-run. 2. App availability: MacMind does not offer a mobile app. This means I will still need to manage my conversations in two separate places (desktop and mobile). It's not ideal but also not a deal breaker.

If cost turns out to be prohibitive there are alternatives such as [T3.Chat](https://t3.chat/) that I will explore. This won't tick all of the boxes on my wishlist but it will be a reasonable option.
