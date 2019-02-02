---
layout: page
title: Archive 🗃
---

{% for post in site.posts %}
  {% capture currentyear %}{{ post.date | date: "%Y"}}{% endcapture %}
  {% if currentyear != year %}
     {{ currentyear }}
    {% capture year %}{{currentyear}}{% endcapture %}
  {% endif %}
  <ul class="posts-in-year">
    <li><p><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}    </a> &mdash; {{ post.date | date: "%B %d" }}</p></li>
  </ul>
{% endfor %}
