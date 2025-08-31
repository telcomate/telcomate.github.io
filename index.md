---
layout: home
author_profile: true
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/header-bg.jpg
  actions:
    - label: "Read Latest Posts"
      url: "#latest-posts"
excerpt: "Insights and expertise in telecommunications technology, industry analysis, and technical innovation."
intro: 
  - excerpt: 'Stay updated with the latest trends and developments in the telco industry. Our expert analysis covers emerging technologies, market insights, and technical deep-dives.'
---

{% include feature_row id="intro" type="center" %}

<div id="latest-posts">
  <h2>Latest Posts</h2>
  
  {% for post in site.posts limit:5 %}
    <div class="list__item">
      <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork">
        {% if post.header.teaser %}
          <div class="archive__item-teaser">
            <img src="{{ post.header.teaser | relative_url }}" alt="{{ post.title }}">
          </div>
        {% endif %}
        
        <h3 class="archive__item-title no_toc" itemprop="headline">
          <a href="{{ post.url | relative_url }}" rel="permalink">{{ post.title }}</a>
        </h3>
        
        {% if post.date %}
          <p class="page__meta">
            <i class="far fa-clock" aria-hidden="true"></i>
            <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
          </p>
        {% endif %}
        
        {% if post.excerpt %}
          <p class="archive__item-excerpt" itemprop="description">
            {{ post.excerpt | markdownify | strip_html | truncate: 200 }}
          </p>
        {% endif %}
        
        <p><a href="{{ post.url | relative_url }}" class="btn btn--primary">Read More</a></p>
      </article>
    </div>
  {% endfor %}
  
  <div class="text-center">
    <a href="/posts/" class="btn btn--large btn--info">View All Posts</a>
  </div>
</div>
