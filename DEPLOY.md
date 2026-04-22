# Monica & Me — Deploy Guide

This folder is ready to upload. Below is the fastest free path to a live URL,
then how to attach your own domain.

---

## Part 1 — Get a live URL in 5 minutes (free, no credit card)

### Option A — Vercel drag-and-drop (easiest, recommended)

1. Go to **https://vercel.com/signup** — sign up with your Google or GitHub
   account. Free tier is enough.
2. On the dashboard, click **"Add New…" → "Project"**.
3. Choose **"Deploy without a Git repository"** (the small link below the
   main import box) **→ "Browse templates" isn't needed**.
4. When it asks for files, **drag this entire `website` folder onto the page**
   (the one that contains `index.html` and `assets/`).
5. Name the project `monica-and-me` (or whatever you like).
6. Click **Deploy**.

After ~30 seconds you'll get a live URL like
`https://monica-and-me.vercel.app` — share it, test it, open it on your phone.

### Option B — Netlify drag-and-drop (equally simple)

1. Go to **https://app.netlify.com/drop**.
2. Drag the `website` folder onto the big drop zone.
3. Done — you get a URL like `https://random-name.netlify.app`. You can
   rename it in Site settings → Change site name.

### Option C — Cloudflare Pages (best if you plan to scale)

1. Sign up at **https://pages.cloudflare.com**.
2. Create project → Direct upload → drag the `website` folder.
3. Free URL is `https://monica-and-me.pages.dev`.

---

## Part 2 — Buy your domain (5 minutes, ~$10–$15)

Domain names don't allow the `&` character, so `monica&me.com` isn't valid.
Good alternatives — **check availability by clicking**:

| Candidate | Check link (direct search) |
|---|---|
| `monicaandme.com` | [Namecheap](https://www.namecheap.com/domains/registration/results/?domain=monicaandme.com) · [Porkbun](https://porkbun.com/checkout/search?q=monicaandme.com) |
| `monica-and-me.com` | [Namecheap](https://www.namecheap.com/domains/registration/results/?domain=monica-and-me.com) · [Porkbun](https://porkbun.com/checkout/search?q=monica-and-me.com) |
| `monicame.com` | [Namecheap](https://www.namecheap.com/domains/registration/results/?domain=monicame.com) · [Porkbun](https://porkbun.com/checkout/search?q=monicame.com) |
| `monicame.co` | [Namecheap](https://www.namecheap.com/domains/registration/results/?domain=monicame.co) · [Porkbun](https://porkbun.com/checkout/search?q=monicame.co) |
| `monicaandme.shop` | [Namecheap](https://www.namecheap.com/domains/registration/results/?domain=monicaandme.shop) · [Porkbun](https://porkbun.com/checkout/search?q=monicaandme.shop) |
| `shopmonicaandme.com` | [Namecheap](https://www.namecheap.com/domains/registration/results/?domain=shopmonicaandme.com) · [Porkbun](https://porkbun.com/checkout/search?q=shopmonicaandme.com) |

**Recommendation**: **Porkbun** is typically the cheapest registrar (~$10/yr for
.com, free WHOIS privacy). Namecheap is also solid. Avoid GoDaddy — their
renewal prices are significantly higher.

At checkout:
- Enable **WHOIS Privacy** (usually free at Porkbun/Namecheap) — hides your
  home address from public records.
- Auto-renew ON.
- Skip the upsells (email hosting, SSL — Vercel/Netlify give you SSL free).

---

## Part 3 — Connect your domain to the live site

Whichever host you picked in Part 1, the flow is the same: point DNS at the host.

### On Vercel

1. In your Vercel project → **Settings → Domains** → **Add**.
2. Type `monicaandme.com` (or whatever you bought) → **Add**.
3. Vercel shows you DNS records to create — either an `A` record or a `CNAME`.
4. Log into your registrar → DNS settings → add those records exactly.
5. Wait 5–30 minutes. The site will be live on your domain with free SSL.

Example records Vercel will give you:

```
Type   Name   Value
A      @      76.76.21.21
CNAME  www    cname.vercel-dns.com
```

### On Netlify

1. Site → **Domain management → Add custom domain**.
2. Netlify will show you either to change nameservers (easiest) or add
   two records. Follow their on-screen instructions.

### On Cloudflare Pages

If you buy the domain at **Cloudflare Registrar** (at-cost pricing — often
cheapest overall), DNS is auto-configured and setup is literally one click.

---

## Part 4 — After-launch checklist

- [ ] Open your live URL on desktop, tablet, phone. Everything should look right.
- [ ] Click every "Shop on Amazon" / "Buy" button — confirm it opens
      `https://www.amazon.com/dp/B0GC66TXDR` in a new tab.
- [ ] Share with 3 friends for a gut-check before you start running ads.
- [ ] Set up Google Analytics or Plausible (free/cheap) to track visits — this
      lets you see which sections people scroll to.
- [ ] If you plan to run Amazon Attribution / off-Amazon ads, consider
      registering at **https://advertising.amazon.com/attribution** and wrapping
      your Amazon URL with attribution tags — you'll earn bonus referral credit
      on every sale that comes through this site.
- [ ] Replace the three placeholder customer reviews in `index.html` with real
      Amazon reviews once you have a few 5-star ones.

---

## File structure for reference

```
website/
├── index.html        ← the page
├── DEPLOY.md         ← this guide
└── assets/
    ├── hero-group.png
    ├── s1-life.png … s6-life.png
    ├── s1-flat.png … s6-flat.png
    ├── editorial-1.png
    ├── editorial-2.png
    └── editorial-3.png
```

To change a photo: drop a new image into `assets/` with the same filename,
re-deploy. Done.

To change copy: open `index.html` in any editor, find the text, change it,
re-deploy.

---

## Total cost to be live on your own domain

| Item | Cost |
|---|---|
| Hosting (Vercel/Netlify/Cloudflare free tier) | **$0** |
| Domain `.com` | **$10–$12 / year** |
| SSL certificate | **$0** (auto) |
| **Total year 1** | **~$10–$12** |

That's it. No monthly fees, no upsells required.
