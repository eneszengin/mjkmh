---
title: "MJKMH - Yayınlar"
layout: gridlay
sitemap: false
permalink: /yayinlar/
---

# Yayınlar

{% assign yillar = site.data.yayinlar | group_by: "year" %}
{% for yil in yillar %}
{% unless forloop.first %}<hr>{% endunless %}
<h2 class="kisi-bolum yayin-yil">{{ yil.name }}</h2>
<ul class="yayinlar">
{% for y in yil.items %}
<li>
<strong>{{ y.title }}</strong><br>
<em>{{ y.source }}</em> · {{ y.type }}{% if y.doi %} · <a href="https://doi.org/{{ y.doi }}">doi:{{ y.doi }}</a>{% endif %}<br>
<span class="danisman">{{ y.members | join: ", " }}</span>
</li>
{% endfor %}
</ul>
{% endfor %}
