---
layout: layouts/base.njk
title: Home
description: "Homepage del sito pubblico del condominio Via Calisina 9."
permalink: /
templateEngineOverride: njk,md
---
<div class="home-hero">
  <div class="home-hero__copy">
    <p class="eyebrow">Sito pubblico del condominio</p>
    <h1>Via Calisina 9</h1>
    <p class="lead">Uno spazio ordinato per avvisi, documenti pubblici e informazioni essenziali del condominio e comprensorio.</p>
    <div class="hero-actions" aria-label="Azioni principali">
      <a class="button-link" href="avvisi/">Consulta avvisi</a>
      <a class="text-link" href="documenti/">Documenti pubblici</a>
    </div>
  </div>
  <div class="home-hero__visual" aria-hidden="true">
    <div class="facade">
      <span></span><span></span><span></span>
      <span></span><span></span><span></span>
      <span></span><span></span><span></span>
    </div>
    <div class="courtyard"></div>
  </div>
</div>

<section class="section-links" aria-label="Sezioni principali">
  <a class="section-link" href="storia/">
    <span class="section-link__kicker">01</span>
    <span class="section-link__title">Storia</span>
    <small>Una breve pagina dedicata alla memoria del comprensorio.</small>
  </a>
  <a class="section-link" href="avvisi/">
    <span class="section-link__kicker">02</span>
    <span class="section-link__title">Avvisi</span>
    <small>Comunicazioni pubbliche ordinate dalla pi&ugrave; recente.</small>
  </a>
  <a class="section-link" href="documenti/">
    <span class="section-link__kicker">03</span>
    <span class="section-link__title">Documenti pubblici</span>
    <small>File consultabili senza accessi o registrazioni.</small>
  </a>
</section>

<section class="content-section latest-notices" aria-labelledby="ultimi-avvisi">
<h2 id="ultimi-avvisi">Ultimi avvisi</h2>

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
</section>
