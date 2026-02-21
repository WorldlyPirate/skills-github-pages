---
layout: default
---

<form action="https://www.google.com/search" method="get">
  <input type="hidden" name="q" value="site:WorldlyPirate.github.io/skills-github-pages/">
  <input type="text" name="q" placeholder="搜索文章..." style="padding: 5px; width: 200px;">
  <button type="submit">搜索</button>
</form>

<hr>

<div class="home">
  <ul class="post-list">
    {% for post in paginator.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      </li>
    {% endfor %}
  </ul>

  {% if paginator.total_pages > 1 %}
    <div style="background: #f4f4f4; padding: 10px; text-align: center;">
      {% if paginator.previous_page %}
        <a href="{{ paginator.previous_page_path | relative_url }}">上一页</a>
      {% endif %}
      <span> 第 {{ paginator.page }} 页 </span>
      {% if paginator.next_page %}
        <a href="{{ paginator.next_page_path | relative_url }}">下一页</a>
      {% endif %}
    </div>
  {% endif %}
</div>

<hr>
<a href="{{ '/archives/' | relative_url }}">查看所有归档...</a>
