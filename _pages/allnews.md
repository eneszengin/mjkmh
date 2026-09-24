---
title: "MJKMH - Haberler"
layout: textlay
sitemap: false
permalink: /haberler/
---

# Haberler

{% for article in site.data.news %}
<p>{{ article.date }} <br> {{ article.headline | markdownify}}</p>
{% endfor %}
