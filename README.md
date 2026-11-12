# NebuLab

### An interactive product website for the Luna sleep mask

NebuLab’s website presents Luna through a cinematic product introduction, an interactive component walkthrough, and a dedicated scientific advisory board page. Built with Next.js, React, and TypeScript, the experience combines custom Canvas animation with responsive layouts and product storytelling.

![Luna sleep mask product imagery](public/slideshow-wake-better.webp)

## Experience

- **Animated starfield:** a custom Canvas scene with layered stars, nebula clouds, and pointer-driven parallax.
- **Product walkthrough:** a 180-frame image sequence that reveals the mask’s internal components, with interactive hotspots explaining each layer.
- **Touch-aware interactions:** adapted animation behavior and reduced frame loading on touch devices, with reduced-motion handling in the product sequence.
- **Product storytelling:** a visual slideshow introducing the project’s sleep, wake, and research themes.
- **Scientific advisory board:** interactive profile cards and a dedicated `/scientific-advisory-board` page.
- **Waitlist interface:** an early-access form with an in-page confirmation state.

## Technology

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
├── luna-mask-hero-video.mp4          Product hero video
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
