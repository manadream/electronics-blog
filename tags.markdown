---
layout: page
title: Tags
permalink: /tags/
---

{%- comment -%}
    Here we loop through all tags and create a tag cloud.
    `site.tags` is a Jekyll variable that contains all tags from all posts.
{%- endcomment -%}

{% if site.tags.size > 0 %}
  <ul class="tag-list">
    {% for tag in site.tags %}
      {% assign tag_name = tag | first %}
      {% assign tag_posts = tag | last %}
      <li>
        <a href="#{{ tag_name | slugify }}">{{ tag_name }}</a> ({{ tag_posts | size }})
      </li>
    {% endfor %}
  </ul>

  {%- comment -%}
    Next, we loop through all tags and display the posts for each tag.
  {%- endcomment -%}

  {% for tag in site.tags %}
    {% assign tag_name = tag | first %}
    {% assign tag_posts = tag | last %}
    <h2 id="{{ tag_name | slugify }}" class="tag-title">{{ tag_name }}</h2>
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
{% else %}
  <p>No tags yet.</p>
{% endif %}
