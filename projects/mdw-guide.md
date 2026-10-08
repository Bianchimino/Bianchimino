# MDW Guide

**Live:** [mdw-guide.com](https://mdw-guide.com) · **Code:** private (web app + scraper)

A guide to Milan Design Week (Fuorisalone): hundreds of events across the city, made easy to browse, filter, map and plan into a personal itinerary.

<!-- To add a screenshot: upload it to assets/mdw-guide.png and put ![Screenshot](../assets/mdw-guide.png) here -->

## What it does

- **Event discovery:** about 850 events, each with its own page, filterable by date and by "vibe" (e.g. Hidden Gem, Tech, Luxury), with crowd-level badges.
- **Interactive map:** every event placed on a map of Milan by district.
- **Itinerary planner:** signed-in users save favourites, build day plans and view them on a map. Curated suggested itineraries are published by admins.
- **SEO:** per-event pages, FAQ content and a generated sitemap, so the site can be found on search engines.

## How it works

The project is two parts that only talk to each other over a secured API:

```
 Scraper (Python, GitHub Actions, runs daily)
        │  collects events from the official listing
        ▼
 Secured webhook (Supabase Edge Function)
        │  validates, deduplicates, inserts / updates events
        ▼
 Postgres database ──► Geocoding function (adds map coordinates)
        │
        ▼
 Web app (React + TanStack Start)
```

- **Scraper:** a headless browser (Playwright) walks the paginated event listing, extracts title, venue, dates, image, description and passport eligibility, and posts the batch to the app's API every night.
- **Ingestion:** an API-key-protected edge function upserts events by their official link, keeps existing data stable, and re-queues geocoding only when an event's address changes.
- **Geocoding:** a second function cleans the messy venue/address strings and turns them into coordinates for the map.
- **Data & auth:** Supabase Postgres with row-level security: user data (favourites, itineraries) is private to each user, events are public, and editing is limited to admins.

## Stack

React 19 · TanStack Start & Router · TypeScript · Tailwind CSS · Leaflet · Supabase (Postgres, Auth, Edge Functions) · Python · Playwright · BeautifulSoup · GitHub Actions · Cloudflare · built with Lovable and Claude Code
