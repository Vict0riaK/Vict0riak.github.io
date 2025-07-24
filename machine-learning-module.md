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

<ul>
  {% for post in site.categories.machine-learning %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}
    </li>
  {% endfor %}
</ul>

