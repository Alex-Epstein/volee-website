# Volee Website

The landing page for Volee, an iOS app that matches junior tennis players with opponents at their level and ranks them on local ladders.

Live at [voleeapp.com](https://voleeapp.com). Get the app on the [App Store](https://apps.apple.com/us/app/volee-app/id6762168017).

## About Volee

Volee is an iOS app I co-founded. Players get placed in a tier, find nearby opponents, play, and report scores. Ratings use Glicko-2. The app has 135+ users.

This repo holds only the marketing site. The app lives elsewhere.

## What's on the page

One scrolling page with a fixed nav bar. Sections in order:

| Section | Anchor | Content |
|---|---|---|
| Hero | `#home` | Headline, tagline, download button, quick stats (6 tiers, 3 match formats), and a phone mockup of the app's home screen built in HTML and CSS. |
| How It Works | `#how` | Four steps: build a profile, find your ladder, challenge and play, report the score. |
| Features | `#features` | Six cards: live ladder rankings, open and direct challenges, three match formats (Best of 3, Pro Set, Fast4), push notifications, family accounts, multi-city play. |
| Tiers | `#tiers` | The six tiers, from Orange Ball Recreational to Yellow Ball Competitive, and how seasons reset every four months. |
| For Clubs | `#clubs` | Pitch for club directors plus a contact form. |
| Download | `#download` | Call to action for the TestFlight beta and App Store waitlist. |
| Footer | | Product, club and legal links. |

A modal with a name and email form opens from the download buttons.

## How it works

It is a single static file, `public/index.html`. All CSS and JavaScript are inline. The only external request is Google Fonts (Bebas Neue, DM Sans, DM Serif Display).

The script does four things:

- Fades sections in as they scroll into view, using `IntersectionObserver`.
- Smooth-scrolls to each section from the nav links.
- Adds a shadow to the nav bar after you scroll.
- Handles the waitlist and club contact forms.

Both forms are front end only. They check the input and show a thank-you message. They do not send or store data anywhere yet. Connecting them to a form service or backend is the main open task.

## Run it locally

No build step and no dependencies. Open the file in a browser:

```bash
open public/index.html
```

Or serve the folder:

```bash
python3 -m http.server 8000 --directory public
```

Then visit http://localhost:8000.

## Deploy

voleeapp.com is served by Vercel. With no framework preset, Vercel serves the `public/` folder as the site root. To deploy your own copy, import the repo in Vercel or run `npx vercel` from the repo root.

Any static host works. Point it at `public/` as the publish directory.

## Repo layout

| Path | Purpose |
|---|---|
| `public/index.html` | The whole site: markup, styles and scripts. |
