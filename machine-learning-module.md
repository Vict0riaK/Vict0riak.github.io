---
layout: module
title: Machine Learning Module
permalink: /machine-learning-module/
banner: "assets/images/banners/machine-learning-scaled.webp"
heading: "Machine Learning Module"
---

Welcome to the Machine Learning Module! 👋  
Here you can explore my discussion posts, reflective essays, and assignments.

---


## Posts in This Module
<ul class="post-list">
  {% for post in site.categories.machine-learning %}
    <li class="post-preview">
      <h2><a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="post-meta">{{ post.date | date: "%b %d, %Y" }}</p>

      <div class="post-excerpt">
        {{ post.excerpt }}
      </div>

      <a class="read-more" href="{{ post.url | relative_url }}">Read More</a>
    </li>
  {% endfor %}
</ul>


