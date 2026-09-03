---
layout: default
title: 홈
---

{%- assign topics = "All,Meetup,GitHub,Copilot,Workflow,Retrospective,Dev Notes" | split: "," -%}

<div class="home">

  {%- comment -%} ===================== Topics filter ===================== {%- endcomment -%}
  <section class="topics" aria-label="주제 필터">
    <span class="topics-label">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M20.59 13.41 13.42 20.58a2 2 0 0 1-2.83 0L2 12V2h10l8.59 8.59a2 2 0 0 1 0 2.82Z" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/><circle cx="7" cy="7" r="1.4" fill="currentColor"/></svg>
      Topics
    </span>
    <div class="topic-pills" role="tablist">
      {%- for topic in topics -%}
        {%- assign t = topic | strip -%}
        <button type="button" class="topic-pill{% if forloop.first %} is-active{% endif %}" data-topic="{{ t | slugify }}">{{ t }}</button>
      {%- endfor -%}
    </div>
  </section>

  {%- comment -%} ===================== Featured post ===================== {%- endcomment -%}
  {%- assign featured = site.posts.first -%}
  {%- if featured -%}
    {%- assign fchars = featured.content | strip_html | strip_newlines | size -%}
    {%- assign fread = fchars | divided_by: 500 | plus: 1 -%}
    <section class="featured" aria-labelledby="featured-title">
      <div class="featured-copy">
        <p class="eyebrow eyebrow-accent">✦ Featured Post</p>
        <h1 id="featured-title" class="featured-heading">{{ featured.headline | default: featured.title }}</h1>
        {%- if featured.excerpt -%}
          <p class="featured-desc">{{ featured.excerpt | strip_html | truncate: 120 }}</p>
        {%- endif -%}
        <div class="featured-meta">
          <span class="meta-item"><svg width="15" height="15" viewBox="0 0 24 24" fill="none" aria-hidden="true"><rect x="3" y="4.5" width="18" height="16" rx="2" stroke="currentColor" stroke-width="1.7"/><path d="M3 9h18M8 2.5v4M16 2.5v4" stroke="currentColor" stroke-width="1.7" stroke-linecap="round"/></svg>{{ featured.date | date: "%Y.%m.%d" }}</span>
          <span class="meta-item"><svg width="15" height="15" viewBox="0 0 24 24" fill="none" aria-hidden="true"><circle cx="12" cy="12" r="9" stroke="currentColor" stroke-width="1.7"/><path d="M12 7v5l3 2" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round"/></svg>{{ fread }} min read</span>
          {%- for tag in featured.tags limit: 2 -%}
            <span class="tag-chip">{{ tag }}</span>
          {%- endfor -%}
        </div>
        <a class="featured-cta" href="{{ featured.url | relative_url }}">Read the full recap <span aria-hidden="true">→</span></a>
      </div>

      <a class="featured-visual" href="{{ featured.url | relative_url }}" aria-label="{{ featured.title }}">
        {%- if featured.image -%}
          <img src="{{ featured.image | relative_url }}" alt="" loading="lazy">
        {%- endif -%}
      </a>
    </section>
  {%- endif -%}

  {%- comment -%} ===================== Posts (7) : Activity log (3) ===================== {%- endcomment -%}
  <div class="home-columns">

    <section class="recent" aria-labelledby="recent-title">
      <header class="col-head">
        <h2 id="recent-title">All posts</h2>
        <a class="col-link" href="{{ '/' | relative_url }}">View all posts <span aria-hidden="true">→</span></a>
      </header>

      <ul class="post-list">
        {%- for post in site.posts -%}
          {%- assign pchars = post.content | strip_html | strip_newlines | size -%}
          {%- assign pread = pchars | divided_by: 500 | plus: 1 -%}
          {%- assign topic_data = post.categories | concat: post.tags | join: " " | slugify -%}
          <li class="post-row" data-topics="{{ topic_data }}">
            <a href="{{ post.url | relative_url }}">
              <span class="post-row-thumb">
                {%- if post.image -%}
                  <img src="{{ post.image | relative_url }}" alt="" loading="lazy">
                {%- else -%}
                  <span class="post-row-thumb-fallback" aria-hidden="true">{{ post.title | slice: 0 }}</span>
                {%- endif -%}
              </span>
              <span class="post-row-body">
                <span class="post-row-title">{{ post.title }}</span>
                {%- if post.excerpt -%}
                  <span class="post-row-desc">{{ post.excerpt | strip_html | truncate: 62 }}</span>
                {%- endif -%}
                <span class="post-row-tags">
                  {%- for tag in post.tags limit: 2 -%}
                    <span class="tag-chip tag-chip-sm">{{ tag }}</span>
                  {%- endfor -%}
                </span>
              </span>
              <span class="post-row-meta">
                <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time>
                <span class="post-row-read">{{ pread }} min read</span>
              </span>
            </a>
          </li>
        {%- endfor -%}
      </ul>
      <p class="post-list-empty" hidden>해당 주제의 글이 아직 없어요.</p>
    </section>

    <section class="activity" aria-labelledby="activity-title">
      <header class="activity-head">
        <h2 id="activity-title" class="mono"><span class="activity-slash">//</span> activity.log <span class="count-badge">{{ site.posts | size }} commits</span></h2>
        <a class="activity-viewall mono" href="{{ '/' | relative_url }}">view all →</a>
      </header>

      <ul class="activity-list">
        {%- for post in site.posts -%}
          {%- assign msg = post.headline | default: post.title | replace: "<br>", " " | strip_html -%}
          {%- assign ctype = post.commit_type | default: "feat" -%}
          {%- assign ctag = post.categories | first | default: "post" | downcase -%}
          <li class="activity-row">
            <a class="activity-main" href="{{ post.url | relative_url }}">
              <span class="activity-dot" aria-hidden="true"></span>
              <span class="activity-hash mono">{{ post.hash | default: post.date | date: "%y%m%d0" }}</span>
              <span class="activity-text"><span class="activity-type mono">{{ ctype }}:</span> {{ msg }}</span>
              <span class="activity-tag activity-tag--{{ ctag }} mono">{{ ctag }}</span>
            </a>
            <time class="activity-date mono" datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time>
          </li>
        {%- endfor -%}
      </ul>
    </section>

  </div>
</div>

<script>
  (function () {
    var pills = document.querySelectorAll('.topic-pill');
    var rows = document.querySelectorAll('.post-row');
    var empty = document.querySelector('.post-list-empty');
    pills.forEach(function (pill) {
      pill.addEventListener('click', function () {
        pills.forEach(function (p) { p.classList.remove('is-active'); });
        pill.classList.add('is-active');
        var topic = pill.getAttribute('data-topic');
        var visible = 0;
        rows.forEach(function (row) {
          var topics = row.getAttribute('data-topics') || '';
          var show = topic === 'all' || topics.indexOf(topic) !== -1;
          row.hidden = !show;
          if (show) { visible++; }
        });
        if (empty) { empty.hidden = visible !== 0; }
      });
    });
  })();
</script>
