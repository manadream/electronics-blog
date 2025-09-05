---
layout: page
title: Tags
permalink: /tags/
---

{% if site.tags.size > 0 %}
  <div class="tag-list">
    {% for tag in site.tags %}
      {% assign tag_name = tag | first %}
      {% assign tag_posts = tag | last %}
      <h3><a href="#{{ tag_name | slugify }}">{{ tag_name }}</a> ({{ tag_posts | size }})</h3>
      <ul>
        {% for post in tag_posts %}
          <li>
            <a class="post-link" href="{{ post.url | relative_url }}">
              {{ post.title | escape }}
            </a>
          </li>
        {% endfor %}
      </ul>
    {% endfor %}
  </div>
{% else %}
  <p>No tags yet.</p>
{% endif %}
