---
layout: default
title: Beranda
---

<div class="hero-section">
  <h1 class="hero-title">Merenungkan Makna di Ujung Senja</h1>
  <p class="hero-description">Tasawuf, filsafat, dan psikologi spiritual untuk jiwa modern yang haus makna.</p>
</div>

<div class="featured-quote">
  <blockquote>
    "Kegelisahan adalah bahasa jiwa yang sedang mencari Tuhan."
    <cite>— Senja Merah</cite>
  </blockquote>
</div>

<h2 class="section-title">Renungan Terbaru</h2>

{% for post in paginator.posts %}
<article class="post-card">
  <div class="post-card-meta">
    <span class="post-card-category">{{ post.categories | first }}</span>
    <span class="post-card-date">{{ post.date | date: "%d %B %Y" }}</span>
  </div>
  <h2 class="post-card-title">
    <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
  </h2>
  <div class="post-card-excerpt">
    {{ post.excerpt | strip_html | truncatewords: 50 }}
  </div>
  <div class="post-card-footer">
    <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Baca Renungan</a>
    <div class="post-card-tags">
      {% for tag in post.tags limit:3 %}
      <span class="tag">#{{ tag }}</span>
      {% endfor %}
    </div>
  </div>
</article>
{% endfor %}

<!-- Pagination -->
{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ site.baseurl }}{{ paginator.previous_page_path }}" class="prev">&laquo; Sebelumnya</a>
  {% endif %}
  
  <span class="page-number">Halaman {{ paginator.page }} dari {{ paginator.total_pages }}</span>
  
  {% if paginator.next_page %}
    <a href="{{ site.baseurl }}{{ paginator.next_page_path }}" class="next">Selanjutnya &raquo;</a>
  {% endif %}
</div>
{% endif %}
