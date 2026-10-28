---
layout: page
title: Archive
permalink: /archive/
description: Every entry, collected in one place.
---
<div class="archive-list">
  {% assign current_year = "" %}
  {% for post in site.posts %}
    {% assign post_year = post.date | date: "%Y" %}
    {% if post_year != current_year %}
      {% unless forloop.first %}</div>{% endunless %}
      <h2 class="archive-year">{{ post_year }}</h2>
      <div class="archive-year-group">
      {% assign current_year = post_year %}
    {% endif %}
    <article class="archive-entry">
      <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %d" }}</time>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      {% if post.categories.size > 0 %}<span>{{ post.categories | first }}</span>{% endif %}
    </article>
    {% if forloop.last %}</div>{% endif %}
  {% endfor %}
  {% if site.posts.size == 0 %}<p>No posts yet. Your archive will appear here once you publish.</p>{% endif %}
</div>
