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
      <h2><a href="#{{ tag_name | slugify }}">{{ tag_name }}</a> ({{ tag_posts | size }})</h2>
      <ul class="post-list">
        {% for post in tag_posts %}
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
    {% endfor %}
  </div>
{% else %}
  <p>No tags yet.</p>
{% endif %}
