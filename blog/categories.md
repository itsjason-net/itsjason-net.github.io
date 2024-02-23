---
layout: default
title: "Post Categories"
---

<section class="category-list">
    <ul>
    {% for category in site.categories %}
    {% unless category[0] == "blog" %}
        <li><a href="#{{ category[0] | url_encode }}">{{ category[0] }}</a></li>
    {% endunless %}
    {% endfor %}
    </ul>
    <div class="spacer">&nbsp;</div>
    {% for category in site.categories %}
    {% unless category[0] == "blog" %}
    <section class="category-entry">
        <h2 class="category-title" id="{{ category[0] | url_encode}}">{{ category[0] }}</h2>
        {% for post in category[1] %}
        {% unless post.draft == true %}
        <article class="post-entry">
            <h3 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h3>
            <div class="post-metadata">
                <b>Posted on:</b> {{ post.date | date: '%B %d, %Y' }}<br />
                <b>Tags:</b> {% for tag in post.tags -%}
                    {%- if forloop.length > 0 -%}
                        <a href="/blog/tags#{{ tag }}">{{ tag | replace: "+", " " }}</a>{% unless forloop.last %}, {% endunless -%}
                    {%- endif -%}
                {% endfor %}
            </div>
        </article>
        {% endunless %}
        {% endfor %}
    </section>
    {% endunless %}
    {% endfor %}
</section>
