---
title: "Resource"

layout: single
author_profile: true
toc: false
sidebar:
  nav: hashicorp
---

{% assign sorted_posts = site.categories.resource | sort:"order" %}
{% for post in sorted_posts %}
  <li><a href="{{post.url}}">{{post.title}}</a></li>
{% endfor %}