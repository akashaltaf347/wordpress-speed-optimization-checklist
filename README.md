# WordPress Speed Optimization Checklist

The exact checklist I run on every client WordPress site before calling it done. Targets: **LCP ≤ 2.5s · INP ≤ 200ms · CLS ≤ 0.1** (measure with PageSpeed Insights and GTmetrix).

## 1. Measure first
- [ ] Baseline: PageSpeed Insights (mobile + desktop), GTmetrix waterfall
- [ ] Note LCP / INP / CLS numbers before touching anything

## 2. Caching
- [ ] Page-cache plugin (or server-level cache) active and verified
- [ ] Object cache for dynamic sites (Redis/Memcached where available)
- [ ] Browser caching headers set

## 3. Images
- [ ] Convert to WebP/AVIF, sized to display dimensions (no 4000px uploads)
- [ ] Lazy-load below-the-fold images
- [ ] Serve via CDN where possible

## 4. Code
- [ ] Minify CSS/JS, defer non-critical JavaScript
- [ ] Remove unused CSS (watch for page-builder bloat)
- [ ] Limit webfonts: 2 families max, `font-display: swap`

## 5. Database
- [ ] Clean post revisions, transients, spam comments
- [ ] Optimize tables (monthly on active sites)

## 6. Hosting & delivery
- [ ] PHP 8.x, HTTP/2 or HTTP/3
- [ ] CDN in front (e.g. Cloudflare free tier)

## 7. Plugin audit
- [ ] Deactivate and delete anything unused
- [ ] No duplicate functionality (one slider plugin, one SEO plugin…)
- [ ] Replace heavy plugins with lighter alternatives where it matters

## 8. Recheck
- [ ] Re-run PageSpeed Insights + GTmetrix, compare against baseline
- [ ] Fix regressions, document the final numbers for the client
