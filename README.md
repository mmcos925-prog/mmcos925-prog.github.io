# brandoncoston.tech — Personal Portfolio Website

A responsive, security-hardened personal portfolio site built with vanilla HTML/CSS/JavaScript, deployed on Netlify CDN with a custom domain and enforced HTTPS.

**Live site:** [brandoncoston.tech](https://brandoncoston.tech)

---

## What It Does

- Showcases cloud security projects, certifications, and technical skills
- Implements HTTP security headers achieving an **A security grade** on securityheaders.com
- Serves globally via Netlify's CDN for fast load times
- Enforces HTTPS with automatic SSL certificate renewal via Let's Encrypt
- Scroll-reveal animations using the Intersection Observer API

---

## Security Implementation

Security headers configured via `_headers` file and verified on [securityheaders.com](https://securityheaders.com):

| Header | Value | Purpose |
|---|---|---|
| `X-Frame-Options` | `DENY` | Prevents clickjacking attacks |
| `X-Content-Type-Options` | `nosniff` | Prevents MIME-type sniffing |
| `Referrer-Policy` | `strict-origin-when-cross-origin` | Controls referrer information |
| `Permissions-Policy` | `geolocation=(), microphone=(), camera=()` | Restricts browser API access |
| `Strict-Transport-Security` | `max-age=31536000; includeSubDomains` | Enforces HTTPS for 1 year |
| `Content-Security-Policy` | See `_headers` | Restricts resource loading sources |

**Security grade: A** — verified at securityheaders.com

---

## Tech Stack

| Technology | Purpose |
|---|---|
| HTML5 / CSS3 | Structure and styling |
| JavaScript (vanilla) | Scroll reveal animations |
| Netlify | Hosting, CDN, SSL, header injection |
| Google Fonts (Space Grotesk + Space Mono) | Typography |
| Namecheap | Domain registration and DNS |
| GitHub | Version control and source |

---

## Architecture

```
GitHub repo (mmcos925-prog/mmcos925-prog.github.io)
         ↓
Netlify — connected via GitHub integration
         ↓
Auto-deploys on every push to main
         ↓
Netlify CDN serves globally
         ↓
_headers file applies security headers on every response
         ↓
brandoncoston.tech (custom domain via Namecheap DNS)
         ↓
HTTPS enforced via Let's Encrypt SSL certificate
```

---

## DNS Configuration

```
A Record     @    75.2.60.5                      (Netlify load balancer)
CNAME        www  apex-loadbalancer.netlify.com  (www redirect)
```

---

## Local Development

```bash
git clone https://github.com/mmcos925-prog/mmcos925-prog.github.io
cd mmcos925-prog.github.io
open index.html
```

No build tools or dependencies required — pure HTML/CSS/JS.

---

## Deployment

Every push to `main` automatically triggers a Netlify deployment:

```bash
git add .
git commit -m "Update site"
git push
```

Netlify builds and deploys in under 30 seconds.

---

## Performance & Security Scores

- **securityheaders.com:** A
- **HTTPS:** Enforced via Let's Encrypt
- **CDN:** Netlify global edge network
- **No tracking:** Zero analytics or third-party data collection

---

## Author

**Brandon Coston** — Cloud Security Professional
AWS Certified Cloud Practitioner | Google Cybersecurity Certificate
[brandoncoston.tech](https://brandoncoston.tech) | [github.com/mmcos925-prog](https://github.com/mmcos925-prog)
