# Infrastructure / Real Estate Website — PRD Template
**Version:** 1.0  
**Type:** Generic Reusable Template  
**Worked Example:** Aeroland (GMADA Township, Mohali)

---

## 1. Purpose

This PRD is a reusable blueprint for building a **real estate / infrastructure township marketing website**. It is designed to be handed to an AI coding assistant (e.g., Claude Code) which will:

1. Ask a series of intake questions to collect project-specific details.
2. Generate a fully functional, production-ready website with all content filled in.
3. Flag any section where it made assumptions, so you can review and correct before going live.

---

## 2. How to Use This PRD

1. Give this entire document to your AI coding assistant.
2. The AI will work through the **Intake Questionnaire** (Section 3) — asking one question at a time.
3. After all answers are collected, the AI builds the complete website.
4. The AI flags every assumption it made with a `⚠️ ASSUMPTION:` comment in the code.
5. Review flagged sections, correct as needed, then deploy.

---

## 3. Intake Questionnaire

> **AI Instruction:** Ask these questions **one at a time**, in order. Wait for the user's answer before proceeding to the next. Do not skip any question. After all questions are answered, confirm the full intake summary and ask "Shall I start building?" before writing any code.

| # | Question | Example Answer |
|---|----------|---------------|
| 1 | What is the **project name**? | Aeroland |
| 2 | What is the **authority or developer name**? (Government body or private developer) | GMADA (Greater Mohali Area Development Authority) |
| 3 | What is the **full location**? (Village/area, city, state, country) | Near Chandigarh International Airport, Mohali, Punjab, India |
| 4 | What is the **project type**? (township plots / apartments / villas / commercial / mixed) | Township Plots |
| 5 | What is the **one-line tagline**? | Where the Future Takes Flight |
| 6 | What is the **primary brand color**? (hex code or color name — used throughout the site) | Green (#15803d) |
| 7 | Who is the **target audience**? (investors / end-users / both) | Both — investors and plot buyers |
| 8 | List up to **4 key statistics** to display on the homepage. For each: label, value, unit/suffix, and a sublabel. | 5500+ Acres (GMADA Aerotropolis), ₹1878 Cr Bypass Investment, 300+ AI Companies (Expo City), 2 Pockets (A & B) |
| 9 | Which **optional pages** do you need? Answer yes/no for each: Media/News, Documents/PDF, Floor Plan, Payment Plan | Media: Yes, Docs: Yes, Floor Plan: Yes, Payment Plan: Yes |
| 10 | Is this a **bilingual website**? If yes, what is the second language? | Yes — Hindi |
| 11 | What is the **domain / base URL**? (for SEO canonical tags and OG metadata) | https://aeroland.co.in |
| 12 | What is the **primary contact phone number**? | +91-172-2228272 |
| 13 | What is the **contact email**? | info@gmada.gov.in |
| 14 | What is the **office address**? | GMADA Office, Sector 62, SAS Nagar, Mohali, Punjab — 160062 |
| 15 | What is the **WhatsApp number**? (for the floating contact button) | +91-78392-50007 |
| 16 | Is there a **RERA registration number**? If yes, provide it. | PBRERA-SAS79-PR1319 |
| 17 | Where do you want to **deploy**? (Vercel / Netlify / self-hosted VPS) | Vercel |
| 18 | What is your **GA4 Measurement ID**? (Google Analytics — type "skip" to add later) | G-XXXXXXXXXX |
| 19 | What is your **Meta Pixel ID**? (for Facebook/Instagram ads — type "skip" to add later) | 123456789 |
| 20 | What is your **Google Search Console verification code**? (type "skip" to add later) | abc123xyz |

---

## 4. Tech Stack (Locked)

All projects built from this PRD use the following stack. **Do not substitute.**

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 14 (App Router) |
| Language | TypeScript |
| Styling | Tailwind CSS |
| Animation | Framer Motion |
| Icons | React Icons |
| Font | Inter (Google Fonts via next/font) |
| Images | next/image (optimized) |
| Forms | Native HTML + API Route (no external form library) |
| Content | JSON files (one per language) |
| SEO | Next.js Metadata API + JSON-LD schema |
| Analytics | GA4 (next/script) + Meta Pixel (next/script) |
| Package manager | npm |

---

## 5. Site Architecture

### 5.1 Mandatory Pages (always built)

| Route | Page | Purpose |
|-------|------|---------|
| `/` | Home | Hero, stats, about preview, highlights preview, CTA |
| `/about` | About | Project description, vision, mission, authority details |
| `/highlights` | Highlights / Why Invest | 6 feature cards explaining investment value |
| `/location` | Location | Map embed, connectivity points, master plan image |
| `/contact` | Contact | Lead registration form + contact info |

### 5.2 Optional Pages (built only if answered "yes" in intake)

| Route | Page | Required intake data |
|-------|------|---------------------|
| `/media` | Media / News | News headlines, sources, dates, images |
| `/docs` | Documents | PDF file path or URL |
| `/floor-plan` | Floor Plan | Floor plan image, tower/unit details |
| `/payment-plan` | Payment Plan | BSP, construction schedule, charges table |

### 5.3 Mandatory Components (on every page)

| Component | Description |
|-----------|-------------|
| `Navbar` | Fixed top navbar, transparent on home hero / solid elsewhere. Contains all page links + language toggle (if bilingual). |
| `Footer` | Dark branded footer with quick links, legal links, social icons, copyright. |
| `SocialFloat` | Floating WhatsApp button (bottom-right), always visible. Uses WhatsApp number from intake. |

---

## 6. Page Specifications

### 6.1 Home Page (`/`)

**Sections (in order):**
1. **Hero** — Full-screen dark gradient background, project name, tagline, description, two CTA buttons ("Register Interest" → `/contact`, "Download Brochure" → `/docs` if exists else `/contact`).
2. **Stats Bar** — 4 animated counter cards from intake Q8.
3. **About Preview** — 2-column layout, text + authority badge. Links to `/about`.
4. **Highlights Preview** — 3-column grid of top 3 highlight cards. Links to `/highlights`.
5. **CTA Banner** — Full-width green gradient, "Register Your Interest" button.

### 6.2 About Page (`/about`)

**Sections:**
1. **Hero banner** — dark gradient, page title.
2. **Description** — AI-generated from project name, location, authority, type. ⚠️ FLAGGED FOR REVIEW.
3. **Vision & Mission** — Two cards side by side. ⚠️ FLAGGED FOR REVIEW.
4. **Authority info** — Name, notification number (if RERA provided).

### 6.3 Highlights Page (`/highlights`)

**Sections:**
1. **Hero banner**.
2. **6 feature cards** — AI generates 6 investment/project highlights based on project type, location, authority, and stats. ⚠️ ALL 6 FLAGGED FOR REVIEW.
3. **Bottom CTA**.

### 6.4 Location Page (`/location`)

**Sections:**
1. **Hero banner**.
2. **Connectivity list** — AI generates 5 location advantages based on address/area. ⚠️ FLAGGED FOR REVIEW.
3. **Master plan image** — placeholder if no image provided.
4. **Google Maps embed** — using the location from intake.

### 6.5 Contact Page (`/contact`)

**Sections:**
1. **Hero banner**.
2. **Lead form** — Full Name, Email, Phone, Message. Submits to `/api/register` (Next.js API route), saves to a JSON file or logs to console. ⚠️ AI flags if no DB/webhook is configured.
3. **Contact info card** — phone, email, address from intake.

### 6.6 Media Page (`/media`) — Optional

**Sections:**
1. **Hero banner**.
2. **News card grid** — AI generates placeholder headlines based on project. ⚠️ ALL HEADLINES FLAGGED FOR REVIEW. User replaces with real press coverage.

### 6.7 Documents Page (`/docs`) — Optional

**Sections:**
1. **Hero banner**.
2. **PDF embed** — inline iframe + download button. Requires PDF placed at `/public/assets/[project-name].pdf`.
3. **Summary card** — AI-generated project document summary. ⚠️ FLAGGED FOR REVIEW.

### 6.8 Floor Plan Page (`/floor-plan`) — Optional

**Intake required:** Floor plan image path, tower names, unit types, floor range.

**Sections:**
1. **Hero banner**.
2. **Spec chips** — type, towers, floors, units per floor.
3. **Full-width image** — from `/public/floor-plan/floor-plan.jpg`.
4. **Download button** + RERA badge.

### 6.9 Payment Plan Page (`/payment-plan`) — Optional

**Intake required:** BSP, unit size, unit type, construction milestone schedule, other charges.

**Sections:**
1. **Hero banner**.
2. **Summary chips** — unit type, size, BSP.
3. **Construction Linked Payment table**.
4. **Down Payment table** (if applicable).
5. **Other Charges grid**.
6. **Notes** (legal disclaimers).
7. **Contact strip** + download button.

---

## 7. Content System

### 7.1 Structure

All user-facing text lives in JSON files under `src/data/`:

```
src/data/
  content.en.json     ← English (primary)
  content.hi.json     ← Second language (only if bilingual = yes)
```

The Hindi (or second-language) file is typed `as typeof en` in TypeScript.

### 7.2 Content Generation Rules (Hybrid — per Section 8 decision)

- AI **auto-generates** all copy from the intake answers.
- Every AI-generated text block gets a `// ⚠️ ASSUMPTION: [reason]` comment above it in the JSON file.
- AI produces a **flagged sections summary** at the end of the build — a numbered list of every assumption made, so the user can review them in one place.
- Factual data (stats, contact info, RERA, WhatsApp, URLs) is **never assumed** — always taken verbatim from intake answers.

---

## 8. Content JSON Schema

```json
{
  "nav": {
    "home": "string",
    "about": "string",
    "highlights": "string",
    "location": "string",
    "contact": "string",
    "media": "string",          // only if media page = yes
    "docs": "string",           // only if docs page = yes
    "floor_plan": "string",     // only if floor plan page = yes
    "payment_plan": "string"    // only if payment plan page = yes
  },
  "hero": {
    "badge": "string",
    "title": "string",
    "subtitle": "string",
    "description": "string",
    "cta_primary": "string",
    "cta_secondary": "string"
  },
  "stats": [
    { "value": number, "prefix": "string?", "suffix": "string", "label": "string", "sublabel": "string" }
  ],
  "about": { "badge": "string", "title": "string", "description": "string", "overview": "string", "vision_title": "string", "vision": "string", "mission_title": "string", "mission": "string", "authority": "string", "notification": "string" },
  "highlights": {
    "badge": "string", "title": "string",
    "features": [{ "icon": "string", "title": "string", "description": "string" }]
  },
  "location": { "badge": "string", "title": "string", "description": "string", "masterplan_title": "string", "masterplan_description": "string", "map_title": "string", "highlights": ["string"] },
  "contact": { "badge": "string", "title": "string", "description": "string", "form": { "name": "string", "email": "string", "phone": "string", "message": "string", "message_placeholder": "string", "submit": "string", "success": "string" }, "info": { "authority": "string", "address": "string", "email": "string", "phone": "string" } },
  "footer": { "tagline": "string", "links": { "title": "string", "items": ["string"] }, "legal": { "title": "string", "items": ["string"] }, "copyright": "string" }
}
```

Optional sections (`media`, `docs`, `floor_plan`, `payment_plan`) are added to this schema only when the corresponding page is enabled.

---

## 9. Navbar Behaviour

- **Transparent with white text** — only on the home page at scroll position 0.
- **White / frosted with dark text** — on all other pages, and on home when scrolled past 20px.
- Controlled by: `const dark = scrolled || !isHome` in `Navbar.tsx`.
- If a new full-screen hero page is added, update this logic accordingly.
- Mobile: hamburger menu opens a dark green drawer with all links.
- Language toggle button: visible only if bilingual = yes.

---

## 10. CSS Utilities (`globals.css`)

The following utility classes must be defined and used consistently:

| Class | Definition |
|-------|-----------|
| `.gradient-green` | Dark diagonal green gradient — used on all hero banners |
| `.gradient-green-light` | Pale green — used for CTA sections |
| `.section-padding` | `py-20 px-4 md:px-8 lg:px-16` |
| `.container-max` | `max-w-7xl mx-auto` |
| `.badge` | Light green pill for section labels on white backgrounds |
| `.page-hero-badge` | Semi-transparent pill for labels on dark hero banners |

**Critical:** Every non-home page must wrap content in `<div className="pt-16">` to clear the fixed 64px navbar.

---

## 11. SEO Specification (Mandatory)

### 11.1 Per-Page Metadata

Every page exports a `metadata` object with:
- `title` — optimized for primary keyword + project name
- `description` — 150–160 characters, includes location + authority + CTA phrase
- `keywords` — 8–10 keywords
- `alternates.canonical` — full URL
- `openGraph` — title, description, URL, image (`/og-image.jpg`, 1200×630)
- `twitter` — card: summary_large_image

### 11.2 Root Layout Metadata

`layout.tsx` exports site-wide defaults:
- `metadataBase` — from intake domain
- `title.template` — `'%s | [PROJECT_NAME]'`
- `robots` — index: true, follow: true
- `verification.google` — from intake GSC code

### 11.3 JSON-LD Schema

Two schema blocks in `layout.tsx` via `next/script`:
- `Organization` — name, URL, logo, address, contactPoint
- `RealEstateListing` — name, description, URL, location (with GeoCoordinates ⚠️ AI flags lat/lng for review)

### 11.4 Sitemap & Robots

- `/robots.txt` — auto-generated via Next.js App Router
- `/sitemap.xml` — auto-generated, includes all enabled pages

---

## 12. Analytics Specification (Mandatory)

### 12.1 Google Analytics 4

- GA4 script loaded via `next/script` with `strategy="afterInteractive"` in `layout.tsx`.
- Uses Measurement ID from intake Q18.
- If skipped, leave a clearly marked `TODO` comment.

### 12.2 Google Search Console

- Verification meta tag injected via `metadata.verification.google` in `layout.tsx`.
- Uses code from intake Q20.

### 12.3 Meta Pixel

- Meta Pixel script loaded via `next/script` with `strategy="afterInteractive"` in `layout.tsx`.
- Uses Pixel ID from intake Q19.
- If skipped, leave a clearly marked `TODO` comment.

### 12.4 WhatsApp Click Tracking

- The `SocialFloat` WhatsApp button fires a GA4 event on click: `{ event: 'whatsapp_click', project: '[PROJECT_NAME]' }`.

---

## 13. SocialFloat Component (Mandatory)

Fixed floating button, bottom-right corner, visible on all pages.

**Behaviour:**
- Links to `https://wa.me/[WHATSAPP_NUMBER]?text=I'm interested in [PROJECT_NAME]`
- Opens in new tab
- Fires GA4 event on click (see Section 12.4)
- Z-index above all content
- Pulse animation to draw attention

---

## 14. Form & Lead Capture

**Route:** `/api/register` (Next.js API Route)

**Accepts:** `POST { name, email, phone, message }`

**Behaviour (in order of preference — AI picks first available):**
1. If a webhook URL is provided during intake → POST to webhook (e.g., Zapier, Make, Google Sheets).
2. If no webhook → append lead to a local `leads.json` file in the project root.
3. Always return `{ success: true }` to the client on success.

**Validation:**
- Server-side: name (required), phone (required, 10 digits), email (valid format).
- Client-side: same rules with inline error messages.

---

## 15. Bilingual System (Optional)

**Activated when:** intake Q10 = yes.

**Implementation:**
- `src/context/LanguageContext.tsx` — provides `{ t, language, setLanguage }` via React context.
- `useLanguage()` hook used in every component that renders text.
- Second language JSON cast `as typeof en` for TypeScript type safety.
- Language toggle button in navbar (desktop + mobile drawer).
- Default language: English (or primary language).
- Language preference stored in `localStorage`.

**AI Instruction:** When bilingual is enabled, generate the second-language JSON with accurate translations (not placeholders). Flag any translation that might need review with `⚠️`.

---

## 16. Deployment

### 16.1 Vercel

```bash
npm i -g vercel
vercel login
vercel --prod
```

Set environment variables in Vercel dashboard if any API keys are used.

### 16.2 Netlify

```bash
npm run build
# Upload /out directory to Netlify, or connect GitHub repo
# Set build command: npm run build
# Set publish directory: .next
# Install Netlify Next.js plugin: @netlify/plugin-nextjs
```

### 16.3 Self-hosted VPS

```bash
npm run build
npm start   # runs on port 3000
# Use nginx as reverse proxy, certbot for SSL
```

---

## 17. File Structure

```
[project-root]/
├── public/
│   ├── assets/
│   │   ├── [project].pdf          # official documents (if docs page enabled)
│   │   ├── news1.jpg – news5.jpg  # press images (if media page enabled)
│   │   └── og-image.jpg           # 1200×630 OG image (REQUIRED)
│   ├── floor-plan/
│   │   └── floor-plan.jpg         # (if floor plan page enabled)
│   └── payment_plan/
│       └── payment-plan.jpg       # (if payment plan page enabled)
├── src/
│   ├── app/
│   │   ├── layout.tsx             # root layout, metadata, analytics scripts
│   │   ├── globals.css            # utility classes
│   │   ├── page.tsx               # home page
│   │   ├── about/
│   │   ├── highlights/
│   │   ├── location/
│   │   ├── contact/
│   │   ├── media/                 # optional
│   │   ├── docs/                  # optional
│   │   ├── floor-plan/            # optional
│   │   ├── payment-plan/          # optional
│   │   └── api/
│   │       └── register/
│   │           └── route.ts       # lead capture API
│   ├── components/
│   │   ├── Navbar.tsx
│   │   ├── Footer.tsx
│   │   └── SocialFloat.tsx
│   ├── context/
│   │   └── LanguageContext.tsx    # only if bilingual = yes
│   └── data/
│       ├── content.en.json
│       └── content.hi.json        # only if bilingual = yes
├── CLAUDE.md                      # AI instructions for this codebase
├── package.json
├── tailwind.config.ts
├── tsconfig.json
└── next.config.js
```

---

## 18. CLAUDE.md Template

Every project built from this PRD must include a `CLAUDE.md` with the following content (filled in for the specific project):

```markdown
# CLAUDE.md

## Commands
\`\`\`bash
npm run dev      # Start dev server at http://localhost:3000
npm run build    # Production build (run to catch type/lint errors)
npm start        # Serve production build locally
\`\`\`

## Architecture
Next.js 14 App Router with Tailwind CSS, Framer Motion, and [bilingual system if applicable].

### Content system
All user-facing text lives in src/data/content.en.json [and content.[LANG].json].
Never hardcode user-facing strings in components.

### Page structure pattern
Every non-home page:
\`\`\`tsx
<div className="pt-16">        {/* clears fixed 64px navbar */}
  <div className="gradient-green ...">   {/* hero banner */}
  <section className="section-padding bg-white">  {/* main content */}
\`\`\`

### Key project facts
- Project: [PROJECT_NAME]
- Authority: [AUTHORITY]
- Location: [LOCATION]
- RERA: [RERA_NUMBER]
```

---

## 19. Commands Reference

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Production build (always run before considering work done)
npm run build

# Serve production build locally
npm start

# Deploy to Vercel
vercel --prod

# Type-check only
npx tsc --noEmit
```

---

## 20. Assumptions Flagging — AI Output Format

At the end of every build, the AI must output a **Flagged Sections Report** in this format:

```
⚠️ FLAGGED SECTIONS — Please review before going live:

1. [About Page] Description paragraph — AI-generated from project type and location. Verify factual accuracy.
2. [Highlights] All 6 feature cards — AI-generated. Replace with actual project USPs.
3. [Location] Connectivity list — AI-generated from address. Verify distances and landmarks.
4. [Schema] GeoCoordinates (lat/lng) — AI estimated from city name. Replace with exact coordinates.
5. [Media] All news headlines — placeholder content. Replace with real press coverage.
[... and so on]
```

---

## 21. Worked Example — Aeroland (GMADA Township, Mohali)

This PRD was used to build **aeroland.co.in** — a GMADA township marketing site near Chandigarh International Airport.

**Intake answers used:**

| # | Answer |
|---|--------|
| 1 | Aeroland |
| 2 | GMADA (Greater Mohali Area Development Authority) |
| 3 | Near Chandigarh International Airport, Mohali, Punjab, India |
| 4 | Township Plots |
| 5 | Where the Future Takes Flight |
| 6 | Green (#15803d) |
| 7 | Both — investors and plot buyers |
| 8 | 5500+ Acres (GMADA Aerotropolis), ₹1878 Cr (6-Lane Zirakpur Bypass), 300+ AI Companies (Expo City), 2 Pockets (A & B) |
| 9 | Media: Yes, Docs: Yes, Floor Plan: Yes, Payment Plan: Yes |
| 10 | Yes — Hindi |
| 11 | https://aeroland.co.in |
| 12 | +91-172-2228272 |
| 13 | info@gmada.gov.in |
| 14 | GMADA Office, Sector 62, SAS Nagar, Mohali, Punjab — 160062 |
| 15 | +91-78392-50007 |
| 16 | PBRERA-SAS79-PR1319 |
| 17 | Vercel |
| 18 | (to be configured) |
| 19 | (to be configured) |
| 20 | (to be configured) |

**GitHub repo:** https://github.com/kunalgupta91/aeroland_web  
**Live site:** https://aeroland.co.in

---

*PRD Version 1.0 — Generated from the Aeroland project — May 2026*
