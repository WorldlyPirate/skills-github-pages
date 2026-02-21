---
layout: default
---

<div class="home">
  <h1 class="page-heading">Posts</h1>

  <ul class="post-list">
    {% for post in paginator.posts %}
      <li>
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
      </li>
    {% endfor %}
  </ul>

  {% if paginator.total_pages > 1 %}
  <div class="pagination">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | relative_url }}" class="previous">上一页</a>
    {% else %}
      <span class="previous">上一页</span>
    {% endif %}

    <span class="page_number ">第 {{ paginator.page }} 页，共 {{ paginator.total_pages }} 页</span>

    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | relative_url }}" class="next">下一页</a>
    {% else %}
      <span class="next">下一页</span>
    {% endif %}
  </div>
  {% endif %}
</div>
