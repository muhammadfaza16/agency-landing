# PROMPT — Solo Software House Landing Page
> Lempar ke Claude Code / Opus as-is. Edit bagian [CAPS] sesuai kebutuhan lo.

---

## CONTEXT & GOAL

Build a production-ready company profile / landing page for a solo software house.
The owner is a solo developer who uses AI-assisted (vibe coding) workflows to deliver
fast, high-quality software products. The site must be optimized for SEO from day one.

**Framework:** Astro (preferred for landing page — best Lighthouse score, minimal JS)
**Styling:** Tailwind CSS v4
**Deployment target:** Vercel or Netlify
**Language:** Indonesian (Bahasa Indonesia) with English technical terms as-is

---

## TECH STACK — DO NOT DEVIATE

```
astro@latest
@astrojs/tailwind
@astrojs/sitemap
@astrojs/image (or astro built-in Image component)
astro-seo (for <SEO> component)
schema-dts (for JSON-LD structured data)
```

No React unless strictly needed for an interactive island. Prefer Astro components.

---

## PROJECT STRUCTURE

```
/
├── public/
│   ├── favicon.svg
│   ├── og-image.jpg          # 1200x630 Open Graph image
│   └── robots.txt
├── src/
│   ├── components/
│   │   ├── Nav.astro
│   │   ├── Hero.astro
│   │   ├── Ticker.astro
│   │   ├── About.astro
│   │   ├── Services.astro
│   │   ├── Works.astro
│   │   ├── Pricing.astro
│   │   ├── Testimonials.astro
│   │   ├── FAQ.astro          # interactive island, use Astro + vanilla JS
│   │   ├── CTA.astro
│   │   └── Footer.astro
│   ├── layouts/
│   │   └── BaseLayout.astro   # handles <head>, SEO, JSON-LD
│   ├── pages/
│   │   ├── index.astro
│   │   └── 404.astro
│   └── data/
│       ├── services.ts
│       ├── works.ts
│       ├── testimonials.ts
│       └── faqs.ts
├── astro.config.mjs
└── tailwind.config.mjs
```

---

## DESIGN SYSTEM

### Color Palette (CSS variables in global.css)
```css
:root {
  --bg: #0A0A08;
  --bg2: #111110;
  --bg3: #1A1A17;
  --fg: #F0EEE6;
  --fg2: #A8A59A;
  --fg3: #5C5A54;
  --accent: #C8FF00;       /* acid green — primary CTA */
  --accent2: #FF6B35;      /* orange — secondary accent */
  --border: rgba(240,238,230,0.08);
  --border2: rgba(240,238,230,0.15);
}
```

### Typography
```
--font-display: 'Syne', sans-serif      (headings, nav, labels)
--font-serif: 'Instrument Serif', serif  (italic accents in h1/h2)
--font-mono: 'DM Mono', monospace        (tags, section labels, prices)
```
Load from Google Fonts in `<head>`. Preconnect to fonts.googleapis.com.

### Design Rules
- Dark theme throughout, no light mode
- Section labels: `// 001 — Label` format, font-mono, color: var(--accent), uppercase, small
- H1: clamp(3rem, 5vw, 5.5rem), font-weight 800, letter-spacing -0.03em, line-height 1
- H2: clamp(2rem, 3.5vw, 3.5rem), same weight/tracking
- Italic accents in headings use `<em>` with Instrument Serif
- Borders: 0.5px solid var(--border) — never 1px
- No border-radius on most elements (sharp corners = intentional)
- CTA buttons: sharp rectangle, no border-radius, font-mono
- Primary button: bg var(--accent), color #0A0A08
- Ghost button: transparent, border 0.5px var(--border2), color var(--fg2)

---

## PAGE SECTIONS — FULL SPEC

### 1. NAV
- Fixed top, backdrop-filter blur(12px), border-bottom 0.5px var(--border)
- Logo: "KD." — KD in var(--fg), dot in var(--accent), font-display weight 800
- Links: About / Services / Works / Pricing — uppercase, letter-spacing 0.1em, font-size 0.78rem
- CTA button: "Mulai Proyek →" — primary button style
- Smooth scroll to sections via anchor links

