---
layout: test
title: Sample Page
---

<nav id="nav2">
    <ul class="nav-list">
    {% for item in site.data.navigation %}
        <li class="nav-item"><a href="{{ item.link }}">{{ item.name }}</a>
        {% if item.subitems %}
            <ul class="nav-list">
                {% for subitem in item.subitems %}
                <li class="nav-item"><a href="{{ subitem.link }}">{{ subitem.name }}</a></li>
                {% endfor %}
            </ul>
        {% endif %}
        </li>
    {% endfor %}
    </ul>
</nav>
This is a sample to see how this is rendered if I browse to it via GitHub pages. I'm unsure if this is a good idea.

1. Numbered List
2. Numbered List
3. Numbered LIst

- Bulleted list
- Bulleted list


[Hyperlink](https://itsjason.net)

![image](/assets/images/IMG_0918.jpeg)

