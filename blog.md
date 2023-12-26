---
layout: default
title: Blog
rank: 0
---
<ul>
  {% for post in site.posts %}
    <li>
    <span class="post-meta">{{ post.date | date: site.date_format }}</span>
    <h3>
      <a class="post-link" href="{{ post.url | relative_url }}">
        {{ post.title | escape }}
      </a>
    </h3>
    {%- if site.show_excerpts -%}
      {{ post.excerpt }}
    {%- endif -%}
    </li>
  <!--
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  -->
  {% endfor %}
</ul>