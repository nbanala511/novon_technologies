# Novon Technologies — Website

A static, responsive 4-page site (Home, About, Services, Contact) built with plain HTML, CSS, and vanilla JavaScript — no build step, no framework.

## Running it locally

No build tools needed. Either:

- Double-click `index.html` to open it directly in a browser, or
- Serve it with a simple local server (recommended, avoids relative-path quirks):
  ```
  python3 -m http.server 8000
  ```
  then open `http://localhost:8000`.

## Deploying (GitHub → Cloudflare Pages)

1. Push this folder to a new GitHub repository.
2. In Cloudflare, go to **Workers & Pages → Create a Pages project → Connect to Git**, and select the repo.
3. Leave the build command blank (this is plain HTML/CSS/JS — nothing to build) and set the output directory to `/` (the repo root).
4. Deploy. Cloudflare gives you a free `*.pages.dev` preview URL.
5. Once you're happy, buy a domain (Cloudflare Registrar is recommended — see the project plan doc) and add it under the Pages project's **Custom Domains**.

Every future `git push` to the connected branch auto-redeploys.

## Before going live — content placeholders to replace

- **Contact form access key**: `contact.html` posts to [Web3Forms](https://web3forms.com), a free form-handling service for static sites. Sign up for a free access key and replace `YOUR_ACCESS_KEY_HERE` in `contact.html`.
- **Email address**: `hello@novontechnologies.com` appears on the Contact page and is a placeholder until the real domain/mailbox exists.
- **Firm name**: "Novon Technologies" is a working name — confirm domain and trademark/business-name availability before it's final (see the project plan doc).
- **Location**: "Toronto, Ontario, Canada" is used as a placeholder location in the footer and Contact page — update or remove if incorrect.
- **Favicon/logo**: `assets/favicon.svg` is a simple placeholder mark (an "N" in orange on black). Swap in real branding whenever it exists.
- **Founder bio**: drafted from the founder's real background (see the project plan doc), intentionally without a personal name or employer names, per instruction. Update if the positioning changes.

## Structure

```
novon-technologies/
├── index.html       Home
├── about.html       About
├── services.html    Services (6 anchored sections)
├── contact.html      Contact (form + info)
├── css/style.css     Shared stylesheet (black + orange theme)
├── js/script.js      Mobile nav, active-link highlighting, scroll reveal
└── assets/favicon.svg
```

## Design notes

- Palette: near-black background (`#0a0a0b`) with a single orange accent (`#ff6a1f`), inspired by a mix of itrexgroup.com's clean/minimal structure and makoitlab.com's use of a bold accent color on a dark base.
- One responsive codebase for both desktop and mobile — no separate mobile site. Mobile switches to a stacked single-column layout with a hamburger menu below 720px.
- No CMS/database — content lives directly in the HTML files.
