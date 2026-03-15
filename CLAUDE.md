# brandcodeco.com — Claude Context

## Color Palette (Starry Night)
- --bg:        #070d1f  (page background)
- --bg1:       #0c1446  (card backgrounds)
- --bg2:       #0f1a52  (input backgrounds)
- --bg3:       #162060  (table headers)
- --cyan:      #b3cde0  (primary accent, powder blue)
- --gold:      #2b5c92  (secondary accent, steel blue)
- --lime:      #7aa8c7  (tertiary accent, mid blue)
- --rose:      #7aa8c7  (fourth accent, mid blue)
- --text:      #efefef  (primary text)
- --text2:     #b3cde0  (secondary text)
- --text3:     #2b5c92  (muted text)

## Infrastructure
- Server: EC2 at 3.16.148.175
- Web root: /var/www/brandcodeco/
- Nginx config: /etc/nginx/sites-available/brandcodeco
- Domain: brandcodeco.com (GoDaddy, renews March 2027)
- SSL: Certbot (expires June 2026)
- Co-hosted: leaselens also on this EC2 — do not touch

## Forms & Integrations
- Formspree ID: mjgaypav
- Calendly: calendly.com/nikhil-brandcodeco/discovery
- Analytics: GA4 G-CMGXBGFVL9
- Google Search Console: verified via GA4

## Deploy Workflow
1. Edit index.html locally or via Claude Code
2. SCP to EC2: scp index.html user@3.16.148.175:/var/www/brandcodeco/
3. SSH and fix permissions: sudo chown www-data:www-data /var/www/brandcodeco/index.html
4. Push to GitHub for version control
