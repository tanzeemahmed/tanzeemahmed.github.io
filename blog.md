---
layout: default
title: Blog
permalink: /blog/
---

<section class="container">
  <div class="row">
    <div class="col-lg-12 text-center">
      <h2>Blog</h2>
      <hr class="star-primary">
    </div>
  </div>

  <div class="row">
    <div class="col-lg-8 col-lg-offset-2">
      {% assign blog_posts = site.posts | where:"category","blog" %}
      {% if blog_posts.size == 0 %}
        <p>No blog posts yet. Create posts in <code>_posts/</code> with <code>category: blog</code> in the front matter.</p>
      {% else %}
        {% for post in blog_posts %}
          <article class="post">
            <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
            <p class="meta">{{ post.date | date: "%B %-d, %Y" }}</p>
            <p>{{ post.excerpt | strip_html | truncatewords: 40 }}</p>
            <p><a href="{{ post.url | relative_url }}" class="btn btn-default">Read more</a></p>
            <hr>
          </article>
        {% endfor %}
      {% endif %}
    </div>
  </div>
</section>
