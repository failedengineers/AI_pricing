# AI Token Calculator

Live: [aipricing.ilovelabfile.in](https://aipricing.ilovelabfile.in)

Paste a prompt and see its token count plus API cost across six providers — OpenAI, Anthropic, Google Gemini, Perplexity, DeepSeek, and Grok. Pick a model per provider and the cost updates instantly.

## Features

- **Exact OpenAI token counts** — uses [js-tiktoken](https://github.com/dqbd/tiktoken) (the same tokenizer OpenAI's models use), loaded client-side
- **Estimated counts for other providers** — character-density based, since none of them publish a browser-usable tokenizer
- **Output-size presets** — Classification, RAG/Q&A, Chat reply, Full response, Long generation — or enter an exact output token count
- **Per-model cost cards** for all 6 providers, switchable via dropdown
- **Full rates table** and **FAQ**, generated from the same pricing data as the calculator
- Runs entirely in the browser — nothing typed into it is sent anywhere
- No build step, no dependencies beyond the CDN-loaded tokenizer

## Structure

```
index.html                      — main calculator, all 6 providers
openai-token-calculator.html    — OpenAI-focused landing page
claude-token-calculator.html    — Claude-focused landing page
gemini-token-calculator.html    — Gemini-focused landing page
robots.txt
sitemap.xml
```

Each HTML file is self-contained (CSS + JS inline) — no build tooling required. Deployed as-is on GitHub Pages.

## Updating pricing

All rates live in the `PRICING` object near the top of the `<script>` tag in each HTML file (per 1M tokens, USD). Update there — the provider cards, rates table, and footer are all generated from it automatically.

## Local development

Just open `index.html` in a browser. No server or build step needed.
