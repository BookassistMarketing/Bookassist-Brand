# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Main Project

The primary project is **Direct Booking Health Score**, located at `~/Documents/GitHub/Directbookinghealthscore`. It's a hotel technology audit tool with AI-powered analysis via Google Gemini, PDF report generation, and multi-language support (EN/IT/ES).

## Commands

Run these from `~/Documents/GitHub/Directbookinghealthscore`:

```bash
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
- `constants.ts` — All question definitions, translations (EN/IT/ES), and category configs
- `types.ts` — Core types: `AppState`, `Language`, `Question`, `Answer`, `AnalysisResult`
- `services/geminiService.ts` — Gemini API integration (Gemini Flash 3); API key read from env vars in priority order: `VITE_GEMINI_API_KEY`, `GEMINI_API_KEY`, `VITE_API_KEY`, `API_KEY`
- `contexts/ContentContext.tsx` — Global React Context for language/content state
- `App.tsx` — Top-level routing between app states, header, nav

**PDF export** uses html2canvas + jsPDF loaded via CDN (not npm), referenced in `index.html`.

**Deployment** targets GitHub Pages; the `vite.config.ts` sets the correct base path.

## Bookassist Brand

The Bookassist brand assets and style guide are maintained at: https://github.com/BookassistMarketing/Bookassist-Brand

**Before creating or editing any of the following, always consult the Style Guide in the repo above:**
- Social media posts
- Emails
- Blog posts
- Any other marketing or brand content

The style guide covers approved colours, fonts, logos, and key terminology that must be used consistently across all Bookassist communications.
