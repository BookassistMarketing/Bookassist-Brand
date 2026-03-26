# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

## Main Project

The primary project is **Direct Booking Health Score**, located at `~/Documents/GitHub/Directbookinghealthscore`. It's a hotel technology audit tool with AI-powered analysis via Google Gemini, PDF report generation, and multi-language support (EN/IT/ES).

## Commands

Run these from `~/Documents/GitHub/Directbookinghealthscore`:

```
npm run dev       # Start dev server on port 3000
npm run build     # Production build (outputs to dist/)
npm run lint      # TypeScript type-check (tsc --noEmit)
npm run preview   # Preview production build locally
npm run deploy    # Deploy to GitHub Pages (gh-pages)
```

## Architecture

**Stack:** React 19 + TypeScript + Vite + Tailwind CSS 4 + Google Gemini API

**Application state machine** (defined in `types.ts`, managed in `App.tsx`):
`WELCOME` → `QUIZ` → `ANALYZING` → `RESULTS`

**Key files:**

* `constants.ts` — All question definitions, translations (EN/IT/ES), and category configs
* `types.ts` — Core types: `AppState`, `Language`, `Question`, `Answer`, `AnalysisResult`
* `services/geminiService.ts` — Gemini API integration (Gemini Flash 3); API key read from env vars in priority order: `VITE_GEMINI_API_KEY`, `GEMINI_API_KEY`, `VITE_API_KEY`, `API_KEY`
* `contexts/ContentContext.tsx` — Global React Context for language/content state
* `App.tsx` — Top-level routing between app states, header, nav

**PDF export** uses html2canvas + jsPDF loaded via CDN (not npm), referenced in `index.html`.

**Deployment** targets GitHub Pages; the `vite.config.ts` sets the correct base path.

---

## Bookassist Skills

Custom skills are stored locally in `.claude/commands/`. Before starting any of the tasks below, always read the corresponding skill file in full — it contains the full instructions, workflow, and brand rules for that task.

| Task | Skill File | When to use |
|---|---|---|
| Write a blog post or article | `.claude/commands/article-creation.md` | Any request to write an article, blog post, or long-form content for Bookassist |
| Write an email or email campaign | `.claude/commands/email-creation.md` | Any request to draft an email, newsletter, campaign, or email copy for Bookassist |
| Create social media posts | `.claude/commands/social-media-posts.md` | Any request for social content across LinkedIn, Instagram, Facebook, or X |
| Translate content | `.claude/commands/translation-v3.md` | Any request to translate Bookassist content into ES, FR, IT, DE, CS, or PL |

**Important:** Do not attempt any of the above tasks from memory or general knowledge. Always read the skill file first. The skill files contain exact brand rules, workflows, output formats, and terminology that must be followed precisely.

---

## Bookassist Brand Guidelines

Always follow these brand guidelines when creating or editing any Bookassist content including social media posts, emails, blog posts, presentations, or any other marketing material.

### Colours

| Name | HEX | Notes |
|---|---|---|
| **Corporate 1** | `#45AEB1` | CMYK 75, 0, 30, 0 |
| **Corporate 2** | `#3B5772` | CMYK 100, 40, 0, 50 |
| **Light BG 1** | `#E5F2F2` | 10% Corp 1 |
| **Light BG 2** | `#D7EAEB` | 20% Corp 1 |
| **Light BG 3** | `#F9F9F9` | — |
| **Light BG 4** | `#9DABB8` | 50% Corp 2 |
| **Highlight 1** | `#F8CF56` | — |
| **Highlight 2** | `#FF8F1B` | — |

### Fonts

**Montserrat Extrabold** — Used for page headers and strong banner text only. Do not use other weights of Montserrat. The corporate logo "Bookassist" is a variation of Montserrat Extrabold.

**Roboto** — Used for all body text:
* Regular body text: Roboto Light
* Headings within text: Roboto Bold
* Emphasis: Roboto Light Italic
* Line spacing: 1 line or 0.9 lines
* Paragraph spacing: 1 line

### Key Terminology

Always use these terms consistently:

| Term | Guidance |
|---|---|
| **We make your bookings more profitable** | Repeat on every occasion and at every opportunity. Use at the end of any list of features or descriptions of strategy. |
| **Cost Per Acquisition (CPA)** | Always refer to the cost per acquisition, not just "the cost", "cost of booking", or "OTA cost". |
| **Customer Journey** | We base all our technology and strategy on optimising the customer journey — not just for one booking, but to make it repeatable and constantly evolving into a Perpetual Cycle of Growth. |
| **Perpetual Cycle of Growth** | We constantly refine the Customer Journey to turn it into a Perpetual Cycle of Growth. It's never about just one booking. |
| **Bookassist Ecosystem** | Shows how all products work together and rely on each other to deliver better conversion, higher ROI, and make your bookings more profitable. |
| **Suite, Digital Suite** | Our products work best together as a suite, or Digital Suite. Avoid using "group" or other collective terms. |
| **Omni-channel** | Refer to Digital Media as an omni-channel promotional service — not multi-channel. |
| **Personalisation** | Continually emphasise personalisation in Web Design and Booking Platform. |
| **Next generation, next-gen** | Refer to Web Design (WD) and Booking Platform (BP) as using next generation technology. |
| **Intelligently designed** | Emphasises that the front-end design and UI for Web and Booking Platform is deliberately thought about and is part of the product engineering approach. |

### Brand Voice & Tone

* **Personality:** Innovative, Sophisticated, Trustworthy
* **Tone:** Professional, Informative, Confident, Inspirational
* **Style:** Insight-driven, educational, data-oriented
* Avoid clichés, filler adjectives, and generic hospitality language
* All content in UK English (optimise, personalisation, colour, etc.)

### Bookassist Ecosystem

| Stage | Product | Purpose |
|---|---|---|
| ATTRACT | Digital Media (DM) | Drive visibility and traffic |
| ENGAGE | Web Design (WD) | Convert browsers into bookers |
| CONVERT | Booking Platform (BP) | Maximise direct bookings |
| REFINE | Bookassist Intelligence (BI) + CSM | Optimise performance continuously |

**Ancillary products:** GDS, Bookassist Vouchers (BV)

**Proven results for engaged clients:**
* Total CPA below 8%
* Digital Media ROI greater than 25:1
* Booking Platform CVR greater than 15%

### Untranslatable Acronyms

Always keep these in English regardless of language: `DM`, `WD`, `BP`, `BI`, `GDS`, `BV`, `CPA`, `ROI`, `CVR`, `CSM`, `OTA`
