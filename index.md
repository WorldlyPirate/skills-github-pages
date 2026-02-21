---
layout: default
---

# 文章列表

{% if paginator.posts %}
  <ul>
    {% for post in paginator.posts %}
      <li>
        {{ post.date | date: "%Y-%m-%d" }} - 
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>

  <div style="margin-top: 20px;">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | relative_url }}">上一页</a>
    {% endif %}
    <span>第 {{ paginator.page }} 页</span>
    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | relative_url }}">下一页</a>
    {% endif %}
  </div>

{% else %}
  <p style="color: red;">警告：分页插件未生效，正在显示全部文章列表：</p>
  <ul>
    {% for post in site.posts %}
      <li>
        {{ post.date | date: "%Y-%m-%d" }} - 
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endif %}
