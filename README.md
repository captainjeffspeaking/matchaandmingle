# Matcha & Mingle - Landing Page

A modern, single-page wellness landing site for **Matcha & Mingle**, presented by the **Plus 1 Social App**.
Built as a static site (HTML/CSS/JS, no build step). Email capture uses **Netlify Forms**.

## What's in this folder

| File | Purpose |
|------|---------|
| `index.html` | The landing page |
| `success.html` | "You're on the list" page shown after someone signs up |
| `netlify.toml` | Netlify config (publish settings + security headers) |
| `README.md` | This file |

---

## 1. Deploy to Netlify (drag & drop)

1. Go to **https://app.netlify.com/drop**
2. Log in (or sign up - it's free).
3. **Drag this entire `matcha-and-mingle` folder** onto the drop zone.
4. Netlify uploads it and gives you a live URL like `random-name-123.netlify.app`. Done - your site is live.

> Tip: To get a tidy dashboard (and easy redeploys), instead click **"Add new site → Deploy manually"** from your Netlify team page and drop the folder there. Same result, but the site is saved to your account.

### Redeploying later
Edit the files, then drag the folder onto the same site's **Deploys** tab (or back onto the drop page). No rebuild needed.

---

## 2. Email signups (Netlify Forms - already wired up)

The signup form is ready to go. After your **first deploy**, Netlify auto-detects the form.

- View submissions: **Netlify dashboard → your site → Forms → "updates"**.
- Get notified of new signups: **Forms → Settings & usage → Form notifications** → add an email or Slack webhook.
- Export anytime as CSV from the Forms tab.

No backend, no API keys. Free tier covers 100 submissions/month.

---

## 3. Point your GoDaddy domain (matchaandmingle.com) at Netlify

You bought `matchaandmingle.com` on GoDaddy. Two ways to connect it:

### Option A - Easiest: use Netlify DNS (recommended)
1. In Netlify: **Site → Domain management → Add a domain** → type `matchaandmingle.com`.
2. Netlify shows you **4 nameservers** (e.g. `dns1.p01.nsone.net`, …).
3. In **GoDaddy**: **My Products → Domains → matchaandmingle.com → DNS → Nameservers → Change → "I'll use my own nameservers"**, and paste Netlify's 4 nameservers.
4. Save. Propagation takes ~15 min to 24 hrs. Netlify then auto-issues a free HTTPS certificate.

### Option B - Keep GoDaddy DNS, just add records
1. In Netlify: **Domain management → Add domain** → `matchaandmingle.com` (it'll say "awaiting external DNS").
2. In **GoDaddy → DNS → Records**, add:
   - **A record** - Host: `@` → Value: `75.2.60.5` (Netlify's load balancer IP)
   - **CNAME** - Host: `www` → Value: `your-site-name.netlify.app`
3. Back in Netlify, set `www` (or the apex) as primary and **Verify**. HTTPS is issued automatically.

> Use **Option A** unless you host email or other services on this domain. Confirm Netlify's exact nameservers/IP in their dashboard - they occasionally change.

---

## 4. Customize

- **Event date / location:** edit the `.details` section in `index.html` (search for "Early July").
- **Wording / colors:** colors are CSS variables at the top of `index.html` (`:root { --matcha … }`).
- **Social share image:** add an `og-image.png` (1200×630) to this folder for nice link previews. The meta tag already points to it.

---

Presented by the Plus 1 Social App · 🍵