### 2. HERO
- Full viewport height, padding-top for nav offset
- Two-column grid: left = copy, right = stat cards
- Left:
  - Availability badge: animated green dot + "Available for project — [YEAR]"
  - H1: "Software<br><em>built fast,</em><br>shipped real."
  - Subtext: solo developer, AI-assisted, produk nyata bukan prototipe
  - Two buttons: primary "Cerita dulu →" + ghost "Lihat portofolio"
- Right: 4 stat cards showing:
  - Delivery time: "3–6 minggu"
  - Projects delivered: "24+"
  - Tech stack tags: Next.js, React, Supabase, Python, FastAPI, Vercel, Tailwind, Claude API
  - Availability status with animated pulse dot

### 3. TICKER / MARQUEE
- Full-width horizontal scrolling ticker
- Items: Web App · Mobile App · AI Integration · Landing Page · Dashboard · E-Commerce · SaaS MVP · Internal Tool · API Backend
- CSS animation only (no JS), seamless loop by doubling the content
- Separated by "✦" in var(--accent)
- Font-mono, uppercase, var(--fg3), font-size 0.72rem

### 4. ABOUT / THE DEAL
- Two columns: left = copy, right = process steps
- Section tag: "// 001 — The deal"
- H2: "Bukan agency.<br><em>Bukan freelancer.</em><br>Sesuatu di antaranya."
- Copy: explain solo + AI = small team output, direct communication, real products fast
- Right: numbered process list (01–04) with thin borders:
  01. Discovery call (1 jam)
  02. Scope + Proposal (2–3 hari)
  03. Build & Iterate
  04. Launch + Handoff

### 5. SERVICES
- Section tag: "// 002 — Services"
- 3x2 grid with shared borders (0.5px var(--border)), no gaps
- Each card: icon (emoji), service name, description, tech stack tags
- Services to include:
  1. Web App & SaaS MVP — Next.js, Supabase, Stripe
  2. AI Feature Integration — Claude API, OpenAI, RAG
  3. Landing Page & Marketing Site — Next.js, Framer, Webflow
  4. Internal Tool & Dashboard — React, PostgreSQL, Recharts
  5. API & Backend Service — FastAPI, Node.js, Supabase
  6. E-Commerce Custom — Next.js, Midtrans, Xendit
- Card hover: background shifts to var(--bg2)

### 6. WORKS / PORTFOLIO
- Section tag: "// 003 — Selected works"
- H2: "Yang sudah<br><em>dikapalkan.</em>"
- 2x2 grid of project cards
- Each card: mock thumbnail area, category, title, description, result metric, arrow link
- Projects:
  1. Sistem Absensi & Payroll — HR Tech, 3 minggu, 80+ pengguna aktif
  2. AI Customer Service — E-Commerce chatbot, kurangi tiket CS 60%
  3. Landing Page Perumahan + Booking — Properti, 12 hari, conversion 8%
  4. POS & Manajemen Stok — F&B, 4 minggu, 5 cabang
- Arrow (↗) animates on hover: translate(3px, -3px)

### 7. PRICING
- Section tag: "// 004 — Pricing"
- H2: "Harga yang<br><em>gue pasang.</em>"
- 3 columns with shared borders:
  1. Starter: Rp 8–15jt/proyek — landing page, 1–2 minggu
  2. Build (featured): Rp 20–50jt/proyek — full-stack web app, 3–6 minggu
     - Top border: 2px solid var(--accent) instead of 0.5px
     - Badge: "Paling sering dipilih" in var(--accent) bg, color #0A0A08
  3. Retainer: Rp 10jt/bulan — 40 jam/bulan, min 3 bulan
- Each has: tier label, price, description, feature list with "→" bullets, CTA button
- Featured card button: primary style, others: ghost

### 8. TESTIMONIALS
- Section tag: "// 005 — Kata mereka"
- H2: "Yang bilang<br><em>beneran kerja.</em>"
- 3-column grid of testimonial cards (bg var(--bg2), border 0.5px var(--border))
- Each: star rating, italic quote (Instrument Serif), avatar initials circle, name + role
- 3 testimonials from: Fintech Founder, F&B Owner, Properti COO

