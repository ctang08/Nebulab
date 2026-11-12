# NebuLab

### Sleep technology that responds to you

NebuLab is developing an intelligent sleep mask that combines EEG sensing, adaptive processing, and gentle haptic feedback. The goal is to understand how you sleep and respond to your changing sleep stages—supporting more restorative nights and a gentler transition into the day.

The design brings brainwave sensing and timed feedback into a lightweight, light-blocking wearable. Rather than relying only on a fixed alarm, NebuLab is being built around a feedback loop: sense, interpret, and respond.

![NebuLab sleep mask product imagery](public/slideshow-wake-better.webp)

## What we’re building

- **Wake better:** use sleep-stage information to guide the timing of gentle wake-up cues.
- **Sleep deeper:** explore adaptive feedback designed to support restorative sleep.
- **See further:** develop a foundation for studying nightly patterns and potential sleep-related biomarkers.

These goals guide the product’s development, from its forehead EEG sensor and haptic modules to its overnight form factor.

## About this repository

This repository contains NebuLab’s public-facing product experience, built with Next.js, React, and TypeScript. It introduces the product, explains its component architecture, and presents the scientific advisory board.

### Website features

- **Animated starfield:** a custom Canvas scene with layered stars, nebula clouds, and pointer-driven parallax.
- **Product walkthrough:** a 180-frame image sequence that reveals the mask’s internal components, with interactive hotspots explaining each layer.
- **Touch-aware interactions:** adapted animation behavior and reduced frame loading on touch devices, with reduced-motion handling in the product sequence.
- **Product storytelling:** a visual slideshow introducing the project’s sleep, wake, and research themes.
- **Scientific advisory board:** interactive profile cards and a dedicated `/scientific-advisory-board` page.
- **Waitlist interface:** an early-access form with an in-page confirmation state.

## Website technology

| Layer | Implementation |
| --- | --- |
| Framework | Next.js 16 · App Router |
| UI | React 19 · TypeScript |
| Styling | Tailwind CSS 4 · custom CSS |
| Animation | Canvas API · `requestAnimationFrame` · image sequences |
| Assets | Local WebP images, product video, and advisor photography |
| Typography | Inter and Space Grotesk via `next/font/google` |

## Local development

Use Node.js 20.9 or newer and npm. A current Node.js LTS release is recommended.

```bash
git clone https://github.com/ctang08/Nebulab.git
cd Nebulab
npm ci
npm run dev
```

Open [localhost:3000](http://localhost:3000).

The current website does not require API keys or environment variables. Font loading during the build requires access to Google Fonts.

### Available commands

| Command | Purpose |
| --- | --- |
| `npm run dev` | Start the development server |
| `npm run build` | Create a production build |
| `npm start` | Serve the production build |
| `npm run lint` | Run ESLint |

To preview a production build locally:

```bash
npm run build
npm start
```

## Project structure

```text
src/app/
├── page.tsx                         Home route
├── layout.tsx                       Shared layout, fonts, and metadata
├── globals.css                      Site styles and responsive behavior
├── StarfieldPage.tsx                 Landing page and Canvas starfield
├── ScrollScrubVideo.tsx              Product sequence and component hotspots
├── ImageSlideshow.tsx                Product storytelling slides
├── SiteNav.tsx                       Navigation and early-access link
├── SplashScreen.tsx                  Introductory loading experience
├── WaitlistSection.tsx               Waitlist form and confirmation state
├── AdvisoryBoardSection.tsx          Reusable advisor cards
├── AdvisoryBoardPage.tsx             Advisory page composition
└── scientific-advisory-board/
    └── page.tsx                     Advisory board route

public/
├── frames/                          180-frame product animation
├── advisors/                        Advisor portraits
├── *.mp4                            Product hero video
├── nebulab-logo.png                 Brand asset
└── slideshow-*.webp                 Product slideshow imagery
```

## Working on the site

- Update the landing-page composition and starfield in `StarfieldPage.tsx`.
- Edit component descriptions and animation behavior in `ScrollScrubVideo.tsx`. Keep its frame count and filename convention aligned with `public/frames/`.
- Update slideshow content in `ImageSlideshow.tsx` and advisor profiles in `AdvisoryBoardSection.tsx`.
- Adjust shared colors, layouts, and responsive styles in `globals.css`.
- Configure page titles, descriptions, and fonts in `layout.tsx`.

## Current scope

This repository contains the product website and its visual assets. Device firmware, EEG processing, sleep-stage models, and hardware design files are maintained outside this codebase.

The waitlist currently updates local React state only: it does not submit, store, or send email addresses. A backend or mailing-list integration is needed before collecting real signups.
