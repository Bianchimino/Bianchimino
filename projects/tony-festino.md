# Tony Festino

**Live:** _coming soon_ · **Code:** private

Website for Tony Festino, a party brand running club nights, house parties and private events in Rome and Milan. Built for the brand as a real client project, with a built-in admin so the team can run the site without a developer.

<!-- To add a screenshot: upload it to assets/tony-festino.png and put ![Screenshot](../assets/tony-festino.png) here -->

## What it does

- **Bilingual site (IT/EN):** every word in both languages, switched with a flag toggle that remembers the visitor's choice and defaults to Italian for Italian phones.
- **"Quando il prossimo tonyfestino?":** the brand's catchphrase from its LED sign runs as a full-width dot-matrix marquee, and the hero answers it with the next event and a live countdown.
- **Events:** a ticket-style next-event card with add-to-calendar, directions and share, plus upcoming and past events and a highlight section for the latest edition (photo background, guest count, DJs).
- **Media:** a photo gallery with albums and a lightbox, vertical video clips with tap-for-sound, and a video hero.
- **Live Instagram feed:** the latest posts and follower count, pulled from the Instagram API (directly with a token, or through a Behold JSON feed), with official post embeds as a fallback.
- **Private-party enquiries:** a form that sends the request straight to WhatsApp or copies it and opens the brand's Instagram DMs.
- **Admin panel:** owners edit every text, event, photo, video and setting in the browser and publish changes live; all content lives in a single JSON file.

## Highlights

- Content-driven architecture: the whole site renders from one `content.json`, so the admin, backups and deploys all work on the same file.
- Editorial night-poster design (condensed display type, dot-matrix LED font, neon red palette), reviewed and reworked at desktop and mobile breakpoints.
- No framework and no build step for the client: a single static page that deploys anywhere (Netlify, any static host).

## Stack

HTML · CSS · vanilla JavaScript · Instagram API · Behold · Python build script · Playwright for visual checks · built with Claude Code
