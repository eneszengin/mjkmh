---
title: "MJKMH - Hocalarımız"
layout: textlay
sitemap: false
permalink: /hocalarimiz/
---

# Hocalarımız

{% for hoca in site.data.hocalar %}
<div class="row hoca" markdown="0">
<div class="col-sm-12 clearfix">
{% if hoca.photo %}<img src="{{ site.url }}{{ site.baseurl }}/images/hocalar/{{ hoca.photo }}" class="img-responsive" width="20%" style="float: left; margin: 6px 22px 12px 0" />{% endif %}
<h3><strong>{{ hoca.name }} {{ hoca.surname }}</strong>{% if hoca.info %}, {{ hoca.info }}{% endif %}{% if hoca.born and hoca.died %} ({{ hoca.born }}–{{ hoca.died }}){% elsif hoca.born %} (d. {{ hoca.born }}){% endif %}</h3>
{% if hoca.bio %}{{ hoca.bio | markdownify }}{% endif %}
</div>
</div>
{% endfor %}
