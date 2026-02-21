---
layout: default
---

<div class="home">
  <h1>Posts</h1>
  <ul class="post-list">
    {% for post in paginator.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      </li>
    {% endfor %}
  </ul>

  {% if paginator.total_pages > 1 %}
  <div class="pagination" style="margin-top: 20px; padding: 10px; border-top: 1px solid #eee;">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | relative_url }}">← 上一页</a>
    {% endif %}
    
    <span> 第 {{ paginator.page }} 页 / 共 {{ paginator.total_pages }} 页 </span>

    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | relative_url }}">下一页 →</a>
    {% endif %}
  </div>
  {% endif %}
</div>