### 9. FAQ
- Section tag: "// 006 — FAQ"
- Max-width 800px, centered
- Accordion — one open at a time, vanilla JS (no framework)
- "+" icon rotates 45deg to "×" when open
- Questions:
  1. Vibe coding itu kualitasnya bisa dipercaya?
  2. Gimana kalau lo sakit atau ada halangan?
  3. Kode-nya gue punya setelah proyek selesai?
  4. Bisa minta revisi setelah launch?
  5. Bisa handle proyek dari luar kota?

### 10. CTA SECTION
- Full-width, bg var(--bg2), border-top and bottom
- Center aligned: section label + H2 + subtext + email input + submit button
- H2: "Punya ide?<br><em>Kita bikin nyata.</em>"
- Email input + "Kirim →" button in a row
- Input: bg var(--bg), border 0.5px var(--border2), focus border var(--accent)
- On submit: show confirmation state (no backend needed, just UI feedback)

### 11. FOOTER
- Simple single row: logo | "© [YEAR] — Solo, tapi serius." | links (LinkedIn, GitHub, WhatsApp)
- Max-width 1200px, centered

---

## SEO — IMPLEMENT ALL OF THESE

### BaseLayout.astro — Meta tags
```astro
---
import { SEO } from 'astro-seo';
const {
  title = '[YOUR NAME] — Solo Software House',
  description = 'Software house satu orang. Web app, SaaS MVP, dan AI integration dengan delivery 3–6 minggu. Vibe coding meets production quality.',
  ogImage = '/og-image.jpg',
  canonical = Astro.url.href,
} = Astro.props;
---
<SEO
  title={title}
  description={description}
  openGraph={{
    basic: {
      title: title,
      type: 'website',
      image: ogImage,
      url: canonical,
    },
    optional: {
      locale: 'id_ID',
      siteName: '[YOUR NAME] — Solo Software House',
    },
  }}
  twitter={{
    card: 'summary_large_image',
    creator: '@[YOUR_HANDLE]',
  }}
  extend={{
    link: [{ rel: 'canonical', href: canonical }],
    meta: [
      { name: 'robots', content: 'index, follow' },
      { name: 'author', content: '[YOUR NAME]' },
      { name: 'geo.region', content: 'ID-JT' },
      { name: 'geo.placename', content: 'Semarang' },
    ],
  }}
/>
```

### JSON-LD Structured Data (in BaseLayout.astro)
```astro
<script type="application/ld+json" set:html={JSON.stringify({
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "LocalBusiness",
      "@id": "[YOUR_DOMAIN]/#business",
      "name": "[YOUR NAME] — Solo Software House",
      "description": "Web app, SaaS MVP, landing page, dan AI integration.",
      "url": "[YOUR_DOMAIN]",
      "logo": "[YOUR_DOMAIN]/favicon.svg",
      "image": "[YOUR_DOMAIN]/og-image.jpg",
      "founder": {
        "@type": "Person",
        "name": "[YOUR NAME]",
        "jobTitle": "Software Developer",
        "sameAs": [
          "https://linkedin.com/in/[HANDLE]",
          "https://github.com/[HANDLE]"
        ]
      },
      "address": {
        "@type": "PostalAddress",
        "addressLocality": "Semarang",
        "addressRegion": "Jawa Tengah",
        "addressCountry": "ID"
      },
      "areaServed": {
        "@type": "Country",
        "name": "Indonesia"
      },
      "priceRange": "Rp 8.000.000 – Rp 50.000.000",
      "telephone": "[YOUR_WHATSAPP]",
      "email": "[YOUR_EMAIL]",
      "openingHoursSpecification": {
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday"],
        "opens": "09:00",
        "closes": "18:00"
      },
      "hasOfferCatalog": {
        "@type": "OfferCatalog",
        "name": "Software Development Services",
        "itemListElement": [
          {
            "@type": "Offer",
            "itemOffered": {
              "@type": "Service",
              "name": "Web App & SaaS MVP Development",
              "description": "Full-stack web application dan SaaS MVP dengan delivery 3–6 minggu"
            }
          },
          {
            "@type": "Offer",
            "itemOffered": {
              "@type": "Service",
              "name": "AI Feature Integration",
              "description": "Integrasi AI ke produk yang sudah ada — chatbot, summarizer, analyzer"
            }
          },
          {
            "@type": "Offer",
            "itemOffered": {
              "@type": "Service",
              "name": "Landing Page & Marketing Site",
              "description": "Landing page yang convert dengan performa dan animasi proper"
            }
          }
        ]
      }
    },
    {
      "@type": "WebSite",
      "@id": "[YOUR_DOMAIN]/#website",
      "url": "[YOUR_DOMAIN]",
      "name": "[YOUR NAME] — Solo Software House",
      "inLanguage": "id-ID"
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "Vibe coding itu kualitasnya bisa dipercaya?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "Vibe coding bukan berarti asal prompt. Setiap baris kode di-review manual, debug secara langsung, dan struktur proyek dijaga agar bersih dan maintainable. AI mempercepat proses — bukan menggantikan judgment."
          }
        },
        {
          "@type": "Question",
          "name": "Kode-nya gue punya setelah proyek selesai?",
          "acceptedAnswer": {
            "@type": "Answer",
            "text": "100%. Full ownership — kode, repo, domain, hosting credentials. Tidak ada vendor lock-in."
          }
        }
      ]
    }
  ]
})} />
```

