# College Soccer Hub

**Live:** _coming soon_ · **Code:** private (web app + scraper)

An ESPN-style platform dedicated to NCAA Men's Division I college soccer: scores, schedules, standings, rankings, teams and news in one place, plus an AI assistant you can ask about the season.

<!-- To add a screenshot: upload it to assets/college-soccer-hub.png and put ![Screenshot](../assets/college-soccer-hub.png) here -->

## What it does

- **Scores & schedule:** match results and upcoming fixtures.
- **Standings & rankings:** conference tables and national rankings, with charts.
- **Teams & news:** team pages and a news feed.
- **AI chat assistant:** a chat built on Google Gemini that answers questions about college soccer. Each answer is grounded in the site's own up-to-date database (matches, rankings, teams, news), so it doesn't invent results.

## How it works

```
 Scraper (scheduled)
        │  collects matches, rankings and teams
        ▼
 Secured ingestion API (Supabase Edge Functions)
        │  token-protected endpoints per data type
        ▼
 Postgres database ──► AI chat function (database context → Gemini, streamed reply)
        │
        ▼
 Web app (React + Vite)
```

## Stack

React 18 · Vite · TypeScript · Tailwind CSS · shadcn/ui · TanStack Query · Recharts · Supabase (Postgres, Edge Functions) · Google Gemini 2.5 Flash · Vitest & Playwright · built with Lovable
