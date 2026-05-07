# Via Casilina 9 - sito condominiale

Sito statico pubblico del condominio e comprensorio di Via Casilina 9.

Repository ufficiale: <https://github.com/ViaCasilina9/sito-condominio.git>

Il sito usa Eleventy, contenuti Markdown, dati JSON, layout Nunjucks e CSS scritto a mano. Non usa WordPress, database, backend, analytics, Google Fonts, cookie di profilazione o risorse esterne obbligatorie.

## Requisiti

- Node.js LTS, versione 20 o successiva.
- npm.

## Installazione

```bash
npm install
```

## Sviluppo locale

```bash
npm run dev
```

Eleventy avvia un server locale e ricompila il sito quando cambiano i file in `src` o `public`.

## Build produzione

```bash
npm run build
```

Il sito statico finale viene generato nella cartella `dist`.

## Creare un nuovo avviso

Creare un file Markdown in `src/avvisi/`, per esempio `src/avvisi/nuovo-avviso.md`.

```md
---
layout: layouts/base.njk
title: Titolo avviso
description: "Descrizione breve della pagina."
date: 2026-05-20
summary: "Riepilogo mostrato nella lista avvisi."
tags: avvisi
---
# Titolo avviso

Testo dell'avviso.
```

Gli avvisi sono ordinati automaticamente per data decrescente. La homepage mostra gli ultimi tre.

## Aggiungere un documento pubblico

1. Caricare il file in `public/documenti/`.
2. Aggiungere una voce in `src/_data/documenti.json`.

```json
{
  "title": "Titolo documento",
  "date": "2026-05-20",
  "category": "Categoria",
  "file": "/documenti/nome-file.pdf"
}
```

Usare documenti pubblici privi di dati personali non necessari. I file placeholder `.txt` presenti nella repository possono essere sostituiti con PDF ufficiali.

## Deploy su GitHub Pages

Il workflow `.github/workflows/deploy.yml` pubblica il sito su GitHub Pages a ogni push su `main`.

Prima di usare il workflow, nelle impostazioni della repository GitHub:

1. Aprire `Settings`.
2. Aprire `Pages`.
3. Impostare `Build and deployment` su `GitHub Actions`.

Poi eseguire il normale flusso Git:

```bash
git status
git add .
git commit -m "Crea sito statico del condominio Via Casilina 9"
git push origin main
```

## Dominio custom

Per collegare un dominio personalizzato:

1. Configurare il dominio nelle impostazioni `Settings > Pages` della repository.
2. Aggiungere i record DNS richiesti da GitHub Pages presso il provider del dominio.
3. Se serve, aggiungere un file `public/CNAME` con il dominio, per esempio `www.esempio.it`.

Il sito usa link relativi, quindi può funzionare sia come pagina progetto, per esempio `https://viacasilina9.github.io/sito-condominio/`, sia con dominio custom.

## Privacy

Il sito è statico, non usa analytics, non usa cookie di profilazione e non contiene moduli di contatto.
