# Vishwodya Listener

## Current State
Fully built MVP with HomePage, BookPage, ConfirmationPage, AdminLoginPage, and AdminDashboardPage. The `index.html` has an empty `<title>` and no meta tags. No robots.txt or sitemap.xml exist.

## Requested Changes (Diff)

### Add
- Full SEO meta tags in `index.html`: title, description, keywords, canonical, author, robots
- Open Graph tags (og:title, og:description, og:type, og:url, og:image, og:locale) for WhatsApp/Facebook link previews
- Twitter Card meta tags
- JSON-LD structured data (Organization + WebSite schema) with social links for Instagram, YouTube, Facebook
- `robots.txt` in public folder -- allow all, disallow /admin
- `sitemap.xml` in public folder -- listing /, /book pages
- `useSEO` hook for per-page dynamic title/description updates
- Per-page SEO applied on HomePage, BookPage, ConfirmationPage

### Modify
- `index.html`: populate title, add all meta/OG/Twitter/JSON-LD tags
- `HomePage.tsx`: call useSEO with homepage-specific title and description
- `BookPage.tsx`: call useSEO with booking-specific title and description
- `ConfirmationPage.tsx`: call useSEO with confirmation-specific title

### Remove
- Nothing removed

## Implementation Plan
1. Update `index.html` with base SEO, OG, Twitter Card tags and JSON-LD structured data
2. Create `src/frontend/public/robots.txt`
3. Create `src/frontend/public/sitemap.xml`
4. Create `src/frontend/src/hooks/useSEO.ts` hook
5. Wire useSEO in HomePage, BookPage, ConfirmationPage
