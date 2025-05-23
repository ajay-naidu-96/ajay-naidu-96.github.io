---
layout: post
title: Code Quality, A Journey from AI Generated Dumpster Fire
date: 2025-05-19 12:21:00
description: just some good old venting
tags: hiring
categories: sample-posts
thumbnail: assets/img/9.jpg
giscus_comments: true
---

AI Generated Code has been a hot topic, from companies adopting "vibe" coding to potential candidates using GPT or any of the LLMs to trick their way into clearing coding rounds. This post serves as a guided tour as to what *not* to do -- and why it matters? When using AI generated code from both sides of the lens, captured from a platform that uses AI generated code to prepare candidates for coding interviews on their platform. Surprisingly, the same is used by Pinterest, Netlix to name a few to screen candidates. I encountered CodeSignal as I was taking up a code screening test for Pinterest, the test had two types of code tests, a traditional leetcode style question and an implementation of ML Algorithm from scratch. This post will be covering the latter type of question in coding rounds. 

At the time of writing, I do not have access to the exact question, because the platform failed to share the question post the tests because of their policy, but I will give an intuition on the problem setting, sharing examples of algorithms from their platform. A lot of it is written from a design point of view on what constitutes a good code vs terribly written AI code. I hopped on their platform after my test, but couldn't get past two weeks after looking at the poorly written code. I will be taking examples of an ML algorithm from their platform to show the problem, 

### List Comprehension, but Without the Comprehension

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/codesignal/func1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An example of a very, unelegantly written list comprehension.
</div>

The above code simply computes a distance metric to cluster fruits and assigns the top k closest labels to classify a.k.a K Nearest Neighbour Classification. While it took me a while to really comprehend what was going on inside that list (line 7-8), this additionally made it challenging looking at the variable names used. While I did rewrite the function splitting it into two standalone functions that just does one thing respectively as shown in the next picture, 

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/codesignal/new_func1.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An example of an okayishly written code that uses list comprehension when necessary.
</div>

Not that I'm saying one code is better than the other (actually it is), when debugging a block of code, things do get easier when the code is written with some clarity and design principles. Not to mention, the linter making it worse in terms of reading the code (the yellow squiggly lines all over). 

### Import Confusion

Another example when their LLM just casually inserting an import in the middle of the function on line 21, 

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/codesignal/import.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    wow import.
</div>

While it does make sense to use AI for assissted code (maybe), but to test candidates using AI generated code, seems like something is fundamentally wrong with the system. This post was written after a test I took up for one of the companies that used the platform, while the leetcode question seemed straightforward, but to test or debug algorithms that are just poorly designed would confuse a test taker given the limited time that they have to take up the test. I'm not sure if this would be reflective of the type of code that is written at the company but I'd be cautious if it were to be me. Now for the second problem of AI generated code, is that overreliance can sometime lead to not trusting yourself to solve the problem as we use more and more of the AI generated code, or atleast that's how I felt during my initial days of using AI generated code. 