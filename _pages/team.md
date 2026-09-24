---
title: "MJKMH - Kişiler"
layout: gridlay
sitemap: false
permalink: /kisiler/
---

# Kişiler

{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix team-member">
  <img src="{{ site.url }}{{ site.baseurl }}/images/kisiler/{{ member.photo | default: 'fotograf-yok.png' }}" class="img-responsive" width="25%" style="float: left" />
  <h4>{{ member.name }} {{ member.surname }}, {{ member.info }}</h4>
  <ul style="overflow: hidden">
  {% for edu in member.education %}
  <li>{{ edu.level }}: {{ edu.university }}{% if site.team_show_department and edu.department %}, {{ edu.department }}{% endif %}{% if site.team_show_years and edu.years %}, {{ edu.years }}{% endif %}</li>
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

{% assign bolumler = "lisansustu:Doktora ve Yüksek Lisans Öğrencileri,lisans:Lisans Öğrencileri,misafir:Misafir Araştırmacılar" | split: "," %}
{% for bolum in bolumler %}
{% assign parca = bolum | split: ":" %}
<h2 class="kisi-bolum">{{ parca[1] }}</h2>
<ul class="ogrenciler">
{% for kisi in site.data.ogrenciler[parca[0]] %}
<li>{{ kisi.name }} {{ kisi.surname }}{% if kisi.info %}, {{ kisi.info }}{% endif %}</li>
{% endfor %}
</ul>
{% endfor %}

<h2 class="kisi-bolum" id="mezunlar">Mezunlar</h2>

{% assign gruplar = "doktora:Doktora,yuksek_lisans:Yüksek Lisans,lisans:Lisans" | split: "," %}
{% for grup in gruplar %}
{% assign parca = grup | split: ":" %}
<h3 class="kisi-bolum">{{ parca[1] }}</h3>
<ul class="mezunlar">
{% for kisi in site.data.mezunlar[parca[0]] %}
<li>{{ kisi.name }} {{ kisi.surname }}{% if kisi.year %}, {{ kisi.year }}{% endif %}</li>
{% endfor %}
</ul>
{% endfor %}
