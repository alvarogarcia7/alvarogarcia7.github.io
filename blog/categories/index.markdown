---
layout: page
title: "categories"
footer: false
---

<ul>
{% assign categories = site.categories | sort %}
{% for item in categories %}
    <li><a href="/blog/categories/{{item[0]}}"}}/">{{ item[0] | capitalize }}</a> [ {{ item[1].size }} ]</li>
{% endfor %}
</ul>