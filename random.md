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
  {% assign categories = site.random | group_by: "category" %}
  {% for category in categories %}
    <h2>{{ category.name | capitalize }}</h2>
      {% for post in category.items %}
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
      {% endfor %}
  {% endfor %}
</ul>
