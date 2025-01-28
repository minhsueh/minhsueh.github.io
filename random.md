---
layout: default
title: Random things
rank: 4
---
<!---
Place to show some random things!
14
-->
<ul>
  {% for post in site.random %}
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