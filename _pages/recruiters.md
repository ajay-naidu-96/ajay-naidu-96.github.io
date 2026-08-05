---
layout: page
title: recruiters
permalink: /recruiters/
nav: true
nav_order: 6
---

Hi and welcome! If you're here, you are probably looking to understand my technical background and what I can bring to your team. 

Officially, I am actively looking for new opportunities starting May 11, 2026, following my graduation from RIT. Although I had signed an offer to join Sauron Systems as an Inference Engineer starting in July, unexpected organizational changes mean I am back on the market and ready to hit the ground running.

As an Machine Learning Engineer, my focus over the last five years has been on **high throughput inference**, **production ML systems**, and **performance optimization**. But beyond titles, my core philosophy is bridging the gap between a model that's benchmarked in a controlled environment and one that performs reliably in production under real-world constraints.

---

### The Tech Stack & Models

In my experience, deploying AI at scale requires flexibility across the entire stack. Here are some of the key models and tools I’ve worked with:

#### Models & Domains
- Model Stack : Yolo's for object detection, Diffusion and GAN's for generation, and of course I've worked on transformers and pose estimation. Feel free to checkout my github.
- Inference Stack: Edge (Jetson Nano/Xavier/Orin and dGPU) and On-prem cloud. TensorRT, DeepStream SDK, ONNX. INT8/FP16 quantization, structured pruning (NVIDIA TAO), Knowledge Distillation.

#### Frameworks and Languages
- I've primarily worked in two languages Python and C++ and dabbled my way around ML frameworks including Pytorch, TensorRT, Tensorflow and Keras (before it became part of tf). But all in all, I am language agnostic, except for Javascript (yes we might have more in common). 

#### Operating System
- Unfortunately I had to retire from [Arch](https://www.youtube.com/watch?v=Dw-2IHEjylk) to Mac amidst grad school chaos. The link is worth clicking, with appropriate caution.

#### Project Documentation 
-

---

### My Engineering Approach

#### 1. Real-World Bottlenecks over Theoretical Benchmarks
In one of my largest deployments, I orchestrated 4 GPU-optimized models per site across up to 225 locations, handling nearly 1,000 live video streams at 5 FPS on a Jetson Nano. Through these deployments, I realised that loading a massive model onto a device is just step one. True production performance is dictated by the *entire* inference stack: decoder throughput, batching strategy, scheduling overhead, network latency and hardware-specific limits.

#### 2. Coding with(-out) AI
While AI assistance tools are great for productivity, I strongly believe in the concept if you don't use it you lose it. Motivated strongly from years of training in the gym towards my 2x bodyweight squat goals. While I'm learning how to balance both, and not making a skill obsolete, I'm leaning heavily towards going back to basics (daily leetcode is my new hobby). I've come to the conclusion that LLMs can repeat but they can't inherently solve, I've seen them fail horribly at certain problems. But that doesn't mean they aren't useful, they are great for automating repeatable stuff. Novel execution still requires human cognitive ability. 

Note: If you are like me and still don't understand how people are able to review code written by LLMs given that their throughput is usually higher than cognitive load of a human, I'm curious how your teams are managing code reviews. 

#### 3. Core Values
- Be honest
- Prioritize Health (Mental and Physical)
- Be Egotistical, have the ego towards the problems you are solving not against people
- Results over obstacles


#### 4. Extremely Goal Oriented
Will be added soon...

---

If you're hiring for a role that requires scaling edge deployments, optimizing LLM inference, or building robust ML pipelines from scratch, I'd love to chat.
