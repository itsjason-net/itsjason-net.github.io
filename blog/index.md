---
layout: default
title: Blog
---

<section class="post-list">
  {% for post in site.posts %}
    {% unless post.hidden == true %}
      <article class="post-entry">
        <h3 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h3>
        <div class="post-metadata">
          <b>Posted on:</b> {{ post.date | date: '%B %d, %Y' }}<br />
          <b>Category:</b> <a href="/blog/categories#{{ post.category | url_encode }}">{{ post.category }}</a><br />
          <b>Tags:</b> {% for tag in post.tags -%}
            {%- if forloop.length > 0 -%}
              <a href="/blog/tags#{{ tag }}">{{ tag | replace: "+", " " }}</a>{% unless forloop.last %}, {% endunless -%}
          {%- endif -%}
        {% endfor %}
        </div>
        <div class="post-excerpt">
          {{ post.excerpt }}
        </div>
        <p><a href="{{ post.url }}">Read more ></a></p>
      </article>
    {% enduless %}
  {% endfor %}
</section>
