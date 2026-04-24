---
layout: page
title: bookshelf
permalink: /books/
nav: true
nav_order: 5
collection: books
---

<style>
  :root {
    --card-bg-elevated: rgba(255, 255, 255, 0.03);
    --text-primary: #f7f7f5;
    --text-secondary: #a4a4a0;
    --text-muted: #72726d;
    --accent: #ffffff;
    --border: rgba(255, 255, 255, 0.12);
    --shadow: 0 24px 80px rgba(0, 0, 0, 0.3);
    --radius: 20px;
    --transition: 220ms ease;
  }

  .bookshelf-page {
    font-family: 'Inter', sans-serif;
  }
  
  .bookshelf-page h1, .bookshelf-page h2 {
    font-family: 'Playfair Display', serif;
    color: var(--text-primary);
  }

  .bookshelf-page hr {
    border: 0;
    height: 1px;
    background: var(--border);
    margin: 40px 0;
  }

  .book-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 24px;
    margin-top: 24px;
    margin-bottom: 40px;
  }

  .book-card {
    border: 1px solid var(--border);
    background:
      linear-gradient(180deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.01)),
      #131313;
    border-radius: var(--radius);
    padding: 24px;
    display: flex;
    transition:
      transform var(--transition),
      border-color var(--transition),
      box-shadow var(--transition);
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.05);
    position: relative;
    overflow: hidden;
  }

  .book-card::before {
    content: '';
    position: absolute;
    inset: 0 0 auto;
    height: 3px;
    background: linear-gradient(90deg, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0.1));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform var(--transition);
  }

  .book-card:hover {
    transform: translateY(-5px);
    border-color: rgba(255, 255, 255, 0.2);
    box-shadow: var(--shadow);
  }

  .book-card:hover::before {
    transform: scaleX(1);
  }

  .book-image {
    width: 80px;
    height: 120px;
    object-fit: cover;
    border-radius: 6px;
    margin-right: 20px;
    flex-shrink: 0;
    box-shadow: 0 4px 12px rgba(0,0,0,0.5);
    border: 1px solid rgba(255,255,255,0.1);
    background: #1e1e1e;
  }

  .book-info {
    flex: 1;
    display: flex;
    flex-direction: column;
  }

  .book-title {
    font-weight: 600;
    font-size: 1.05rem;
    margin-bottom: 4px;
    color: var(--text-primary);
    text-decoration: none;
    line-height: 1.3;
    letter-spacing: -0.01em;
  }

  .book-title:hover {
    color: var(--accent);
    text-decoration: underline;
  }

  .book-author {
    font-size: 0.85rem;
    color: var(--text-muted);
    margin-bottom: 12px;
  }

  .book-meta {
    margin-bottom: 12px;
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .tag {
    background: rgba(255, 255, 255, 0.06);
    border: 1px solid rgba(255, 255, 255, 0.08);
    padding: 3px 10px;
    border-radius: 12px;
    font-size: 0.65rem;
    color: var(--text-secondary);
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.1em;
  }

  .tag.status-reading { color: #facc15; border-color: rgba(250, 204, 21, 0.3); background: rgba(250, 204, 21, 0.05); }
  .tag.status-complete { color: #4ade80; border-color: rgba(74, 222, 128, 0.3); background: rgba(74, 222, 128, 0.05); }

  .book-notes {
    font-size: 0.85rem;
    color: var(--text-secondary);
    line-height: 1.5;
    margin: 0;
  }
</style>

<div class="bookshelf-page" markdown="1">

# My Reading Journey

Didn't think I'd be a huge reader. But I have a growing collection of books that have shaped my thinking and learning. I focus on engineering depth and the athlete/growth mindset.

---

## Performance Mindset

<div class="book-grid">
  <div class="book-card">
    <img src="https://covers.openlibrary.org/b/isbn/1476714207-L.jpg" class="book-image" alt="Relentless cover" onerror="this.src='https://via.placeholder.com/80x120/1e1e1e/555?text=Book'">
    <div class="book-info">
      <a href="https://www.amazon.com/Relentless-Unstoppable-Tim-S-Grover/dp/1476714207" class="book-title">Relentless</a>
      <div class="book-author">Tim S. Grover</div>
      <div class="book-meta">
        <span class="tag status-complete">Completed</span>
        <span class="tag">Psychology</span>
      </div>
      <p class="book-notes">Essential for understanding the "Cleaner" mindset and high-stakes performance.</p>
    </div>
  </div>

  <div class="book-card">
    <img src="https://covers.openlibrary.org/b/isbn/1623365627-L.jpg" class="book-image" alt="The Champion's Mind cover" onerror="this.src='https://via.placeholder.com/80x120/1e1e1e/555?text=Book'">
    <div class="book-info">
      <a href="https://www.amazon.com/Champions-Mind-Great-Athletes-Think/dp/1623365627" class="book-title">The Champion's Mind</a>
      <div class="book-author">Jim Afremow</div>
      <div class="book-meta">
        <span class="tag status-complete">Completed</span>
        <span class="tag">Psychology</span>
      </div>
      <p class="book-notes">Practical drills and mental frameworks used by Olympic athletes.</p>
    </div>
  </div>

  <div class="book-card">
    <img src="https://covers.openlibrary.org/b/isbn/0008438838-L.jpg" class="book-image" alt="Relentless Alistair Brownlee cover" onerror="this.src='https://via.placeholder.com/80x120/1e1e1e/555?text=Book'">
    <div class="book-info">
      <a href="https://www.amazon.com/Relentless-Alistair-Brownlee/dp/0008438838" class="book-title">Relentless</a>
      <div class="book-author">Alistair Brownlee</div>
      <div class="book-meta">
        <span class="tag status-complete">Completed</span>
        <span class="tag">Sport Science</span>
      </div>
      <p class="book-notes">A deep dive into what makes endurance athletes extraordinary.</p>
    </div>
  </div>
</div>

---

## Engineering

<div class="book-grid">
  <div class="book-card">
    <img src="https://covers.openlibrary.org/b/isbn/1633437167-L.jpg" class="book-image" alt="Build a Large Language Model cover" onerror="this.src='https://via.placeholder.com/80x120/1e1e1e/555?text=Book'">
    <div class="book-info">
      <a href="https://www.amazon.com/Build-Large-Language-Model-Scratch/dp/1633437167" class="book-title">Build a Large Language Model (From Scratch)</a>
      <div class="book-author">Sebastian Raschka</div>
      <div class="book-meta">
        <span class="tag status-complete">Completed</span>
        <span class="tag">Deep Learning</span>
      </div>
      <p class="book-notes">An excellent hands-on guide for understanding LLMs from the ground up.</p>
    </div>
  </div>

  <div class="book-card">
    <img src="https://covers.openlibrary.org/b/isbn/9781736049105-L.jpg" class="book-image" alt="Machine Learning System Design Interview cover" onerror="this.src='https://via.placeholder.com/80x120/1e1e1e/555?text=Book'">
    <div class="book-info">
      <a href="https://bytebytego.com/" class="book-title">Machine Learning System Design Interview</a>
      <div class="book-author">Ali Aminian, Alex Xu</div>
      <div class="book-meta">
        <span class="tag status-complete">Completed</span>
        <span class="tag">System Design</span>
      </div>
      <p class="book-notes">Essential reading for architectural patterns and real-world ML deployments.</p>
    </div>
  </div>
  
  <div class="book-card">
    <img src="https://covers.openlibrary.org/b/isbn/0128154128-L.jpg" class="book-image" alt="Engineering a Compiler cover" onerror="this.src='https://via.placeholder.com/80x120/1e1e1e/555?text=Book'">
    <div class="book-info">
      <a href="https://www.amazon.com/Engineering-Compiler-Keith-Cooper/dp/0128154128" class="book-title">Engineering a Compiler</a>
      <div class="book-author">Keith D. Cooper, Linda Torczon</div>
      <div class="book-meta">
        <span class="tag status-reading">Reading</span>
        <span class="tag">Computer Science</span>
      </div>
      <p class="book-notes">Deep dive into the intricacies of translating code into optimized machine instructions.</p>
    </div>
  </div>

  <div class="book-card">
    <img src="https://covers.openlibrary.org/b/isbn/0323814723-L.jpg" class="book-image" alt="Programming Massively Parallel Processors cover" onerror="this.src='https://via.placeholder.com/80x120/1e1e1e/555?text=Book'">
    <div class="book-info">
      <a href="https://www.amazon.com/Programming-Massively-Parallel-Processors-Hands/dp/0323814723" class="book-title">Programming Massively Parallel Processors</a>
      <div class="book-author">David B. Kirk, Wen-mei W. Hwu</div>
      <div class="book-meta">
        <span class="tag status-reading">Reading</span>
        <span class="tag">CUDA</span>
      </div>
      <p class="book-notes">A hands-on approach to CUDA and understanding parallel architectures.</p>
    </div>
  </div>
</div>

---

Feel free to reach out if you want to discuss any of these books or share recommendations!
</div>