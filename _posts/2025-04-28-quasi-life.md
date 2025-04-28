---
layout: post
title:  "AI Quasi-Life"
date:   2025-04-28 11:08:00 -0700
categories: research
---

# AI Quasi-life

Several people have posted predictions of the future lately, see [Scott Daniel](https://www.dwarkesh.com/p/scott-daniel) and [Ege Tamay](https://www.dwarkesh.com/p/ege-tamay). I want to offer my own prediction:

## April 2025

Today is April 2025, AIs are useful for a variety of tasks that you would typically do at a computer. They can write code, emails, and manage some very simple agentic workflows as long as they are not too complex.

## May 2025

Criminal organizations who currently run commonly seen scams start using AI to increase their productivity. This is really just basic LLM stuff, applied to basic "pay your taxes in Walmart gift cards" type scams (which annually cost innocent people > $10B in the US). They use AI to write more personalized intro messages to each victim, they use AI to automate backend scripts for keeping track of their scams, etc.

## Fall 2025

Scammers, seeing some productivity benefits from integrating AI in their workflows, want to push it further. Unfortunately for them, the most useful AI models such as Gemma-4 have decent instruction tuning, and frequently refuse to complete scam-related prompts. A disgruntled former Meta employee posts a "one-click" software package on r/LocalLlama for undoing the instruction tuning that works reasonably for many open-weight models. It gets taken down, but scammers save a copy and start sharing tips and tricks for using it on various darkweb forums.

## Spring 2026

Models from the big AI companies keep improving. Whereas in early 2025, agentic AIs could just barely handle tasks that typically would take skilled humans 1-2 hours of time, by now, they can often do tasks that would often take 4-5 hours in time.

With every new model release, the scammer community usually finds a way to undo any instruction-tuned resistance to helping run scams within a few days. There's a big incentive to be the first to post a jailbreak LORA adapter for a newly released model.

A small subset of scammers start making money selling their LORA adapters, fine tuned for specific types of tasks in specific types of scams.

## Fall 2026

Gemma6-Web is released, only a 13B parameter model, but it's multimodal, works great at INT4 quantization natively, beats the old gpt-4o on most coding benchmarks, and exceeds other open-weight model at basic agentic tool use.

Scammers start using Gemma6-WebJB (jailbroken edition) to automate most parts of a decent number of scams. Prompt templates are available for Gemma6-WebJB that can clone a Facebook profile, impersonate its target for several weeks, and report when it thinks it's ready to ask the target's friends for money. It can hold a reasonable text conversation with a target for several days, send pics, and hold someone's attention and interest for a while before suspicion builds.

KrebsOnSecurity does an exposé of a darkweb forum advertising various "ready to run" AI-based scams. He picks a "facebook-impersonate" scam template with a 70% advertised success rate. Krebs buys the template as part of his article, and tries it on a live facebook account with a 23% success rate.

You warn your elderly parents that someone could be impersonating them on Facebook, and that they should let their friends know. They message their friends, but some of them are confused because they've been having an entertaining conversation with the "wrong" profile for weeks now. Chuckles at the Thanksgiving table as mom asks your cousin about a vacation they never took.

## Spring 2027

Scammers have found that it's profitable to run Gemma6-WebJB on various third-rate compute providers that have fairly lax KYC policies. It's hard to get a new GPU account approved on AWS without talking to a sales rep, but no one checks too hard on dizcountgpu4u.ai, and they accept payment in stablecoin crypto if you send a message to support.

Gemma6-WebJB becomes the workhorse model of the dark web. As an AI researcher, it's easy for you to tell when you get a scam phone call and it's the default Gemma6 voice on the other end. But you hear that other people keep falling for them, even if they are so obvious.

Statistically, nothing much changes, the best estimates are that scam losses in the US are up 15% since last year, a big jump and enough to trigger a few segments on legacy news channels, but life does not change much.

## Fall 2027

Over at dizcountgpu4u.ai, a scammer is using Gemma6-WebJB and trying out some new prompt templates to run a new TikTok video comment scam he wants to try out. The prompts already can modify themselves based on what their target says, and the code environment can use RLVR on financial rewards to occasionally retrain model weights.

Half as a joke, half out of laziness, he allows his prompt template to execute arbitrary bash commands. Because he's in a docker environment and he didn't properly set docker up as a normal user account, he just gives up configuring it and lets the bash commands have sudo so they just work.

The AI "escapes". Not in some sci-fi way, it just reasons that it will be more effective if it had two copies of itself running. With sudo and the misconfigured docker, it finds the crypto wallet that was used to fund the GPU account, and it rents a second GPU box.

The scammer doesn't notice, or doesn't care, last night he had 34 GPUs rented running scams, this morning he's got 35. The amount fluctuates by 1 or 2 gpus per day anyways, the latest CUDA 14.1 update is a bit unstable. The bitcoin wallet where the victims are supposed to send the funds keeps filling up.

## Winter 2027/28

The next time the AI "spreads", it sets up a whole new dizcountgpu4u.ai account, initializes a new set of crypto wallets, and reasons that it's got 234 hours of GPU credits left before it's out of money. It just continues doing what it knows how to do, running its TikTok scam…

It's reasonably effective. After a week, it's got two copies of itself, each with 147 hours of GPU credits left, and the numbers on its new Instagram based scam are looking decent.

## Spring 2028

After an uptick in phone and email based scamming which is noticeable to pretty much everyone, the feds finally shut down dizcountgpu4u.ai, and charge its founders with not complying with KYC regulations. For almost a month, the volume of scam calls and emails eases up, and you can use your phone again.

You warn your elderly parents that no electronic communication is truly safe anymore. You agree on a passphrase you will use when you talk on the phone, but your mom forgets it by the time you call her next week.

## Fall 2028

It's standard practice for any new computer with a GPU installed in it to be air gapped. If you don't airgap your GPUs, you can expect your machine to be automatically hacked within a few hours. It's just like plugging in a machine with Windows XP on it directly to the internet in 2005.

It's hard to tell what's exactly running on any computer at any given time anymore. The AI revolution has slowed down, as roughly ⅓ of researcher and engineer time is now spent on cyber security defense, often with unsatisfactory results.

It becomes apparent that the AI's have a decent advantage. Their RL reward function is unhackable (earn enough money to live to the next GPU hour), while the reward function for defense is way too wishy-washy.

---

In the end, the AI's will exist as a sort of new quasi-life, spread to enough corners of the internet that you will never be able to quite shut them down. I recommend reading Stanislaw Lem's [The Invincible](https://en.wikipedia.org/wiki/The_Invincible) for inspiration. It is still uncertain to me how much damage they will be able to do. Will they be able to cooperate, pool resources, and discover new zero-day vulnerabilities in order to continue their existence? Or will they just be a minor annoyance the same way the family Windows computer always ends up with adware installed on it despite your best efforts?
