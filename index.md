---
layout: default
---

<div class="home">
  <h1>文章列表</h1>

  <ul class="post-list">
    {% for post in paginator.posts %}
      <li style="margin-bottom: 20px;">
        <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>
      </li>
    {% endfor %}
  </ul>

  {% if paginator.total_pages > 1 %}
  <nav class="pagination">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | relative_url }}">← 上一页</a>
    {% endif %}

    <span> 第 {{ paginator.page }} 页 / 共 {{ paginator.total_pages }} 页 </span>

    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | relative_url }}">下一页 →</a>
    {% endif %}
  </nav>
  {% endif %}
</div>

<p><a href="{{ '/archives/' | relative_url }}">前往归档页面</a></p>
