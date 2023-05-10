---
title: "Resource"

layout: single
author_profile: true
toc: false
sidebar:
  nav: docs
---

{% assign posts = site.categories.resource %}
{% for post in posts %} {% include archive-custom.html type=page.entries_layout %} {% endfor %}