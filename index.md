---
layout: home-landing
title: 牵着蜗牛去长大
permalink: /
---

{% assign public_notes = site.notes | where_exp: "note", "note.listed != false" | sort: "order" %}
{% assign grouped_notes = public_notes | group_by: "category" %}

<section class="home-hero">
  <div class="home-hero-copy">
    <p class="home-kicker">亲历、阅读与分析</p>
    <h1>牵着蜗牛去长大</h1>
    <p class="home-lead">把亲身经历过的事、读过的书，以及围绕养育、学习支持和心理边界做过的系统分析，写成适合公开阅读、适合长期回看的中文笔记。</p>
    <p class="home-sublead">这里不是碎片化动态流，也不是原始素材堆放区，而是把真实经历、阅读吸收和方法判断重新梳理后的公开写作。第一次来到这里，先从一条阅读路线开始会更容易进入。</p>
    <div class="home-actions">
      <a class="home-button home-button-primary" href="{{ '/notes/why-i-write-qian-zhe-woniu-qu-changda/' | relative_url }}">先看发刊文</a>
      <a class="home-button home-button-secondary" href="{{ '/docs/' | relative_url }}">浏览文档入口</a>
      <a class="home-button home-button-minimal" href="{{ '/notes/' | relative_url }}">查看全部笔记</a>
    </div>
  </div>

  <aside class="home-hero-panel">
    <p class="home-panel-kicker">站点说明</p>
    <h2>亲历经验、阅读和分析之后的公开写作</h2>
    <p>这里放的是从真实经历出发，再经过阅读、拆解和系统分析后写成的内容，重点是那些值得公开阅读和长期回看的判断、方法与结构。</p>

    <dl class="home-stats">
      <div>
        <dt>公开笔记</dt>
        <dd>{{ public_notes | size }}</dd>
      </div>
      <div>
        <dt>内容分类</dt>
        <dd>{{ grouped_notes | size }}</dd>
      </div>
      <div>
        <dt>导航入口</dt>
        <dd>{{ site.header_pages | size }}</dd>
      </div>
    </dl>

    <ul class="home-panel-list">
      <li>先读发刊文，知道这组内容为什么存在。</li>
      <li>再进文档页或专题卡片，按主题展开阅读。</li>
      <li>如果你是长期读者，可以直接进入全部笔记。</li>
    </ul>

  </aside>
</section>

<section class="home-foreword">
  <div class="home-foreword-mark">写在前面</div>
  <div class="home-foreword-body">
    <p>这不是一套标准答案，也不是某种成功学经验汇编。</p>
    <p>它更像一份缓慢整理的公开记录：把养育里的困惑、试错、边界和方法，一点点写清楚，留给后来也在摸索的人。</p>
    <p>如果这些文字能帮一个家庭少走一点弯路，这个站就值得继续写下去。</p>
  </div>
</section>

<section class="home-section">
  <div class="home-section-head">
    <div>
      <p class="home-kicker">从这里开始</p>
      <h2>先选入口，再选文章</h2>
    </div>
    <p>首页最重要的工作，不是把所有链接平铺出来，而是先帮读者决定从哪里进入。</p>
  </div>

  <div class="home-card-grid home-card-grid-3">
    <article class="home-card">
      <span class="home-card-badge">01</span>
      <h3>先看发刊文</h3>
      <p>如果你想知道这组内容的起点、问题意识和写作边界，先从发刊文开始最稳。</p>
      <ul class="home-link-list">
        <li><a href="{{ '/notes/why-i-write-qian-zhe-woniu-qu-changda/' | relative_url }}">为什么我要写《牵着蜗牛去长大》</a></li>
      </ul>
    </article>

    <article class="home-card">
      <span class="home-card-badge">02</span>
      <h3>看总览页</h3>
      <p>如果你只想快速了解当前已公开内容，文档页会比逐篇翻找更省时间。</p>
      <ul class="home-link-list">
        <li><a href="{{ '/docs/' | relative_url }}">文档页</a></li>
        <li><a href="{{ '/notes/' | relative_url }}">全部笔记</a></li>
      </ul>
    </article>

    <article class="home-card">
      <span class="home-card-badge">03</span>
      <h3>按问题进入</h3>
      <p>如果你已经有明确问题，可以直接跳到成长规划、学习机、心理边界和模型方法这几条线索。</p>
      <ul class="home-link-list">
        <li><a href="{{ '/notes/education-stages/' | relative_url }}">成长规划</a></li>
        <li><a href="{{ '/notes/xueersi-learning-machine-14-day-summary/' | relative_url }}">学习机专题</a></li>
        <li><a href="{{ '/notes/npd-guide/' | relative_url }}">心理专题</a></li>
      </ul>
    </article>
  </div>
