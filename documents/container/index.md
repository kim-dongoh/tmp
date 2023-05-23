---
layout: single
parmalink: /documents/container/
sidebar:
  nav: container
---

{% assign posts = site.categories.container %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}