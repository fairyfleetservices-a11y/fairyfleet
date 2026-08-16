# FairyFleet — Website

A 4-page, animated, fully responsive site for FairyFleet Errands & Virtual Services Ltd., built from the brand's own SOP and marketing materials. No build step — pure HTML/CSS/JS, ready for GitHub Pages.

**Pages:** `index.html` (home) · `services.html` (all 6 divisions) · `about.html` (philosophy & standard) · `contact.html` (book a call / send a request)

## Ship it to GitHub Pages (5 minutes)

1. Create a new repo on GitHub (e.g. `fairyfleet-website`) — public, no README/gitignore (this folder already has them).
2. From this folder:
   ```bash
   git remote add origin https://github.com/<your-username>/fairyfleet-website.git
   git branch -M main
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Build and deployment → Source → GitHub Actions.** The included workflow (`.github/workflows/deploy.yml`) will build and publish automatically on every push to `main`.
4. Your site goes live at `https://<your-username>.github.io/fairyfleet-website/`. To use `fairyfleet.com` instead, add a `CNAME` file with your domain and point your DNS at GitHub Pages (Settings → Pages → Custom domain handles this for you).

## Connect the contact form

The form on `contact.html` currently falls back to opening the visitor's email app. To make it submit silently and land in your inbox:

1. Go to [web3forms.com](https://web3forms.com) (free) and create an access key with `hello@fairyfleet.com`.
2. In `contact.html`, find:
   ```html
   <form id="contact-form" data-access-key="YOUR_WEB3FORMS_ACCESS_KEY">
   ```
   Replace `YOUR_WEB3FORMS_ACCESS_KEY` with the key you received.
3. Commit and push — submissions will now email you directly with no server required.

*(Any similar static-form service — Formspree, Getform — works the same way; just swap the endpoint in `js/main.js`.)*

## Add real call booking

Right now "Book a Call" routes to the contact form. If you want an actual calendar (Calendly, Cal.com, etc.), drop their embed `<iframe>` or script into `contact.html` above the form — takes two minutes.

## Editing

- Colors, type, spacing, animations → `css/style.css` (all tokens at the top under `:root`)
- Shared behavior (nav, scroll reveals, form) → `js/main.js`
- Logo → `assets/logo.png`

## Notes

- Built mobile-first; test the hamburger nav and stacked layouts under 768px before shipping.
- All motion respects `prefers-reduced-motion`.
- Trust-bar client names (Digicel, JMMB, Sagicor, Sandals, VM Group) are pulled from FairyFleet's existing marketing poster — confirm current permission to display each logo/name before launch.
