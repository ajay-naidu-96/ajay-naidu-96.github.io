---
layout: about
title: about
permalink: /about/
subtitle: Portfolio's a work in progress — just like everything in life, one commit at a time!

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false
  more_info:

selected_papers: false
social: true

announcements:
  enabled: true
  scrollable: true
  limit: 5

latest_posts:
  enabled: true
  scrollable: true
  limit: 3
---

Ajay is a Machine Learning Engineer and researcher focused on LLM inference, production ML systems, and performance optimization, with over five years of engineering experience building and scaling AI products at B2B startups. He is currently pursuing graduate research in Artificial Intelligence at the Rochester Institute of Technology (RIT), where his work focuses on practical strategies for deploying efficient AI systems in the real world.

Much of Ajay's engineering journey has revolved around scaling edge-based computer vision systems under tight hardware constraints (and even tighter budgets). In one of his largest deployments, he orchestrated 3–4 GPU-optimized models per site across up to 225 locations, each handling 4 to 25 live camera feeds. At peak, this meant nearly 1,000 video streams running in parallel at 5 frames per second. That experience shaped how he thinks about inference as a systems problem: throughput, memory, scheduling, failure modes, and all the unglamorous details that decide whether a model is actually usable in production.

Through these deployments, he’s come to appreciate that real-world bottlenecks don’t just stem from model size or GPU memory, but from the full inference stack: decoder throughput, batching strategy, scheduling overhead, latency targets, and hardware-specific limits. Lesson learned: you can often load a seemingly massive model onto a device, but production performance is decided by the whole serving pipeline, not just the checkpoint.

Ajay’s current work draws heavily from these production war stories, with a focus on efficient inference, scalable ML systems, and deployment pipelines that make advanced models practical under real constraints. He is especially interested in the engineering gap between a model that benchmarks well and a model that can be served reliably at scale.

If you're working on LLM inference, production ML systems, efficient deployment, or just want to swap GPU war stories, feel free to reach out.

---
