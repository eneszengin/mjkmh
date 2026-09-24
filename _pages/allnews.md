---
title: "MJKMH - Haberler"
layout: textlay
sitemap: false
permalink: /haberler/
---

# Haberler

{% for article in site.data.news %}
<p>{% if article.date %}{{ article.date }}<br>{% endif %}{{ article.headline | markdownify}}</p>
{% endfor %}
