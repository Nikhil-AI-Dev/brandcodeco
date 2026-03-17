# brandcodeco.com

Landing page for Brand Code Co — custom software & AI solutions. Single-file static site (HTML/CSS/JS in index.html).

## Architecture
- **Single file**: Everything lives in `index.html` — markup, styles (`<style>`), and scripts (`<script>`)
- **No build step**: Edit index.html directly, no bundler/framework
- **Blog posts**: Separate HTML files in `blog/` directory, same Starry Night theme
- **Static assets**: `og-image.png`, `sitemap.xml`, `CNAME`
- **Fonts**: Google Fonts (Syne, Inter, JetBrains Mono) loaded via CDN

## Color Palette — Starry Night
All colors defined as CSS custom properties in the `:root` block (~line 204):
- `--bg: #070d1f` — page background
- `--bg1: #0c1446` — card backgrounds
- `--bg2: #0f1a52` — input backgrounds
- `--bg3: #162060` — table headers
- `--cyan: #b3cde0` — primary accent (powder blue)
- `--gold: #2b5c92` — secondary accent (steel blue)
- `--lime: #7aa8c7` — tertiary accent (mid blue)
- `--rose: #7aa8c7` — fourth accent (mid blue)
- `--text: #efefef` — primary text
- `--text2: #b3cde0` — secondary text
- `--text3: #2b5c92` — muted text

When changing colors: update `:root` variables AND any inline `rgba()` values throughout the file. The JS particle canvas near the bottom also has hardcoded RGB strings.

## Infrastructure
- **Server**: AWS EC2 at `3.16.148.175`, user `ubuntu`
- **SSH key**: `C:/Users/nikhi/Downloads/leaselens-key.pem`
- **Web root**: `/var/www/brandcodeco/`
- **Nginx config**: `/etc/nginx/sites-available/brandcodeco`
- **Domain**: brandcodeco.com (GoDaddy, renews March 2027)
- **SSL**: Certbot (expires June 2026)
- **Co-hosted**: LeaseLens is also on this EC2 — **never touch leaselens files**

## Deploy
```bash
# 1. SCP to EC2 (direct write needs sudo, so use /tmp)
scp -i "C:/Users/nikhi/Downloads/leaselens-key.pem" index.html ubuntu@3.16.148.175:/tmp/index.html
scp -i "C:/Users/nikhi/Downloads/leaselens-key.pem" -r blog ubuntu@3.16.148.175:/tmp/blog

# 2. SSH in, move to web root, fix permissions
ssh -i "C:/Users/nikhi/Downloads/leaselens-key.pem" ubuntu@3.16.148.175 \
  "sudo cp /tmp/index.html /var/www/brandcodeco/index.html && sudo cp -r /tmp/blog /var/www/brandcodeco/blog && sudo chown -R www-data:www-data /var/www/brandcodeco/index.html /var/www/brandcodeco/blog"

# 3. Push to GitHub
git add -A && git commit -m "description" && git push origin main
```

## Forms & Integrations
- **Contact form**: Formspree (ID: `mjgaypav`) — POST to `https://formspree.io/f/mjgaypav`
- **Scheduling**: Calendly at `calendly.com/nikhil-brandcodeco/discovery`
- **Analytics**: GA4 `G-CMGXBGFVL9`
- **Search Console**: Verified via GA4
- **Structured data**: JSON-LD blocks for Organization, FAQPage, ProfessionalService, WebSite

## Products (listed on landing page)
- **SyndromeAI** — syndrome-ai.com (live) — gas station intelligence
- **LeaseLens** — coming soon — commercial real estate analytics
- **OnboardFlow** — coming soon — immigration tech

## Blog Posts
Located in `blog/` directory. Each post is a standalone HTML file with the Starry Night theme, GA4 tracking, and JSON-LD structured data.
- `blog/fuel-variance-gas-stations.html` — Operations / SyndromeAI
- `blog/spreadsheets-to-software-cre.html` — Real Estate / LeaseLens
- `blog/document-ocr-business-workflows.html` — AI & Automation / OnboardFlow

Linked from the Insights section on the landing page.

## Security
- **HSTS**: `max-age=31536000; includeSubDomains; preload`
- **CSP**: Locked down — self, Google Analytics, Formspree, Calendly, Google Fonts only
- **Headers**: X-Frame-Options, X-Content-Type-Options, X-XSS-Protection, Referrer-Policy, Permissions-Policy
- All resources loaded over HTTPS — no mixed content

## Mobile
- Responsive breakpoints: 1024px (tablet), 768px (phone), 380px (small phone)
- Burger menu on mobile — hides nav links, shows burger + Book a Call button
- Phone number hidden on mobile nav
- Full-width hero CTA buttons on mobile
- Floating mobile CTA bar appears on scroll
- Touch targets min 44px

## Rules
- Always deploy to EC2 after editing index.html or blog posts
- Always push to GitHub after deploying
- Never modify leaselens files on the EC2 server
- Keep landing page in one index.html — do not split into separate CSS/JS files
- Blog posts go in `blog/` as separate HTML files
- Tab title should be just "brandcodeco"
- Nav background must use `rgba(7,13,31,.6)` to match --bg
