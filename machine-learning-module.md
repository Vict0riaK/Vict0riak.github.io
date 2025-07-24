---
layout: default
title: Machine Learning Module
permalink: /machine-learning-module/
banner: "assets/images/banners/machine-learning-scaled.webp"
heading: "Machine Learning Module"
---

Welcome to the Machine Learning Module! 👋  
Here you can explore my discussion posts, reflective essays, and assignments.

---

## 🧠 Posts in This Module

{% for post in site.categories.machine-learning %}
  <div class="post-preview">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    
    <p><small>{{ post.date | date: "%b %d, %Y" }} &bull; About {{ post.content | number_of_words | divided_by: 200 }} mins</small></p>

    <div class="excerpt">
      {{ post.excerpt | strip_html | truncatewords: 50 }}
    </div>

    <p><a href="{{ post.url }}">Read More</a></p>

    {% if post.tags %}
      <p class="tags">
        {% for tag in post.tags %}
          <span class="tag">#{{ tag }}</span>
        {% endfor %}
      </p>
    {% endif %}

    <hr />
  </div>
{% endfor %}


