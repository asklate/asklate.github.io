---
layout: page
title: Topics
permalink: /topics/
description: Browse the notebook by recurring interests.
---
{% assign all_tags = site.tags | sort %}
{% if all_tags.size > 0 %}
  <div class="topic-cloud">
    {% for tag in all_tags %}
      <a id="{{ tag[0] | slugify }}" href="#{{ tag[0] | slugify }}">{{ tag[0] }} <span>{{ tag[1].size }}</span></a>
    {% endfor %}
  </div>
  {% for tag in all_tags %}
<section class="topic-section" id="{{ tag[0] | slugify }}-posts">
  <h2>{{ tag[0] }}<span class="accent-dot">.</span></h2>
  {% for post in tag[1] %}
    <p class="topic-post"><time>{{ post.date | date: "%b %-d, %Y" }}</time><a href="{{ post.url | relative_url }}">{{ post.title }}</a></p>
  {% endfor %}
</section>
  {% endfor %}
{% else %}
  <p>Add tags to your posts’ front matter and they’ll be collected here automatically.</p>
{% endif %}