### Sitemap
```js
// astro.config.mjs
import { defineConfig } from 'astro/config';
import tailwind from '@astrojs/tailwind';
import sitemap from '@astrojs/sitemap';

export default defineConfig({
  site: 'https://[YOUR_DOMAIN]',
  integrations: [tailwind(), sitemap()],
});
```

### robots.txt (in /public/robots.txt)
```
User-agent: *
Allow: /
Sitemap: https://[YOUR_DOMAIN]/sitemap-index.xml
```

### Performance — Image Optimization
- Use Astro's built-in `<Image>` component for all images
- Specify width, height, format="webp", loading="lazy" on below-fold images
- Hero image (if any): loading="eager", fetchpriority="high"
- All images must have descriptive `alt` text

### Core Web Vitals checklist
- [ ] No layout shift (CLS): set explicit width/height on all images
- [ ] Font preload: `<link rel="preload" as="font">` for Syne and DM Mono
- [ ] Preconnect: `<link rel="preconnect" href="https://fonts.googleapis.com">`
- [ ] No render-blocking scripts: all scripts `defer` or `type="module"`
- [ ] Ticker animation: CSS only, no JS

---

## CONTENT — COPY FINAL (BAHASA INDONESIA)

Paste ini ke src/data/ files masing-masing. Ganti placeholder [X] sesuai fakta lo.

```ts
// src/data/services.ts
export const services = [
  {
    icon: '⚡',
    name: 'Web App & SaaS MVP',
    desc: 'Dari ide ke produk yang bisa dipakai user. Full-stack dengan auth, database, payment, dan dashboard admin.',
    stack: ['Next.js', 'Supabase', 'Stripe'],
  },
  {
    icon: '🤖',
    name: 'AI Feature Integration',
    desc: 'Tambahin AI ke produk lo — chatbot, summarizer, analyzer. Bukan gimmick, tapi yang beneran berguna.',
    stack: ['Claude API', 'OpenAI', 'RAG'],
    accentStack: true,
  },
  {
    icon: '📱',
    name: 'Landing Page & Marketing Site',
    desc: 'Yang convert. Bukan template — didesain khusus untuk cerita bisnis lo.',
    stack: ['Next.js', 'Framer', 'Webflow'],
  },
  {
    icon: '🗄',
    name: 'Internal Tool & Dashboard',
    desc: 'CRM sederhana, inventory system, dashboard data — software internal yang bikin tim lo lebih efisien.',
    stack: ['React', 'PostgreSQL', 'Recharts'],
  },
  {
    icon: '🔌',
    name: 'API & Backend Service',
    desc: 'REST API, webhook, integrasi third-party. Bisa standalone atau sebagai backbone aplikasi lo.',
    stack: ['FastAPI', 'Node.js', 'Supabase'],
  },
  {
    icon: '🛒',
    name: 'E-Commerce Custom',
    desc: 'Toko online dengan checkout smooth, manajemen produk, dan integrasi payment gateway lokal.',
    stack: ['Next.js', 'Midtrans', 'Xendit'],
  },
];
```

