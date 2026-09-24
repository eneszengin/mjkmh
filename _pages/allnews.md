---
title: "MJKMH - Haberler"
layout: textlay
sitemap: false
permalink: /haberler/
---

# Haberler

<div markdown="0">
{% for article in site.data.news %}
{% if article.date %}<p class="news-date">{{ article.date }}</p>{% endif %}
{{ article.headline | markdownify }}
{% endfor %}
</div>
