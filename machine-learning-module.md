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
{% for post in site.categories.machine-learning %}
  <div class="post-preview">
    <h2><a class="post-title" href="{{ post.url }}">{{ post.title }}</a></h2>
    
    <p class="post-meta">{{ post.date | date: "%b %d, %Y" }}</p>

    <div class="post-excerpt">
      {{ post.excerpt }}
    </div>

    <p><a class="read-more" href="{{ post.url }}">Read More</a></p>

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


    <hr />
  </div>
{% endfor %}



