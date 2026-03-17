# Brand Code Co — brandcodeco.com

Landing page for Brand Code Co, a custom software and AI solutions company.

## Live Site
https://brandcodeco.com

## Stack
- Single-file HTML/CSS/JS — no framework
- Hosted on AWS EC2 (Nginx)
- Forms: Formspree (ID: mjgaypav)
- Scheduling: Calendly (calendly.com/nikhil-brandcodeco/discovery)
- Analytics: GA4 (G-CMGXBGFVL9)

## Color Palette — Starry Night
- Background: #070d1f
- Cards: #0c1446
- Primary accent: #b3cde0
- Secondary accent: #2b5c92
- Text: #efefef

## Services
- [Custom SaaS Development](https://brandcodeco.com/services/custom-software.html)
- [AI & Automation Integration](https://brandcodeco.com/services/ai-automation.html)
- [Operations Software](https://brandcodeco.com/services/operations-software.html)
- [Data Dashboards & Analytics](https://brandcodeco.com/services/data-dashboards.html)

## Blog
- [How Gas Stations Silently Lose $800/Month on Fuel Variance](https://brandcodeco.com/blog/fuel-variance-gas-stations.html)
- [Why CRE Operators Still Use Spreadsheets (And How to Replace Them)](https://brandcodeco.com/blog/spreadsheets-to-software-cre.html)
- [Document OCR in 2026: What Actually Works for Business Workflows](https://brandcodeco.com/blog/document-ocr-business-workflows.html)

## Products
- SyndromeAI — syndrome-ai.com (live)
- LeaseLens — coming soon
- OnboardFlow — coming soon

## Lead Magnet
- AI Readiness Checklist — email capture on landing page (Formspree)

## Deploy
SCP index.html, blog/, and services/ to EC2 at 3.16.148.175:/var/www/brandcodeco/
then chown -R www-data:www-data

## Security
- HTTPS enforced with HSTS preload
- Content-Security-Policy restricts all resources to trusted origins
- Full security headers (X-Frame-Options, X-Content-Type-Options, Referrer-Policy, Permissions-Policy)

## Mobile
- Fully responsive: 1024px, 768px, 380px breakpoints
- Burger menu, floating CTA, full-width buttons on phone

## Notes
- Do NOT touch leaselens files on the same EC2
- SSL via Certbot — renews June 2026
- Domain via GoDaddy — renews March 2027
