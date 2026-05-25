# Deploy guide — Quentin's checklist

End-to-end runbook for taking this repo from "git push" to "Patrick's domain
loads with a padlock." Roughly 30 minutes total, mostly waiting for DNS.

---

## Prerequisites

- Repo is on GitHub: `qhalsey/patrick-pockels-golf` ✅
- Local build works: `npm run build` succeeds ✅
- Branch is merged (or about to be) into `main`

---

## Phase A — Vercel (one-time, ~5 min)

1. Sign in at https://vercel.com using **GitHub** (single sign-on; gives
   Vercel access to your repos).
2. Click **Add New → Project**.
3. Find `patrick-pockels-golf` in the import list → **Import**.
4. Vercel auto-detects Astro:
   - **Framework Preset:** Astro
   - **Build Command:** `npm run build` *(auto)*
   - **Output Directory:** `dist` *(auto)*
   - **Install Command:** `npm install` *(auto)*
   No env vars needed.
5. Click **Deploy**. First build takes ~30 seconds.
6. You'll get a live URL like `patrick-pockels-golf.vercel.app`. Open it,
   confirm everything renders.

> **From now on:** every push to `main` redeploys automatically. Push to a
> branch → Vercel builds a **preview deployment** with its own URL — great
> for showing Patrick changes before they go live.

---

## Phase B — Domain in Cloudflare (~10 min + DNS wait)

1. Sign in at https://dash.cloudflare.com
2. Top right → **Add a Domain** → **Register a new domain**
3. Search `patrickpockelsgolf.com`. If available, ~$10–12/yr (Cloudflare
   sells at-cost).
4. Buy. Cloudflare auto-configures itself as nameservers — nothing to do.

If the domain is taken, fallbacks in order of preference:
- `patrickpockelsgolfhb.com`
- `pockelsgolf.com`
- `coachpockels.com`

---

## Phase C — Point the domain at Vercel (~5 min)

1. **Vercel → Project → Settings → Domains** → **Add**
2. Type `patrickpockelsgolf.com` → **Add**
3. Vercel shows you DNS records to create. They'll look like one of:

   **Apex (root domain):**
   ```
   Type: A     Name: @     Value: 76.76.21.21
   ```

   **www subdomain:**
   ```
   Type: CNAME    Name: www    Value: cname.vercel-dns.com
   ```

4. Open **Cloudflare → Your domain → DNS → Records → Add record**.
   Paste exactly what Vercel showed you.

   > **Important:** For the `A` record, set Cloudflare's "Proxy status" to
   > **DNS only** (gray cloud, not orange). Vercel terminates HTTPS itself
   > — you don't want Cloudflare's proxy in the middle.

5. Back in Vercel, also add `www.patrickpockelsgolf.com`. Set the apex as
   the canonical and let `www` redirect to it (Vercel does this in the
   Domains panel with one click).

---

## Phase D — Wait for DNS, then verify (~5 min – 2 hr)

DNS usually propagates in under 10 minutes with Cloudflare, but can take
up to a couple hours.

Once Vercel shows ✅ next to the domain:

- [ ] `https://patrickpockelsgolf.com` loads, padlock shows
- [ ] `http://patrickpockelsgolf.com` redirects to `https://`
- [ ] `https://www.patrickpockelsgolf.com` redirects to the apex
- [ ] No mixed-content warnings (check browser devtools console)

**The HTTPS cert:** Vercel auto-provisions Let's Encrypt the moment DNS
resolves, and auto-renews forever. You do nothing.

---

## Phase E — Search Console (~5 min, do once after launch)

1. Go to https://search.google.com/search-console
2. **Add property** → URL prefix → `https://patrickpockelsgolf.com`
3. Verify ownership — easiest method:
   - Choose **HTML tag** → copy the `<meta>` tag
   - Add it to `src/layouts/Layout.astro` in `<head>`
   - Commit, push, wait for Vercel deploy
   - Back in Search Console, click **Verify**
4. Once verified → **Sitemaps** → submit
   `https://patrickpockelsgolf.com/sitemap-index.xml`

That tells Google "here's everything on the site, please crawl it." Indexing
usually starts within 24 hours.

---

## Phase F — Pre-launch sanity check

- [ ] Run https://pagespeed.web.dev on the live URL — should be green
- [ ] Test the mock booking flow end-to-end (or the real Calendly once swapped)
- [ ] Text the URL to yourself — does the link preview card look right?
      (validates OG tags)
- [ ] Open on an actual phone — hero photo loads fast, nothing overflows
- [ ] All `tel:` links call when tapped on mobile
- [ ] All `mailto:` links open mail compose with prefilled subject

---

## Future updates

To change copy / images / pricing later:

```powershell
git checkout main
git pull
# make edits
git add -A
git commit -m "tweak hero copy"
git push origin main
```

Vercel builds + deploys in ~30 seconds. No other steps.

For bigger features (Calendly swap, Google reviews widget, new sections),
open a branch, push, share the Vercel preview URL with Patrick for sign-off,
then merge to main.
