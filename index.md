---
layout: default
title: 홈
---

<div class="home-page">
  <section class="home-hero" aria-labelledby="home-title">
    <p class="home-eyebrow">GitHub · Copilot · Developer Experience</p>
    <h1 id="home-title">배우고, 만들고,<br>나누는 개발 기록</h1>
    <p class="home-intro">GitHub와 AI 기반 개발을 공부하며 직접 경험하고 배운 내용을 기록합니다.</p>
    <a class="home-cta" href="#recent-posts">최근 글 보기</a>
  </section>

  <section class="recent-posts" id="recent-posts" aria-labelledby="recent-posts-title">
    <header class="section-heading">
      <div>
        <p class="section-label">Latest</p>
        <h2 id="recent-posts-title">최근 글</h2>
      </div>
      <p>{{ site.posts | size }}개의 기록</p>
    </header>

    <div class="post-card-grid">
      {% for post in site.posts %}
        <article class="post-card">
          <a href="{{ post.url | relative_url }}">
            {% if post.image %}
              <div class="post-card-image">
                <img src="{{ post.image | relative_url }}" alt="" loading="lazy">
              </div>
            {% endif %}
            <div class="post-card-body">
              <p class="post-card-meta">
                <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y.%m.%d" }}</time>
                {% if post.categories.size > 0 %}
                  <span>{{ post.categories | join: " · " }}</span>
                {% endif %}
              </p>
              <h3>{{ post.title }}</h3>
              <p class="post-card-excerpt">{{ post.excerpt | strip_html | normalize_whitespace | truncate: 150 }}</p>
              <span class="post-card-link">글 읽기</span>
            </div>
          </a>
        </article>
      {% else %}
        <p class="empty-posts">아직 작성된 글이 없습니다.</p>
      {% endfor %}
    </div>
  </section>
</div>