```ts
// src/data/works.ts
export const works = [
  {
    category: 'B2B SaaS — HR Tech',
    title: 'Sistem Absensi & Payroll Otomatis',
    desc: 'Web app untuk manajemen karyawan dengan absensi QR, kalkulasi payroll otomatis, dan laporan bulanan.',
    result: '3 minggu, 80+ pengguna aktif',
    color: 'accent',
  },
  {
    category: 'AI Integration — E-Commerce',
    title: 'AI Customer Service untuk Toko Online',
    desc: 'Chatbot yang bisa jawab pertanyaan produk, cek status order, dan escalate ke CS manusia kalau perlu.',
    result: 'Kurangi tiket CS 60%',
    color: 'accent2',
  },
  {
    category: 'Marketing Site — Properti',
    title: 'Landing Page Perumahan + Booking Tour',
    desc: 'Site multi-halaman dengan galeri, kalkulator KPR, dan sistem booking kunjungan terintegrasi WhatsApp.',
    result: '12 hari, conversion rate 8%',
    color: 'neutral',
  },
  {
    category: 'Internal Tool — F&B',
    title: 'POS & Manajemen Stok Warung Kopi',
    desc: 'Kasir digital tablet-friendly dengan tracking stok real-time, laporan harian, dan alert stok menipis.',
    result: '4 minggu, 5 cabang pakai',
    color: 'neutral',
  },
];
```

```ts
// src/data/faqs.ts
export const faqs = [
  {
    q: 'Vibe coding itu kualitasnya bisa dipercaya?',
    a: 'Vibe coding bukan berarti asal prompt dan berharap. Gue tetap review setiap baris kode yang di-generate AI, debug secara manual, dan pastiin struktur proyeknya bersih dan maintainable. AI mempercepat prosesnya — bukan menggantikan judgment-nya.',
  },
  {
    q: 'Gimana kalau lo sakit atau ada halangan?',
    a: 'Ini risiko nyata dari kerja dengan satu orang. Makanya gue selalu kasih buffer waktu di setiap proyek, dan semua kode serta dokumentasi tersimpan di repo yang lo punya akses penuh — jadi kalau ada apa-apa, lo tidak tersandera.',
  },
  {
    q: 'Kode-nya gue punya setelah proyek selesai?',
    a: '100%. Gue transfer full ownership — kode, repo, domain, hosting credentials. Lo bebas bawa ke developer lain, modifikasi sendiri, atau apapun. Tidak ada vendor lock-in.',
  },
  {
    q: 'Bisa minta revisi setelah launch?',
    a: 'Setiap paket punya periode support post-launch. Di luar itu, lo bisa masuk ke paket retainer atau kita buat kesepakatan per-revisi. Gue tidak menghilang setelah delivery.',
  },
  {
    q: 'Bisa handle proyek dari luar kota?',
    a: 'Ya, semua proyek dijalankan remote. Lo di Jakarta, Surabaya, Bali, atau bahkan luar negeri — tidak masalah. Komunikasi via WhatsApp, Notion, dan Google Meet.',
  },
];
```

---

## THINGS TO NOT DO

- Jangan pakai `import React` — ini Astro, bukan Create React App
- Jangan pakai `px-*` sembarangan — konsisten dengan spacing system
- Jangan hardcode warna hex — selalu pakai CSS variables
- Jangan buat komponen terlalu granular — 11 komponen sudah cukup
- Jangan pakai border-radius kecuali memang dibutuhkan (avatar circle, badge pill)
- Jangan skip alt text pada gambar apapun
- Jangan pakai 1px border — selalu 0.5px
- Jangan pakai `position: fixed` untuk overlay/modal
- Jangan load JS library untuk hal yang bisa CSS-only (ticker, hover states)

---

## FINAL CHECKLIST SEBELUM DEPLOY

- [ ] `astro build` tanpa error atau warning
- [ ] Lighthouse score: Performance ≥ 90, SEO = 100, Accessibility ≥ 90
- [ ] Test di mobile (375px) dan desktop (1440px)
- [ ] All anchor links scroll correctly
- [ ] FAQ accordion works without JS errors
- [ ] Email CTA form shows feedback on submit
- [ ] OG image appears correctly saat link dishare di WhatsApp
- [ ] sitemap.xml accessible di /sitemap-index.xml
- [ ] robots.txt accessible di /robots.txt
- [ ] No console errors di browser devtools
- [ ] Replace semua placeholder [CAPS] dengan data asli

---

*Generated for solo software house project. Edit [CAPS] placeholders before use.*