</section>



<section class="home-section">
  <div class="home-section-head">
    <div>
      <p class="home-kicker">优先阅读</p>
      <h2>把常用入口收成四组主题</h2>
    </div>
    <p>首页不需要展示全部细节，但应该把最值得先读的内容组织成清楚的主题块。</p>
  </div>

  <div class="home-card-grid home-card-grid-2">
    <article class="home-card">
      <p class="home-card-kicker">成长规划</p>
      <h3>先判断阶段，再安排行动</h3>
      <p>适合正处在学习支持、入学准备和家庭节奏调整阶段的家长作为行动型入口。</p>
      <ul class="home-link-list">
        <li><a href="{{ '/notes/education-stages/' | relative_url }}">孩子学习的关键阶段</a></li>
        <li><a href="{{ '/notes/primary-school-readiness/' | relative_url }}">小学入学前，家长该做哪些准备？</a></li>
      </ul>
    </article>

    <article class="home-card">
      <p class="home-card-kicker">学习机专题</p>
      <h3>从连续观察里看伴学方法</h3>
      <p>把 14 天伴学内容拆成完整整理和逐日目录，适合想快速了解学习机使用逻辑的人。</p>
      <ul class="home-link-list">
        <li><a href="{{ '/notes/xueersi-learning-machine-14-day-summary/' | relative_url }}">完整整理</a></li>
        <li><a href="{{ '/notes/xueersi-learning-machine-14-day-transcript/' | relative_url }}">视频整理目录</a></li>
      </ul>
    </article>

    <article class="home-card">
      <p class="home-card-kicker">心理专题</p>
      <h3>按类型理解特征、影响和边界</h3>
      <p>把常见人格模式拆开看，避免把复杂问题一股脑混成一个模糊标签。</p>
      <div class="home-pill-list">
        <a class="home-pill" href="{{ '/notes/npd-guide/' | relative_url }}">NPD</a>
        <a class="home-pill" href="{{ '/notes/aspd-guide/' | relative_url }}">ASPD</a>
        <a class="home-pill" href="{{ '/notes/bpd-guide/' | relative_url }}">BPD</a>
        <a class="home-pill" href="{{ '/notes/hpd-guide/' | relative_url }}">HPD</a>
        <a class="home-pill" href="{{ '/notes/ocpd-guide/' | relative_url }}">OCPD</a>
        <a class="home-pill" href="{{ '/notes/ppd-guide/' | relative_url }}">PPD</a>
      </div>
    </article>

    <article class="home-card">
      <p class="home-card-kicker">模型与书摘</p>
      <h3>补方法框架，也补长期视角</h3>
      <p>一部分内容用模型帮助行动，一部分内容用书摘和整理帮助重新理解家庭处境。</p>
      <ul class="home-link-list">
        <li><a href="{{ '/notes/fogg-behavior-model/' | relative_url }}">福格行为模型</a></li>
        <li><a href="{{ '/notes/family-awakening/' | relative_url }}">家庭的觉醒</a></li>
      </ul>
    </article>
  </div>
</section>

<section class="home-boundary">
  <p class="home-kicker">公开边界</p>
  <h2>这里公开的，不是零散归档，而是我亲身经历过的事、读过的书，以及反复分析之后留下来的方法、判断和结构。</h2>
  <p>未经处理的生活细节、原始素材和情绪化记录不会直接放进来。第一次来到这里，建议按“发刊文 → 文档页 → 专题文章”的顺序阅读；如果你已经知道自己要找什么，直接从上面的主题入口进入即可。</p>
</section>
