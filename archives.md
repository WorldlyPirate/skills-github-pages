---
layout: page
title: 归档
permalink: /archives/
---

{% assign postsByYear = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
  <h2>{{ year.name }}</h2>
  <ul>
    {% for post in year.items %}
      <li>{{ post.date | date: "%m-%d" }} - <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
