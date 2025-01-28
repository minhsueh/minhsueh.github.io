---
layout: default
title: Random things
rank: 4
---
<!---
Place to show some random things!
14
-->
<h2>Random Topics</h2>
<ul>
  {% for post in site.random %}
    <li>
      <span class="post-meta">{{ post.date | date: "%B %d, %Y" }}</span>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
