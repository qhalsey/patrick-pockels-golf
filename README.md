# Patrick Pockels Golf — v1 Site

Single-page marketing site for Patrick Pockels' private golf instruction business at Meadowlark Golf Course, Huntington Beach, CA.

## Stack
- **Astro 5** (static output) — real HTML for SEO, near-zero JS shipped
- **Tailwind v4** via `@tailwindcss/vite`
- **@astrojs/sitemap** — auto-generated sitemap-index.xml
- **Vercel** — auto-deploy on every push to `main`
- **Cloudflare** — domain + DNS (HTTPS cert handled automatically by Vercel)
- **Calendly** — booking (planned; current build ships a polished mock until Patrick sets up his account)

## Local development

```powershell
npm install
npm run dev      # http://localhost:4321
npm run build    # production build into dist/
npm run preview  # serve the dist/ output locally
```

## Project structure

```
src/
  layouts/Layout.astro      # html shell, meta tags, OG, JSON-LD LocalBusiness
  components/
    Nav.astro
    Hero.astro              # TODO: Patrick's headshot/course photo
    About.astro             # TODO: Patrick's headshot
    Services.astro          # $150 / $750 / $1000 pricing cards
    Testimonials.astro      # 1 real (Quentin), 2 placeholders
    Booking.astro           # Mock booking UI — swap for Calendly later
    Contact.astro
    Footer.astro
  pages/index.astro         # composes all sections
  styles/global.css         # @import "tailwindcss" + brand colors
public/
  robots.txt
  favicon.svg
```

## What changes when Patrick is ready

See **PATRICK_TODO.md** — 5 things Patrick personally owns (Calendly, photos, testimonials, Google Business Profile, reviews link).

## Deploy

See **DEPLOY.md** — step-by-step Vercel + Cloudflare wiring.

## Issue tracking

- Issue: https://github.com/qhalsey/patrick-pockels-golf/issues/1
