---
layout: layouts/base.njk
title: Home
description: "Homepage del sito pubblico del condominio Via Calisina 9."
permalink: /
templateEngineOverride: njk,md
---
# Via Calisina 9

Benvenuti nel sito pubblico del condominio e comprensorio di Via Calisina 9. Questo spazio raccoglie informazioni essenziali, avvisi e documenti pubblici consultabili dai residenti.

<div class="section-links" aria-label="Sezioni principali">
  <a class="section-link" href="storia/">
    <span>Storia</span>
    <small>Una breve pagina dedicata alla memoria del comprensorio.</small>
  </a>
  <a class="section-link" href="avvisi/">
    <span>Avvisi</span>
    <small>Comunicazioni pubbliche ordinate dalla più recente.</small>
  </a>
  <a class="section-link" href="documenti/">
    <span>Documenti pubblici</span>
    <small>File consultabili senza accessi o registrazioni.</small>
  </a>
</div>

## Ultimi avvisi

{% if collections.avvisi | length %}
<ol class="notice-list compact-list">
{% for avviso in collections.avvisi %}
{% if loop.index <= 3 %}
  <li>
    <time datetime="{{ avviso.date | htmlDateString }}">{{ avviso.date | dateReadable }}</time>
    <h3><a href="{{ avviso.url | relativeUrl(page.url) }}">{{ avviso.data.title }}</a></h3>
    <p>{{ avviso.data.summary }}</p>
  </li>
{% endif %}
{% endfor %}
</ol>
{% else %}
<p>Non ci sono ancora avvisi pubblicati.</p>
{% endif %}

<p><a class="text-link" href="avvisi/">Vedi tutti gli avvisi</a></p>
