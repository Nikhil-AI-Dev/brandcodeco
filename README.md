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

## Products
- SyndromeAI — syndrome-ai.com (live)
- LeaseLens — coming soon
- OnboardFlow — coming soon

## Deploy
SCP index.html to EC2 at 3.16.148.175:/var/www/brandcodeco/
then chown www-data:www-data

## Notes
- Do NOT touch leaselens files on the same EC2
- SSL via Certbot — renews June 2026
- Domain via GoDaddy — renews March 2027
