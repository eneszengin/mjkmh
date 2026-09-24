---
title: "MJKMH - Team"
layout: gridlay
sitemap: false
permalink: /team/
---

# Çalışma grubu üyeleri

{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix team-member">
  <img src="{{ site.url }}{{ site.baseurl }}/images/kisiler/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
  <h4>{{ member.name }} {{ member.surname }}, {{ member.info }}</h4>
  <ul style="overflow: hidden">
  {% for line in member.education %}
  <li> {{ line | markdownify }} </li>
  {% endfor %}
  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}
