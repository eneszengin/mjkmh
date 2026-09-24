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
{% if site.yayin_detayli_yillar contains yil.name %}
<div class="row yayin-kutular">
{% for y in yil.items %}
<div class="col-sm-6 clearfix">
<div class="well yayin-kutu">
<pubtit>{{ y.title }}</pubtit>
<img src="{{ site.url }}{{ site.baseurl }}/images/{% if y.image %}yayinlar/{{ y.image }}{% else %}kisiler/fotograf-yok.png{% endif %}" class="img-responsive" width="33%" style="float: left" />
{% if y.abstract %}<p>{{ y.abstract }}</p>{% endif %}
<p><em>{{ y.source }}</em> · {{ y.type }}{% if y.quartile %} · <span class="quartile">{{ y.quartile }}</span>{% endif %}</p>
<p class="danisman">{{ y.members | join: ", " }}</p>
{% if y.doi %}<p><strong><a href="https://doi.org/{{ y.doi }}" target="_blank" rel="noopener">doi:{{ y.doi }}</a></strong></p>{% endif %}
</div>
</div>
{% cycle '', '<div class="clearfix hidden-xs"></div>' %}
{% endfor %}
</div>
{% else %}
<ul class="yayinlar">
{% for y in yil.items %}
<li>
<strong>{{ y.title }}</strong><br>
<em>{{ y.source }}</em> · {{ y.type }}{% if y.quartile %} · <span class="quartile">{{ y.quartile }}</span>{% endif %}{% if y.doi %} · <a href="https://doi.org/{{ y.doi }}" target="_blank" rel="noopener">doi:{{ y.doi }}</a>{% endif %}<br>
<span class="danisman">{{ y.members | join: ", " }}</span>
</li>
{% endfor %}
</ul>
{% endif %}
{% endfor %}
