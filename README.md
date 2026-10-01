# sonnet-opus-sol-prompts

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude_Code-Sonnet_5.5_%7C_Opus_5.5-d97757)](https://docs.anthropic.com/en/docs/claude-code)
[![Codex CLI](https://img.shields.io/badge/Codex_CLI-GPT_6.1_Sol-10a37f)](https://github.com/openai/codex)

**sonnet-opus-sol-prompts** è una raccolta di quattro prompt che ti permette di replicare il confronto diretto fra Sonnet 5.5, Opus 5.5 e GPT 6.1 Sol, oppure di riutilizzarli nei tuoi progetti. Ogni prompt descrive un task completo a complessità crescente, eseguito dai tre modelli con lo stesso testo e lo stesso livello di effort.

---

## I quattro prompt

**1. 🎬 [Video in JavaScript](./prompts/prompt-01-terminal-vs-desktop.md)** — un video verticale di 18 secondi (1080×1920, 30 fps) generato interamente in codice su `<canvas>`, con colonna sonora via Web Audio API ed export in MP4. Soggetto: Claude Code da terminale e da applicazione desktop.

**2. 🧳 [Landing page](./prompts/prompt-02-group-travel-landing.md)** — la landing page di Wildpack, un brand inventato di viaggi di gruppo, con elenco dei viaggi filtrabile, flusso di prenotazione simulato e immagini generate con GPT Images 2.5.

**3. 🌍 [Globo 3D](./prompts/prompt-03-migration-globe.md)** — una visualizzazione 3D interattiva delle grandi migrazioni animali, con timeline dei dodici mesi, movimenti di camera per specie e un livello di dati integrato nella scena.

**4. 🕹️ [Videogioco arcade](./prompts/prompt-04-run-and-gun-arcade.md)** — un run-and-gun a scorrimento laterale in stile Metal Slug, in TypeScript e Canvas 2D, con sprite, animazioni e audio generati in codice, giocabile dalla schermata iniziale al boss finale.

---

## Prerequisiti

- **Claude Code** — per eseguire i prompt con Sonnet 5.5 e Opus 5.5.
- **Codex CLI** — per eseguire i prompt con GPT 6.1 Sol. I prompt 2 e 3 la richiedono anche con i modelli Anthropic, perché le immagini vengono generate con GPT Images 2.5 tramite l'abbonamento Codex.
- **Node.js e ffmpeg** — il prompt 1 produce uno script di export basato su Node, Playwright e ffmpeg; il prompt 4 produce un progetto Vite.

---

## Utilizzo

1. Crea una cartella vuota per ogni coppia modello-prompt, così gli output restano separati.
2. Avvia l'agente nella cartella, seleziona il modello e imposta l'effort su `high`.
3. Incolla il testo del prompt senza modifiche.

Per un confronto valido usa lo stesso prompt e lo stesso effort su tutti i modelli, e non intervenire durante l'esecuzione.

---

## Risultati del confronto

**Qualità dell'output** — classifica per esperimento, secondo la valutazione dell'autore:

- **Video in JavaScript** — Opus, Sol, Sonnet.
- **Landing page** — Sol, Opus, Sonnet.
- **Globo 3D** — Opus, Sol, Sonnet.
- **Videogioco arcade** — Opus, Sonnet, Sol.

**Costo** — il costo equivalente via API dei quattro task è stato di circa 4 $ con GPT 6.1 Sol, 65 $ con Opus 5.5 e 100 $ con Sonnet 5.5.

**Tempo** — per il videogioco Sol ha impiegato 75 minuti, Opus 113 e Sonnet 120.

---

## Struttura del progetto

```
prompts/
  prompt-01-terminal-vs-desktop.md
  prompt-02-group-travel-landing.md
  prompt-03-migration-globe.md
  prompt-04-run-and-gun-arcade.md
```

---

Designed by **[Dario Fontanel, PhD](https://dariofontanel.com/)**

*Aiuto PMI italiane ad integrare l'intelligenza artificiale per automatizzare i lavori ripetitivi, abbattere i costi e guadagnare tempo per crescere.*

[![Sito](https://img.shields.io/badge/Sito-dariofontanel.com-4285F4?style=flat&logo=googlechrome&logoColor=white)](https://dariofontanel.com/)
[![YouTube](https://img.shields.io/badge/YouTube-FF0000?style=flat&logo=youtube&logoColor=white)](https://www.youtube.com/@dariofontanel)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=flat&logo=instagram&logoColor=white)](https://www.instagram.com/dariofontanel.ai/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0yMC40NDcgMjAuNDUyaC0zLjU1NHYtNS41NjljMC0xLjMyOC0uMDI3LTMuMDM3LTEuODUyLTMuMDM3LTEuODUzIDAtMi4xMzYgMS40NDUtMi4xMzYgMi45Mzl2NS42NjdIOS4zNTFWOWgzLjQxNHYxLjU2MWguMDQ2Yy40NzctLjkgMS42MzctMS44NSAzLjM3LTEuODUgMy42MDEgMCA0LjI2NyAyLjM3IDQuMjY3IDUuNDU1djYuMjg2ek01LjMzNyA3LjQzM2MtMS4xNDQgMC0yLjA2My0uOTI2LTIuMDYzLTIuMDY1IDAtMS4xMzguOTItMi4wNjMgMi4wNjMtMi4wNjMgMS4xNCAwIDIuMDY0LjkyNSAyLjA2NCAyLjA2MyAwIDEuMTM5LS45MjUgMi4wNjUtMi4wNjQgMi4wNjV6bTEuNzgyIDEzLjAxOUgzLjU1NVY5aDMuNTY0djExLjQ1MnpNMjIuMjI1IDBIMS43NzFDLjc5MiAwIDAgLjc3NCAwIDEuNzI5djIwLjU0MkMwIDIzLjIyNy43OTIgMjQgMS43NzEgMjRoMjAuNDUxQzIzLjIgMjQgMjQgMjMuMjI3IDI0IDIyLjI3MVYxLjcyOUMyNCAuNzc0IDIzLjIgMCAyMi4yMjUgMHoiLz48L3N2Zz4%3D)](https://www.linkedin.com/in/dario-fontanel/)
[![TikTok](https://img.shields.io/badge/TikTok-000000?style=flat&logo=tiktok&logoColor=white)](https://www.tiktok.com/@dario.fontanel)
[![AI Academy](https://img.shields.io/badge/AI_Academy-E7514F?style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAzIDEgOWwxMSA2IDktNC45MVYxN2gyVjlMMTIgM3pNNSAxMy4xOFYxN2MwIDEuNjYgMy4xMyAzIDcgM3M3LTEuMzQgNy0zdi0zLjgybC03IDMuODItNy0zLjgyeiIvPjwvc3ZnPg%3D%3D)](https://www.skool.com/ai-academy-2306)

Licenza [MIT](./LICENSE).
