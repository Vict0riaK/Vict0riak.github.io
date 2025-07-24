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
  <article>
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p><small>{{ post.date | date: "%b %d, %Y" }} &bull; About {{ post.content | number_of_words | divided_by: 200 }} mins</small></p>

    <p>{{ post.excerpt | strip_html | truncate: 250 }}</p>

    <p><a href="{{ post.url }}">Read More</a></p>

    <p>
      {% if post.tags %}
        {% for tag in post.tags %}
          <span>#{{ tag }}</span>
        {% endfor %}
      {% endif %}
    </p>
    <hr />
  </article>
{% endfor %}

